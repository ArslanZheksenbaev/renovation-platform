# 5. Technology Comparison

## Decision 1: Backend platform

Requirements: role-based access, secure storage of project data, marketplace/order/contract logic, orchestration of AI modules, maintainability by a team of three.

| Criterion | Java Spring Boot | Python FastAPI | Node.js NestJS |
| --- | --- | --- | --- |
| Team skills and existing plan | The project draft already assigns Spring Boot to the backend developer, so no learning cost | Used by the ML engineers, but not by the backend developer | No team member is planned to work with it, so it adds a third stack |
| Security and role-based access | Spring Security is a mature, widely used solution for roles, sessions and tokens | Possible with libraries, but more of it must be assembled and maintained by hand | Good built-in guards and a large ecosystem, but less established for complex role models |
| Transactions and relational data | Strong support for transactions and JPA mapping, which fits orders, contracts and design versions | Capable, but with fewer ready conventions for large relational models | Capable through ORMs; comparable to FastAPI |
| Integration with ML libraries | Weak: ML code must run in a separate service | Native: the same language as the ML libraries | Weak: also requires a separate ML service |
| Time to first working API | Slower start because of more configuration | Fastest start | Fast start |

Decision: Spring Boot for the core application, with ML modules as separate Python (FastAPI) services. Spring Boot is best where the core logic lies (access, orders, contracts, stages), and FastAPI is best where ML libraries are needed. Splitting the responsibilities removes the weakness of each choice and matches the roles in the team.

Trade-off: two languages and an inter-service API to maintain.

## Decision 2: Data storage

Requirements: structured relational data (users, rooms, designs, estimates, versions, contracts); consistency between the approved design, the estimate and the contract; large binary files (photos, renders).

| Criterion | PostgreSQL | MySQL | MongoDB |
| --- | --- | --- | --- |
| Relational integrity and transactions (room -> approved design and specification -> material estimate -> renovation request with fixed labour amount -> accepted contractor response -> contract) | Full ACID transactions and strict constraints keep the chain consistent | Also reliable, with slightly fewer advanced features | Supports transactions, but the model is document-oriented, so referential integrity across the chain depends on application code |
| Flexible fields (finish specifications, AI job parameters) | JSONB stores semi-structured data inside the relational model, with indexing | JSON support exists but is more limited | Natural fit, since documents are flexible by design |
| Fit with Spring Data/JPA and migrations | Well supported | Well supported | Supported, but the relational chain of the project does not map naturally to documents |
| Reports and price history | Rich SQL: window functions, aggregates | Adequate | Aggregation is possible but less convenient for relational reports |

Decision: PostgreSQL for all structured data, with JSONB for flexible specifications. It covers both the strict relational chain and the semi-structured fields in one system, which MySQL (weaker flexible fields) and MongoDB (weaker integrity) each cover only partly. Images and generated renders go to S3-compatible object storage (e.g. MinIO in development); the database keeps only references, metadata and the version of the request that produced each file. Storing large files inside the relational database was rejected because it makes backups and queries slower.

## Decision 3: AI design generation approach

Requirements: generate renovation concepts from the user's room photo; keep the room structure; allow editing and human review; no model training from scratch (project scope); reasonable cost; privacy of user photos.

| Criterion | A. Hosted commercial image API | B. Self-hosted Stable Diffusion + pre-trained structural control (ControlNet-type), orchestrated with ComfyUI/diffusers | C. Custom-trained control network (IDCN-like) |
| --- | --- | --- | --- |
| Structure preservation of the room | Depends on the provider; control over walls and openings is limited | Pre-trained control networks preserve walls and edges, but may not generate furniture reliably on their own, so this must be tested | Designed specifically for interior structure; the strongest option |
| Control and editing (masks, sketches, prompts) | Limited to what the provider exposes | Modular node-based pipelines allow masks, sketches and prompt control | Full control, as the model is ours |
| Fit with the "no training from scratch" scope | Fits: nothing to train | Fits: only pre-trained components | Does not fit: needs a paired dataset of thousands of images and days of GPU training |
| Cost per request and vendor lock-in | Per-call fees and dependence on one provider | Only GPU cost; models are replaceable | GPU cost plus training cost |
| Privacy of user photos | Photos leave our infrastructure | Photos stay in our infrastructure | Photos stay in our infrastructure |
| Implementation effort for the MVP | Lowest: a single API call | Medium: pipeline setup and GPU access | Highest: dataset creation, training, evaluation |

Decision: Option B as the main path. It is the only option that preserves structure reasonably, gives editing control, respects the scope, and keeps photos private at an acceptable effort. Option A is allowed as a replaceable fallback behind the same internal API. Option C is documented as a future improvement, because its data and compute needs exceed the project scope. The pipeline always includes a human selection/editing step before a design is approved.

Risk: keeping the structure while generating furniture is the known weak point of ControlNet-type methods, so the verification plan must measure structure preservation and include a fallback (sketch-based generation: unfurnished room image -> sketch -> designer edit -> render).

## Decision 4: Cost and material estimation method

Requirements: estimate linked to the selected design; uncertainty ranges; explainable breakdown; little renovation training data available; accuracy comparable against a reference.

| Criterion | A. Rule-based: quantity take-off × unit-price table | B. Pure ML regression (gradient boosting) | C. Hybrid: A as baseline + ML correction with prediction intervals |
| --- | --- | --- | --- |
| Works with little training data | Needs no training data, only a price table | Needs many records; published results rely on thousands of records in a narrow domain | Baseline works from day one; ML is added when data accumulates |
| Accuracy potential | Limited: cannot capture hidden cost effects | High on well-covered data: boosting models clearly outperform linear models in comparable studies | Highest: baseline accuracy plus ML correction |
| Explainability of line items | Fully transparent: every item is quantity × price | Weaker: needs feature-attribution methods (SHAP-type) to explain | Transparent baseline plus explained correction |
| Uncertainty ranges | Only through manual scenario ranges (min/max prices) | Prediction intervals are possible | Intervals on the ML correction, plus price scenarios |
| Implementation effort | Lowest | Medium | Medium–high: both parts must be built |

Decision: Option C. Material quantities multiplied by documented unit prices form the deterministic baseline, which is also used for evaluation. The ML component estimates material costs only; contractor labour payment is set by the homeowner and recorded separately. Candidate models include HistGradientBoosting, XGBoost, and CatBoost. The final model and prediction-interval method will be selected using our validation data and compared against the deterministic baseline..

Risk: until a renovation dataset exists, the ML part adds little, so the project must reserve time for importing and cleaning price data.

## Decision 5: Component interaction

Requirements: the core backend calls the design and cost services; image generation and model inference are slow compared with ordinary requests; results must be traceable to a request version.

| Criterion | A. Synchronous REST only | B. REST + asynchronous job queue (RabbitMQ or Redis) with status polling | C. gRPC between services |
| --- | --- | --- | --- |
| Handling of long generation jobs | A request may time out or block while an image is generated | The request returns immediately; the job runs in the background and the client polls its status | Supports streaming, but a long call still holds a connection unless combined with a queue |
| Simplicity for a small team | Simplest to build and debug | One more component (the queue), but a widely known pattern | Needs schema definitions and extra tooling |
| Traceability (job id, request version, result) | Possible, but there is no job object unless added | A job record with state (queued, running, done, failed) is natural, and it links to the design/estimate version in the handoff table | Possible, but not built in |
| Compatibility with Spring Boot and Python services | Fully compatible | Fully compatible | Compatible, with additional setup on both sides |

Decision: Option B. The client and the core backend communicate through REST/JSON. The core submits generation and estimation jobs to the Python services through a queue and stores the job state with the design_id/estimate_id and request version from the team's handoff table. gRPC was rejected for the MVP: it adds tooling without solving the main problem, which is long-running jobs.

## Decision 6: Frontend

Requirements: web application for non-expert users; image upload, side-by-side design comparison, estimate breakdown tables, progress views; usability testing.

| Criterion | React | Vue | Angular |
| --- | --- | --- | --- |
| Team familiarity and ecosystem | The largest ecosystem and the most available examples; the team's experience must be confirmed | Smaller ecosystem, easy to adopt | Complete framework, but heavier to learn |
| Component libraries for dashboards, tables and uploads | A very wide choice of table, chart and upload components | Good choice, slightly narrower | Good built-in tools and libraries |
| Learning curve | Moderate | Gentlest | Steepest, with many concepts (modules, dependency injection) |
| Suitability for a rapid prototype | High | High | Lower, because of more setup and boilerplate |

Decision: React with TypeScript, subject to the team's actual experience; Vue is an acceptable alternative. This is the least critical decision and can be changed at low cost.

## Summary of the selected stack

| Layer | Selected | Main alternatives rejected |
| --- | --- | --- |
| Core backend | Java Spring Boot | FastAPI-only, NestJS |
| ML services | Python (FastAPI) | Embedding ML in the Java service |
| Database | PostgreSQL (+ JSONB) | MySQL, MongoDB |
| File storage | S3-compatible object storage | Files in the database |
| AI design | Self-hosted Stable Diffusion + pre-trained structural control, behind an internal API | Hosted API only; training an IDCN-like network |
| Cost estimation | Hybrid: quantity × price baseline + gradient-boosting correction with intervals | Rules only; ML only |
| Service interaction | REST + asynchronous job queue | Synchronous REST only; gRPC |
| Frontend | React + TypeScript | Vue, Angular |
