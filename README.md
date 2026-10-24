# Renovation Platform

## Team:

### 1) Arslan Zheksenbaev Serikovich,

Group: SE-2403,

Phone: +7 776 298 8401,

Email: [usenbaeva1994@gmail.com](mailto:usenbaeva1994@gmail.com)

### 2) Bayazit Abayev Kazymbetovich

Group: SE-2403

Phone: +7 771 033 5826,

Email: [bayazit439@gmail.com](mailto:bayazit439@gmail.com)

### 3) Daryn Maulen Arkabayuly,

Group: SE-2403,

Phone: +7 771 535 00 98,

Email: [darynmaulen12@gmail.com](mailto:darynmaulen12@gmail.com)

## Contents

- [1. Project Proposal](#1-project-proposal)
- [2. Evidence of the relevance](#2-evidence-of-the-relevance)
- [3. Literature review](#3-literature-review)
- [4. Existing system comparison](#4-existing-system-comparison)
- [5. Technology comparison](#5-technology-comparison)
- [6. Requirements specification](#6-requirements-specification)
- [7. Architecture and Diagrams](#7-architecture-and-diagrams)
- [8. UX / prototype](#8-ux--prototype)
- [9. Verification and evaluation plan](#9-verification-and-evaluation-plan)
- [10. Project management and risks](#10-project-management-and-risks)

## 1. Project Proposal

### Topic:

ENG: «The Development of an Intelligent Digital Platform for Renovation Project Management with AI-Based Design and Cost Estimation»

RUS: «Разработка интеллектуальной цифровой платформы для управления ремонтными проектами с использованием ИИ для генерации дизайна и оценки стоимости»

KZ: «Дизайнды генерациялау мен құнын бағалауда ЖИ қолданатын, жөндеу жобаларын басқаруға арналған зияткерлік цифрлық платформаны әзірлеу»

### Supervisor:

Kozhakhmet Zhaksylyk

### Problem statement

Renovation planning today is split across disconnected tools: AI image generators for design ideas, separate spreadsheets or estimators for costs and materials, and separate BIM or tracking tools for progress. Existing research also treats these tasks in isolation: generative design (Zeng et al., 2025; Chen et al., 2025a), cost and resource forecasting (Chen et al., 2025b; Zeng & Gao, 2024), and BIM interoperability and progress tracking (Seydgar et al., 2024; Xue et al., 2022). Studies also show that AI-generated interiors need human oversight and authenticity checks (Liu & Deng, 2025; Alshboul et al., 2026). As a result, homeowners and contractors lack a single workflow that connects an AI-generated design with a cost and material estimate and with project monitoring. It remains unclear how such a workflow can be built and evaluated as one coherent, user-centered and secure system.

### Target users

- Homeowners planning an apartment or house renovation, who need to visualize options, understand the budget and follow progress without technical expertise.

- Renovation contractors and small renovation teams, who need to turn client requirements into estimates, materials lists and schedules, and report progress to clients.

- Secondary: interior designers and project managers who use the platform to speed up concept drafts and estimates.

### Aim

To design and develop a web platform that integrates AI-based design generation, cost and material estimation, and project monitoring into a single renovation workflow for homeowners and contractors, and to evaluate it against a baseline of the current manual process.

### Objectives

1. Collect and verify requirements through 3-5 discussions with homeowners and contractors (or an agreement with a real client).

2. Review the literature (at least 12 sources, including at least 8 scientific ones) and compare 3-5 existing systems against 6-10 criteria.

3. Justify the technology stack by comparing alternatives for at least three key decisions (backend platform, data storage, AI/ML integration approach).

4. Specify functional and non-functional requirements with priorities and acceptance criteria.

5. Design the architecture (system context, use case and component diagrams) and a UX prototype of the key scenarios.

6. Implement the backend core: project and user management, role-based access, secure storage of project data.

7. Implement the design module: AI generation and editing of renovation concepts from user input, with a human review step.

8. Implement the estimation module: cost and material estimates linked to the selected design, with uncertainty ranges.

9. Implement the monitoring module: tasks, stages and progress tracking, with a BIM-related data exchange (e.g. IFC import/export) if feasible within the scope.

10. Evaluate the platform: testing, usability testing with real users, and comparison with the baseline using defined metrics.

### Expected outcomes

- A working MVP of the platform, with design, estimation and monitoring modules connected in one workflow.

- A documented analysis package: literature review, system and technology comparisons, requirements specification, architecture description and diagrams.

- A UX prototype of the key user scenarios.

- An evaluation report with results on estimate accuracy against a reference, time saved compared with the manual process, and user feedback.

- A GitHub/GitLab repository with documentation, tests and a YouTrack task history that shows the development process.

### Scope

#### In scope

- Web application (backend plus user interface) for homeowners and contractors.

- Residential interior renovation (apartments and houses).

- AI design generation via existing models/APIs (integration and adaptation, not training a model from scratch).

- Cost and material estimation based on price data and project parameters (area, room type, work types, finish level).

- Project monitoring: stages, tasks, progress status, basic reporting.

- Authentication, role-based access and protection of project data.

#### Out of scope

- Training new generative AI models from scratch.

- Full BIM authoring or a complete BIM editor; only basic data exchange if feasible.

- Structural, engineering or legal calculations and building-permit approval.

## 2. Evidence of the relevance

Initial qualitative requirements validation | 4 participant questionnaires

### 1. Purpose and project context

The diploma project, “The Development of an Intelligent Digital Platform for Renovation Project Management with AI-Based Design and Cost Estimation,” proposes a connected web workflow for residential renovation. Homeowners can describe rooms, review AI-generated interior concepts, obtain preliminary material and cost estimates, interact with contractors, record agreed terms, and monitor work progress. The target users are apartment and house owners and renovation contractors or small construction teams. This section evaluates whether those proposed capabilities address problems described by potential users.

### 2. Evidence collection method

Four completed written questionnaires were collected: two from construction/renovation professionals and two from homeowners (one apartment owner and one private-house owner). The professionals reported working in Aktobe, Kazakhstan, and completed their questionnaires on 23 October 2026. The homeowner forms state 24 October 2026; this date should be confirmed before submission because it is later than the current drafting date, 23 October. All four forms indicate consent to use responses in anonymized academic reporting. The questionnaires covered existing practices, budgeting, design decisions, contractor coordination, progress reporting, and reactions to the proposed solution. This is purposive, small-sample qualitative requirements discovery, not a representative survey. The study records self-reported experience and opinions; no platform usability test or objective accuracy test has yet been performed.

### 3. Participant profile

P1 - renovation/finishing contractor and team manager; approximately ten years’ experience reported in the answer; typically one or two projects per month. P2 - construction professional specializing in house construction; the profile states 30 years of experience; typically one to four projects per month. H1 - owner of a three-room apartment renovated with a private team. H2 - owner of a roughly 200 m² private house finished using several specialized crews. Participant identifiers are used in this report instead of names or contact details.

### 4. Findings grounded in participant responses

F1. Fragmented and time-consuming estimation (P1, P2, H1, H2). Both professionals reported using small Excel tables and determining quantities from measured areas/volumes and consumption norms. Both described the absence of specialized software and the manual maintenance of spreadsheets as time-consuming. H1 described a rough handwritten estimate and materials requested in stages; H2 had separate calculations from different teams without one consolidated estimate. These accounts support the need for a structured project-wide estimate and material breakdown.

F2. Cost overruns and uncertain quantities (P1, P2, H1, H2). Both professionals cited uneven surfaces, material quality and excess consumption as reasons estimates change. H1 reported a roughly 30–35% increase over her initial renovation budget; this is a single participant’s recollection, not an average or measured market statistic. H2 described additional putty and tile adhesive needed because of uneven preliminary plastering. A preliminary estimate should therefore display assumptions, waste allowances, price dates and a range rather than promise a final fixed cost.

F3. Design ambiguity and change requests (P1, P2, H1, H2). Both professionals noted that customers often lack formal design projects and change their preferences during execution. H1 described relocating sockets and changing wall colours, with rework and additional payments; H2 reported new lighting and finishing ideas leading to rework. Both professionals considered a visible design concept helpful for earlier agreement on intended finishes and for preparing an estimate. This supports AI-generated concepts with explicit homeowner review and approval, not fully automatic design decisions.

F4. Contractor selection, agreements and coordination (P1, P2, H1, H2). Both professionals obtain customers primarily through reputation or referrals and expressed interest in receiving requests through the platform. H1 found it difficult to assess contractor reliability and described verbal agreements without clearly fixed deadlines. H2 described coordination problems between specialist crews and a mix of written and verbal agreements. These findings support contractor profiles, comparable quotations, a versioned record of agreed terms, and visibility of work responsibilities; they do not establish the legal validity of an electronic signature.

F5. Progress reporting and oversight (P1, P2, H1, H2). Both professionals reported frequent on-site oversight and phone calls to clients. H1 visited the renovation almost daily and received receipts and photos through WhatsApp; H2 travelled to the site two or three times per week and received photos, videos and receipts through messaging apps. These experiences support a shared progress view with stage status and supporting evidence.

F6. Trust depends on transparency (P1, P2, H1, H2). Both professionals said they would initially check automated estimates manually and wanted the consumption norms to be visible. Both homeowners likewise conditioned trust on understandable norms or reference standards; H1 additionally wanted verified contractor reviews and photographs of completed projects. Therefore the estimation interface should expose inputs, calculation rules, units and assumptions and allow human checking.

### 5. Evidence-to-requirements traceability

| Finding | Participants | Requirements | Proposed response |
| --- | --- | --- | --- |
| F1: manual/fragmented estimates | P1, P2, H1, H2 | FR-02, FR-06, FR-07 | Measured room inputs; unified itemized estimate; material quantities |
| F2: overruns and variable quantities | P1, P2, H1, H2 | FR-06, FR-07 | Waste/assumptions; price data and preliminary ranges |
| F3: design changes and ambiguity | P1, P2, H1, H2 | FR-03, FR-04, FR-05 | Photo-based concepts and mandatory human approval |
| F4: contractor coordination and agreements | P1, P2, H1, H2 | FR-08, FR-09, FR-10 | Profiles, quotations, recorded agreement versions |
| F5: progress visibility | P1, P2, H1, H2 | MVP step 9; progress requirement needs explicit FR ID | Stage updates and homeowner progress view |
| F6: explainable results | P1, P2, H1, H2 | FR-06, FR-07; NFR-03 | Show norms, inputs, units, assumptions and allow checks |

### 6. Implications and decisions

The interviews support prioritizing a single connected renovation workflow rather than separate design, estimating and messaging tools. The MVP should emphasize: (1) measured room dimensions and finish specifications as estimation inputs; (2) human review of AI design concepts before an estimate is generated; (3) material quantities with units, calculation norms and waste assumptions; (4) a preliminary cost breakdown with uncertainty and a clear distinction between materials and contractor labour quotations; (5) contractor profiles, requests, quotations and recorded agreement versions; and (6) stage-based progress updates with photos or notes. These are proposed design responses to participant findings and still require prototype validation.

Two participants suggested functionality beyond the current MVP: H1 requested protected milestone-based payments or escrow, and H2 requested a schedule coordinating different specialist crews. Escrow/payment processing should be recorded as a future enhancement rather than silently added to the MVP. Detailed cross-contractor scheduling may also be considered for a later iteration after the core stage-tracking workflow is implemented.

### 7. Limitations and research integrity

The sample comprises only four participants, all reported from Aktobe; it cannot represent the entire renovation market in Kazakhstan. Recruitment was purposive and no random selection was used. The questionnaires were written and self-reported; the responses were not independently observed or verified. Participants were introduced to the proposed features before answering evaluation questions. The four professional questionnaires contain notably similar accounts in several areas.

### 8. Conclusion

The four questionnaires provide initial qualitative evidence that residential renovation users face fragmented estimation, material overrun, unclear design expectations, informal coordination, and limited progress visibility. Both user groups described practical reasons to value an integrated platform, especially transparent preliminary estimates, early design review and progress reporting. The evidence supports the relevance of the proposed problem and informs the initial requirements.

## 3. Literature review

Link to the: [Literature review](https://astanait-my.sharepoint.com/:x:/g/personal/240918_astanait_edu_kz/IQCeBkEoLnnXQbaCteyTzQ03AbOKV19lI8t-qzqPmUYo6LU?e=es6I24)

## 4. Existing system comparison

### Selection of systems

No single product covers the full scope of the project, so five publicly available products were chosen. Each covers a part of the scope.

| System | Type | Why it was chosen |
| --- | --- | --- |
| InteriorFlow | AI photo-based redesign | Typical consumer tool: room photo to restyled render |
| Coohom | Interior design and planning | 3D/2D planning, AI layout tools, rendering |
| Planner 5D | Interior design and planning | Popular among non-professionals; planning, AI suggestions, cost estimation and shopping list |
| Houzz Pro | Renovation business management | Contractor-side tool with estimates, scheduling, client portal and contracts |
| Buildertrend | Renovation business management | Construction management with takeoff, budgeting, scheduling and customer portal |

### Comparison criteria

Eight criteria were chosen from the functions of the proposed platform and its target users

| ID | Criterion | Why it matters for this project |
| --- | --- | --- |
| C1 | AI design from the user's room photo or plan | Core of the design module |
| C2 | Editing of the generated design | Human review and modification |
| C3 | Cost estimate | Core of the estimation module |
| C4 | Estimate linked to the visual design | Integration claim of the project |
| C5 | Price ranges / uncertainty in the estimate | Objective in the proposal |
| C6 | Project tracking (schedule, tasks, daily logs) | Core of the monitoring module |
| C7 | Client–contractor collaboration (portal, proposals, contracts) | Both target user groups |
| C8 | Target audience and entry price | Fit for homeowners and small teams |

### Comparison

#### Design features

| System | C1 AI design from photo/plan | C2 Editing of the design |
| --- | --- | --- |
| Interior AI | Yes. Photo upload -&gt; photorealistic redesign, 40+ styles, virtual staging of empty rooms | Partial. Object replacement by prompt, before/after view, history |
| Coohom | Partial. AI layout, auto-drafting, AI decorator; works from 3D/2D plans, not photo restyling | Yes. Drag-and-drop 3D editor, material and lighting changes |
| Planner 5D | Partial. AI layout, colour and furniture suggestions, plan recognition; AI Design Generator only in a higher plan | Yes. Drag-and-drop 3D/2D editing, adjustable materials and colours |
| Houzz Pro | None of the sources reviewed states the feature. AI is documented for estimates and schedules; visualisation is 2D/3D and mood boards | Partial. 3D floor plans, selections |
| Buildertrend | None of the sources reviewed states the feature | None of the sources reviewed states the feature |

#### Cost features

| System | C3 Cost estimate | C4 Estimate linked to the design | C5 Ranges / uncertainty |
| --- | --- | --- | --- |
| Interior AI | No estimate. "Shop the look" product search only | None of the sources reviewed states the feature | None of the sources reviewed states the feature |
| Coohom | Partial. Elite plan: kitchen and bath BOM and quotation | Partial. BOM generated from the kitchen/bath design (Elite) | None of the sources reviewed states the feature |
| Planner 5D | Partial. Cost estimation and shopping list | Partial. Estimate based on items placed in the project | None of the sources reviewed states the feature |
| Houzz Pro | Yes. AI-assisted estimates and proposals, labour and materials from local data | None of the sources reviewed states the feature. Estimates come from prompts, templates and a catalogue | None of the sources reviewed states the feature |
| Buildertrend | Yes. Estimating, takeoff, budgeting | No link to AI design. Takeoff from uploaded plans | None of the sources reviewed states the feature |

#### Management and business features

| System | C6 Project tracking | C7 Client–contractor collaboration | C8 Audience and entry price |
| --- | --- | --- | --- |
| Interior AI | None of the sources reviewed states the feature | None of the sources reviewed states the feature | Homeowners, designers, real-estate staff; from about \$29/month billed yearly (third-party listing) |
| Coohom | None of the sources reviewed states the feature | Partial. Team and project sharing | Designers, retailers, manufacturers, homeowners; limited free tier; one listing: Elite \$699/year |
| Planner 5D | None of the sources reviewed states the feature | Partial. Sharing and remote collaboration | Amateurs and professionals; free plan plus paid plans |
| Houzz Pro | Yes. Scheduling, tasks, daily logs, AI schedule from estimate | Yes. Client portal, proposals, e-signature contracts, invoices | Builders, remodelers, designers; about \$85–\$249/month depending on source and plan |
| Buildertrend | Yes. Scheduling with delay alerts, daily logs, change orders | Yes. Customer portal, selections, change orders, subcontractor portal | Builders and remodelers; from about \$499/month (third-party listing) |

### Summary: what each system covers

| System | Design (C1–C2) | Estimate (C3–C5) | Tracking & Collab (C6–C7) | Main gap for our project |
| --- | --- | --- | --- | --- |
| Interior AI | Strong | None | None | No cost, no project management |
| Coohom | Medium–strong | Partial | Partial | Not photo-based; estimate only for kitchen/bath; no tracking |
| Planner 5D | Medium–strong | Partial | Partial | AI generation limited to a higher plan; no tracking |
| Houzz Pro | Limited | Strong | Strong | No AI design from a photo; business price |
| Buildertrend | None | Strong | Strong | No design generation; highest entry price |
| Proposed platform | AI from photo + human review | Estimate from approved design, with ranges | Stage & task tracking for homeowner & contractor | - |

### Why the proposed solution is needed and whether claims about existing systems are supported by evidence

Market Split. Existing tools are divided: design software lacks contractor workflows, while construction management platforms cannot generate AI designs from room photos.

No Cost Uncertainty. None of the evaluated systems provide price ranges or confidence intervals, giving only a single fixed estimate or no budget calculation at all.

Weak Design-to-Cost Link. Automating estimates from visual concepts is a major gap; current tools only generate bills of materials for specific sub-spaces or from manually placed 3D objects.

Audience & Price Mismatch. Enterprise management software uses expensive business subscriptions, whereas consumer design tools stop before budgeting and execution, leaving homeowners and small crews underserved.

Need for Expert Review. Fully automated AI output often faces quality limits, requiring professional designer refinement before finalizing project plans.

## 5. Technology comparison

### Decision 1: Backend platform

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

### Decision 2: Data storage

Requirements: structured relational data (users, rooms, designs, estimates, versions, contracts); consistency between the approved design, the estimate and the contract; large binary files (photos, renders).

| Criterion | PostgreSQL | MySQL | MongoDB |
| --- | --- | --- | --- |
| Relational integrity and transactions (room -&gt; approved design and specification -&gt; material estimate -&gt; renovation request with fixed labour amount -&gt; accepted contractor response -&gt; contract) | Full ACID transactions and strict constraints keep the chain consistent | Also reliable, with slightly fewer advanced features | Supports transactions, but the model is document-oriented, so referential integrity across the chain depends on application code |
| Flexible fields (finish specifications, AI job parameters) | JSONB stores semi-structured data inside the relational model, with indexing | JSON support exists but is more limited | Natural fit, since documents are flexible by design |
| Fit with Spring Data/JPA and migrations | Well supported | Well supported | Supported, but the relational chain of the project does not map naturally to documents |
| Reports and price history | Rich SQL: window functions, aggregates | Adequate | Aggregation is possible but less convenient for relational reports |

Decision: PostgreSQL for all structured data, with JSONB for flexible specifications. It covers both the strict relational chain and the semi-structured fields in one system, which MySQL (weaker flexible fields) and MongoDB (weaker integrity) each cover only partly. Images and generated renders go to S3-compatible object storage (e.g. MinIO in development); the database keeps only references, metadata and the version of the request that produced each file. Storing large files inside the relational database was rejected because it makes backups and queries slower.

### Decision 3: AI design generation approach

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

Risk: keeping the structure while generating furniture is the known weak point of ControlNet-type methods, so the verification plan must measure structure preservation and include a fallback (sketch-based generation: unfurnished room image -&gt; sketch -&gt; designer edit -&gt; render).

### Decision 4: Cost and material estimation method

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

### Decision 5: Component interaction

Requirements: the core backend calls the design and cost services; image generation and model inference are slow compared with ordinary requests; results must be traceable to a request version.

| Criterion | A. Synchronous REST only | B. REST + asynchronous job queue (RabbitMQ or Redis) with status polling | C. gRPC between services |
| --- | --- | --- | --- |
| Handling of long generation jobs | A request may time out or block while an image is generated | The request returns immediately; the job runs in the background and the client polls its status | Supports streaming, but a long call still holds a connection unless combined with a queue |
| Simplicity for a small team | Simplest to build and debug | One more component (the queue), but a widely known pattern | Needs schema definitions and extra tooling |
| Traceability (job id, request version, result) | Possible, but there is no job object unless added | A job record with state (queued, running, done, failed) is natural, and it links to the design/estimate version in the handoff table | Possible, but not built in |
| Compatibility with Spring Boot and Python services | Fully compatible | Fully compatible | Compatible, with additional setup on both sides |

Decision: Option B. The client and the core backend communicate through REST/JSON. The core submits generation and estimation jobs to the Python services through a queue and stores the job state with the design_id/estimate_id and request version from the team's handoff table. gRPC was rejected for the MVP: it adds tooling without solving the main problem, which is long-running jobs.

### Decision 6: Frontend

Requirements: web application for non-expert users; image upload, side-by-side design comparison, estimate breakdown tables, progress views; usability testing.

| Criterion | React | Vue | Angular |
| --- | --- | --- | --- |
| Team familiarity and ecosystem | The largest ecosystem and the most available examples; the team's experience must be confirmed | Smaller ecosystem, easy to adopt | Complete framework, but heavier to learn |
| Component libraries for dashboards, tables and uploads | A very wide choice of table, chart and upload components | Good choice, slightly narrower | Good built-in tools and libraries |
| Learning curve | Moderate | Gentlest | Steepest, with many concepts (modules, dependency injection) |
| Suitability for a rapid prototype | High | High | Lower, because of more setup and boilerplate |

Decision: React with TypeScript, subject to the team's actual experience; Vue is an acceptable alternative. This is the least critical decision and can be changed at low cost.

### Summary of the selected stack

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

## 6. Requirements specification

### Purpose and scope

The proposed system is an intelligent web platform for residential renovation project management. It connects homeowners and renovation contractors through a marketplace and integrates AI-based interior design generation, cost and material estimation, electronic contract records, and project progress monitoring.

The platform supports a connected workflow: a homeowner creates a renovation project, provides room information, reviews an AI-generated design, obtains a preliminary estimate, selects a contractor, confirms the agreed scope, and monitors renovation progress.

These requirements represent an initial baseline derived from the project proposal. They must be validated through 3–5 discussions with potential users or a substantive agreement with an actual client. They do not represent confirmed interview findings.

### User roles

| Role | Main responsibilities |
| --- | --- |
| Homeowner | Create renovation projects, provide room information, review designs and estimates, select a contractor, confirm agreements, and monitor progress. |
| Contractor | Maintain a service profile, review renovation requests and respond to renovation requests with homeowner-defined fixed labour amounts, submit quotations, confirm agreements, and update assigned project stages. |
| Platform administrator | Manage accounts and marketplace records, assign project access, and maintain reference data within granted permissions. |

### Requirement priorities

- Must: Required for the MVP and demonstration of the complete renovation workflow.

- Should: Important functionality that may follow the core implementation.

- Could: Optional functionality implemented if time and resources permit.

### Functional requirements

| ID | Requirement | Priority | Acceptance criteria |
| --- | --- | --- | --- |
| FR-01 | The system should support registration, authentication, and role-based access. | Must | Homeowners and contractors can register and sign in using valid credentials. Invalid credentials are rejected. Administrator privileges cannot be obtained through public registration. Access to protected operations is checked on the server. |
| FR-02 | The system should allow homeowners to create and manage renovation projects and rooms. | Must | A homeowner can create a project and add rooms with a room type, dimensions, renovation scope, and finish level. Missing mandatory values and non-positive dimensions are rejected. Saved information remains available after signing out and signing in again. |
| FR-03 | The system should support room photo uploads. | Must | A user can upload a JPEG or PNG image and associate it with a room. Unsupported or oversized files are rejected with an explanatory message. Uploaded photos are accessible only to authorized project participants. |
| FR-04 | The system should generate interior design concepts using an existing AI model or service. | Must | For a valid room photo, selected style, and user constraints, the system creates a generation request and displays its processing status. A successful request produces at least one viewable concept linked to the correct room. Failed requests display an error and allow a retry. |
| FR-05 | The system should require human review before a generated design is used for estimation. | Must | The user can view the original photo and generated concept, accept or reject the concept, and confirm or edit its finish specification. Only a confirmed design and specification version can be submitted for estimation. |
| FR-06 | The system should calculate material quantities from confirmed room measurements and renovation scope. | Must | For a reference room with known dimensions, calculated quantities match independently prepared calculations within the documented rounding tolerance. The output states units, calculation assumptions, and any waste allowance. Quantities are not derived solely from a generated image. |
| FR-07 | The system shall estimate renovation material costs using confirmed measurements, specifications, documented price data, and an ML component. | Must | The estimate displays material quantities, units, cost breakdown, total in KZT, an estimated range, and price-data date. The homeowner-defined contractor labour payment is excluded. Each estimate references its input versions. |
| FR-08 | The system should provide contractor profiles and renovation requests. | Must | A contractor can maintain a profile containing service categories, rating,service area, and a description. A homeowner can publish a renovation request containing the agreed project information. Other homeowners cannot access the request’s private photos, estimates, or contract records. |
| FR-09 | The system shall allow homeowners to publish renovation requests with a fixed labour amount, contractors to respond, and homeowners to select an executor. | Must | The homeowner specifies the work scope and fixed labour amount separately from material costs. Contractors can respond with availability and comments without changing that amount. The homeowner can select one contractor; conflicting selections are prevented. |
| FR-10 | The system should maintain an electronic record of the agreed renovation contract. | Must | A contract record references the homeowner, contractor, accepted contractor response, selected design, estimate, work scope, and agreed dates. Confirmation by each party is recorded with a timestamp. Changes after confirmation create a new version requiring renewed confirmation. |
| FR-12 | The system should provide a downloadable project summary. | Could | An authorized participant can download a summary containing the selected design, estimate breakdown, accepted contract response, and current progress. Exported values match the corresponding stored project versions. |
| FR-13 | The system should maintain traceability between designs, estimates, quotations, and contract records. | Could | Each estimate identifies the design, specification, measurement, price-data, and model versions used. Changing an input does not overwrite a previously accepted estimate. A quotation or contract based on an older version remains identifiable and requires explicit reconfirmation before replacement. |
| FR-14 | The system shall support renovation stages, tasks, and progress monitoring. | Must | Authorized project participants can manage stages and tasks. The assigned contractor can update task statuses, and the homeowner can view progress. Updates record their author and timestamp. Unrelated users cannot modify the project. |

### Non-functional requirements

| ID | Requirement | Priority | Acceptance criteria |
| --- | --- | --- | --- |
| NFR-01 | The system should provide responsive interaction under the documented demonstration workload. | Must | With 10 concurrent users on the documented test environment, at least 95% of ordinary project, profile, and task requests complete within 2 seconds. AI generation and file transfer are measured separately. |
| NFR-02 | The system should handle AI-service failures without losing project data. | Must | When an AI request times out or fails, the project and previous successful results remain available. The request receives a visible failure status. Retrying does not create duplicate accepted designs, estimates, or contracts. |
| NFR-03 | The interface should be usable by users without technical expertise. | Must | In a usability session with at least five representative users, at least four complete project creation, design review, and estimate viewing without moderator intervention. Completion times, errors, and participant feedback are recorded. |
| NFR-04 | The system should preserve data consistency across its modules. | Must | An interrupted operation does not leave a contract without its accepted quotation or an estimate without its input references. Saving repeated confirmation requests does not create duplicate confirmations. |

### AI and ML acceptance criteria

#### Design generation

Technical generation success and visual design quality should be evaluated separately. Returning an image alone does not demonstrate that the design meets the user’s requirements.

For the initial evaluation:

- Prepare at least 20 room-and-style test scenarios with documented constraints.

- At least 90% of valid requests should return a viewable result within the configured timeout on the documented environment.

- Two reviewers independently assess style consistency, visual coherence, and preservation of required room features using a defined five-point rubric.

- The proposed quality target is a mean score of at least 3.5 out of 5 for each dimension.

- Failed generations and reviewer disagreements are included in the evaluation report.

Generated images should be presented as renovation concepts requiring user review.

#### Cost estimation

The estimation model should be evaluated using renovation records excluded from model training and model selection. Records belonging to the same renovation project should remain in the same data partition to reduce information leakage.

Acceptance requires:

- A documented dataset containing input features, target costs, units, price dates, and preprocessing rules.

- Separate training, validation, and test partitions.

- Comparison against a simple baseline, such as average renovation cost per square metre by finish level.

- Reporting of Mean Absolute Error in KZT and Weighted Absolute Percentage Error on the held-out test set.

- A proposed target of WAPE no greater than 20% and lower MAE than the baseline on the same test cases.

- Evaluation of the reported cost ranges against actual costs, including their observed coverage and average width.

The 20% threshold is an initial research target. Its feasibility must be reviewed after examining the dataset. Any revision must be documented before final testing.

#### Material quantities

Material quantity calculations should be checked separately from ML cost predictions.

For at least 10 reference cases, covering supported room shapes and work types, calculated quantities should match independently prepared calculations within the declared rounding tolerance. Each case should specify dimensions, deductions, units, and waste assumptions.

### MVP acceptance scenario

The MVP should demonstrate the following connected scenario:

1. A homeowner registers and creates a renovation project.

2. The homeowner adds a room, measurements, photos, and renovation preferences.

3. The platform generates an interior design concept.

4. The homeowner reviews the concept and confirms its finish specification.

5. The platform produces material quantities and a preliminary cost estimate.

6. The homeowner publishes a renovation request.

7. The homeowner publishes a renovation request with a fixed labour amount. A contractor responds to these conditions, and the homeowner selects the contractor.

8. Both parties confirm the corresponding electronic contract record.

9. The contractor updates a renovation stage, and the homeowner views the progress.

10. The contractor submits completed work for acceptance. The homeowner accepts the work or requests corrections. After acceptance, the homeowner submits a rating, and the contractor’s average rating is recalculated.

### Requirements validation and traceability

Each mandatory requirement should be linked to a YouTrack task, a responsible team member, and at least one verification activity. A requirement may be marked as completed only when its acceptance criteria have been checked and supporting evidence has been recorded.

User discussions should validate the proposed workflow, required project inputs, contractor response information and homeowner-defined fixed labour terms, agreement confirmation process, and progress reporting needs. Changes resulting from these discussions should be recorded in the requirements revision history.

For the initial submission, acceptance means that the requirements are documented, prioritized, traceable, and reviewable. Implementation acceptance will be assessed during later project stages.

## 7. Architecture and Diagrams

![System Context Diagram](https://github.com/ArslanZheksenbaev/renovation-platform/blob/main/docs/diagrams/01-system-context.png?raw=true)

*Figure 1.1*

### 1.1. System Context Diagram

The diagram (figure 1.1) defines the platform’s boundary and its interactions with three user roles: homeowner, contractor, and administrator. Homeowners provide room photos, measurements, and a fixed labour amount, while contractors respond to requests and report progress. The platform connects AI design, cost estimation, agreements, and renovation monitoring. Contractor labour payment is separate from the cost estimate.

![Use Case Diagram](https://github.com/ArslanZheksenbaev/renovation-platform/blob/main/docs/diagrams/02-use-case.png?raw=true)

*Figure 1.2*

### 1.2. Use Case Diagram

The diagram (figure 1.2) presents the main functions available to each role. Homeowners create projects, approve designs and specifications, view estimates, select contractors, monitor progress, and rate completed work. Contractors manage their profiles, respond to requests, and update renovation tasks. Both parties confirm the agreement, while administrators manage users and marketplace records.

![Component Diagram](https://github.com/ArslanZheksenbaev/renovation-platform/blob/main/docs/diagrams/03-component.png?raw=true)

*Figure 1.3*

### 1.3. Component Diagram

The diagram shows the proposed internal architecture. A React interface communicates with the Spring Boot backend, which manages business processes and stores structured data in PostgreSQL. A background queue distributes tasks to separate Python services for design generation and cost estimation. Images are stored in private object storage, while versioned inputs and results support traceability between modules.

## 8. UX / prototype

A high-fidelity mobile prototype was prepared in Figma to illustrate the proposed user experience of the renovation platform. It focuses on two primary roles: homeowners and contractors. The prototype supports discussion of navigation, screen structure, and key interactions before full implementation.

Prototype link: [Prototype](https://www.figma.com/make/ShngS37t4GbtCX3zjj9Uba/High-Fidelity-Mobile-Prototype?fullscreen=1&t=ZdXv8rB1sZVHp6sx-1&code-node-id=0-6)

### Main User Scenarios

The intended homeowner workflow begins with project creation, entry of room measurements, photo upload, and selection of design preferences. The homeowner reviews AI-generated concepts, confirms the finish specification, and views the material-cost estimate. A separate fixed labour amount is then entered when publishing a renovation request.

The subsequent workflow covers reviewing contractor responses, selecting an executor, confirming the agreement, and monitoring renovation stages. After accepting completed work, the homeowner can submit a rating.

The contractor experience focuses on maintaining a profile, reviewing renovation requests, responding to the stated scope and fixed labour amount, confirming agreements, and updating task statuses.

### Interface Design Principles

The mobile interface is designed around short forms, readable project cards, clear status indicators, and prominent primary actions. Material estimates and contractor labour payments are presented separately to prevent confusion. AI-generated images are treated as concepts requiring homeowner review before estimation.

The prototype will be used in usability sessions to assess task completion, navigation clarity, and user understanding of the renovation workflow. Findings will inform interface revisions. Prototype interactions demonstrate proposed behaviour; they do not establish the functionality or accuracy of the backend and AI modules.

## 9. Verification and evaluation plan

| Area and requirements | Verification or evaluation method | Data and conditions | Acceptance target and evidence |
| --- | --- | --- | --- |
| Authentication and authorization - FR-01 | Test valid and invalid credentials, role restrictions, and cross-project access. | Separate homeowner, contractor, and administrator accounts; at least two private projects. | Valid operations succeed; unauthorized access and privilege escalation are rejected. Record test results. |
| Project creation and uploads - FR-02–03 | Submit valid project data, missing fields, invalid dimensions, supported images, and files exceeding the configured limit. | Reference room data; JPEG/PNG files; unsupported and oversized files. | Valid records persist after a new login. Invalid inputs are rejected with clear messages. Record the upload limit before testing. |
| AI generation and approval - FR-04–05 | Test generation states, correct room association, failure handling, and approval before estimation. | Valid photographs, style requests, constraints, and simulated service failures. | Successful results reference the correct room and request version. Unapproved specifications cannot be used for estimation. |
| Design quality | Compare the proposed pipeline with an unconditioned generation baseline. Two reviewers independently assess style consistency, structural preservation, and visual coherence. | At least 20 room-and-style scenarios; identical inputs and comparable generation settings; predefined five-point rubric and timeout. | Proposed targets: at least 90% technical success and a mean score of at least 3.5/5 in each quality dimension. Report failures and reviewer disagreements. |
| Material quantities - FR-06 | Compare system quantities with independently prepared manual calculations. | At least 10 cases with known dimensions, openings, materials, waste allowances, and rounding rules. | Quantities match reference calculations within a tolerance fixed before testing. Save calculations and differences. |
| Material-cost accuracy - FR-07 | Compare ML predictions and the deterministic quantity × unit-price baseline against independent reference costs. Calculate MAE in KZT and WAPE. | Held-out renovation records or expert-verified material estimates; project-separated training, validation, and test sets. Labour payment excluded. | Proposed targets: WAPE ≤20% and lower MAE than the deterministic baseline on identical test cases. Report dataset size, reference quality, and limitations. |
| Cost ranges - FR-07 | Measure the proportion of reference costs inside predicted ranges and their average width. | Same held-out cases; nominal coverage selected before final testing. | Report observed coverage against the selected nominal level and average interval width. Explain undercoverage or excessively wide ranges. |
| Marketplace and fixed labour amount - FR-08–09 | Publish a request, submit contractor responses, and select an executor. Attempt conflicting selections. | One homeowner and at least two contractor accounts; fixed labour amount stored separately from the material estimate. | Responses preserve the homeowner’s amount. Only one contractor is selected. Labour payment is not included in the material estimate. |
| Agreements and traceability - FR-10, FR-13 | Confirm the same agreement as both parties, change its terms, and repeat confirmation requests. | Versioned designs, specifications, estimates, contractor responses, and agreements. | Confirmations record matching versions and timestamps. Changed terms require renewed confirmation. Previous accepted records remain accessible; duplicate confirmations are prevented. |
| Renovation monitoring - FR-11 | Create stages and tasks, update statuses, and inspect progress from the homeowner account. | Assigned contractor, project homeowner, and unrelated user. | Authorized updates persist with author and timestamp. The homeowner sees changes; unrelated users cannot edit. |
| Project summary - FR-12, if implemented | Export a project summary and compare it with stored records. | A project containing a selected design, estimate, agreement, and progress updates. | Exported information matches the referenced project versions. |
| Completion and rating - FR-14 | Submit completed work, request corrections, accept completion, and submit ratings. Attempt premature, duplicate, and self-ratings. | Completed and incomplete projects; reference ratings such as 5, 4, and 3. | Ratings follow homeowner acceptance. Invalid ratings are rejected. The reference scores produce an average of 4.0 and a count of 3. |
| Performance - NFR-01 | Run a defined workload and measure response-time percentiles and errors. | 10 concurrent users; documented hardware, software, database size, and request mix. AI generation and uploads measured separately. | At least 95% of ordinary project, profile, and task requests complete within 2 seconds. Save workload configuration and results. |
| Reliability and consistency - NFR-02, NFR-04 | Simulate AI timeouts, repeated submissions, duplicate result delivery, and interrupted operations. | Existing projects with saved results and versioned agreement records. | Existing data remain accessible. Failures have visible statuses. Retries do not create duplicate accepted records or broken references. |
| Mobile usability - NFR-03 | Observe users completing project creation, design review, and estimate viewing without moderator intervention. Evaluate contractor tasks separately. | At least five representative homeowners using the mobile interface; additional contractor participants for request and progress tasks. | At least four of five homeowners complete the core tasks independently. Record time, errors, assistance, and feedback. Report contractor results separately. |
| Time savings | Compare equivalent material-planning tasks using a spreadsheet and the platform. | Identical measurements, specifications, and price data; alternate task order where practical. | Report completion time and percentage change, including unsuccessful tasks. Separate active user time from processing time. |
| End-to-end integration | Execute the full workflow: project -&gt; approved design -&gt; material estimate -&gt; fixed labour request -&gt; contractor selection -&gt; agreement -&gt; progress -&gt; acceptance -&gt; rating. | Connected homeowner and contractor accounts operating on the same project. | The workflow completes with correct permissions, consistent amounts and versions, persistent records, and a correctly updated rating. |

## 10. Project management and risks

### 1. Management approach and objectives

The project is managed as an iterative, evidence-driven software engineering effort. Requirements, architecture, user experience, implementation, and evaluation are developed in reviewable increments rather than delivered as a single final submission. The first pre-defense establishes the documented analysis and design baseline; later iterations will implement and validate the minimum viable product (MVP). The team uses GitHub for version control and peer review, YouTrack for task ownership and progress tracking, and Figma for UX prototyping. Supervisor feedback is recorded as actionable revisions. This approach supports individual accountability, early identification of integration issues, and traceability from requirements to delivered evidence.

The project targets an integrated residential renovation workflow: homeowner project and room creation; room-photo upload; AI-generated design concepts and human approval; transparent material quantities and preliminary material-cost estimation; homeowner-defined fixed contractor labour amount; contractor responses and selection; electronic agreement records; renovation stages and progress updates; and completion acceptance and contractor ratings. AI output is a design concept, not a construction-certified plan. Material estimates exclude the separate contractor labour payment. The platform does not process payments, train a generative model from scratch, or provide a full BIM editor.

### 2. Team structure and responsibility allocation

#### Arslan Zheksenbaev

Primary responsibility: Machine Learning and Cost Estimation Engineer

Principal deliverables: Quantity rules; documented price inputs; deterministic baseline; ML correction and uncertainty ranges; cost-related tests; evaluation metrics; project planning and risk register.

Review and coordination: Align estimate inputs and versions with the approved design and backend API; coordinate cross-module evaluation.

#### Bayazit Abayev

Primary responsibility: Backend and Marketplace Developer

Principal deliverables: Spring Boot APIs; PostgreSQL data model; authentication and role-based access; project/room records; contractor profiles and responses; agreements; progress and rating logic; architecture diagrams.

Review and coordination: Define API contracts, access permissions, persistence, and service integration.

#### Daryn Maulen

Primary responsibility: AI Design Generation Engineer

Principal deliverables: room-photo design pipeline using existing pretrained models; Figma mobile prototype; generation status and failure handling; design review and specification handoff; AI design evaluation.

Review and coordination: Align UX states and approved design versions with backend and estimation inputs.

#### All three members

Primary responsibility: Integration, testing, documentation and defense

Principal deliverables: Cross-module acceptance scenario; peer review; reproducible evidence; issue updates and presentation.

Review and coordination: Each member reviews another member’s changes and explains their own contribution.

Responsibilities identify accountable owners, not isolated workstreams. Changes to shared APIs, data schemas, user journeys, and acceptance criteria require coordination among affected members. The supervisor reviews major scope and architectural decisions.

### 3. Tools, repository and traceability

GitHub repository: [Repository](https://github.com/ArslanZheksenbaev/renovation-platform)

YouTrack project: [YouTrack](https://renovation-platform.youtrack.cloud/projects/DIP)

Figma: [Prototype](https://www.figma.com/make/ShngS37t4GbtCX3zjj9Uba/High-Fidelity-Mobile-Prototype?fullscreen=1&t=ZdXv8rB1sZVHp6sx-1&code-node-id=0-6)

Repository organization: backend/, ai-design-service/, cost-estimation-service/,docs/, diagrams/, prototype/, and config/,with tests maintained beside the relevant code or in a clearly documented test directory.

Each meaningful work item is tracked as a YouTrack issue with an assignee, priority, expected deliverable, deadline, and acceptance criteria. Its issue ID is included in the working branch and commit/PR title (for example, `DIP-23-database-schema` and `DIP-23: Add database schema`). A teammate reviews the pull request before merging into `main`. The issue links to the PR and relevant evidence and is closed only when acceptance criteria have been checked. Documentation and prototype changes follow the same workflow as code. Every contributor uses an individual Git account and identifiable commit author. Credentials, API keys, unredacted interview questionnaires, phone numbers, and private room photos must not be committed. The supervisor and committee should receive appropriate repository access.

The repository README must provide the project description, target users, scope, team roles, technologies, development status, documentation and YouTrack links, and-when runnable components exist-setup and test commands. The team will create the immutable Git tag `pre-defense-1` for the exact first-submission revision, with later tags `pre-defense-2` and `final-pre-defense`. Tags are created only after checking the corresponding repository state; this document does not claim that a tag already exists.

### 4. Work breakdown and milestone plan

| Milestone | Deliverables and exit evidence | Owner(s) | Status at planning baseline |
| --- | --- | --- | --- |
| M1 - Initial validation and scope | Project proposal; four anonymized user questionnaires; evidence-to-requirements mapping; documented MVP boundaries | All; Arslan coordinates evidence | Documented in the supplied diploma draft. Date inconsistencies in two questionnaire headers require confirmation. |
| M2 - First pre-defense (24 Oct 2026) | Literature and existing-system review; technology alternatives; prioritized requirements and acceptance criteria; context/use-case/component diagrams; Figma prototype; verification plan; GitHub/YouTrack traceability; risk register | All; deliverables assigned by section | Documentation and prototype described in diploma v0.3. Repository access, final links, review history, and submission tag require live verification. |
| M3 - Foundation and interface contracts | Database schema and migrations; role-based authentication; project/room APIs; versioned data contracts; runnable development environment | Bayazit; Arslan and Daryn review | Planned; completion date to be agreed in YouTrack. |
| M4 - AI design and cost services | Photo/design workflow; human approval; quantity calculations; material-cost baseline; ML experiment; uncertainty output | Daryn (design); Arslan (estimation); Bayazit (integration) | Planned; dependent on test data, model availability, and service interfaces. |
| M5 - Marketplace and progress integration | Requests with fixed labour amount; contractor responses and selection; agreement versions; stage/task updates; completion acceptance; rating | Bayazit; all integrate and test | Planned; dependent on M3 and approved estimate/design data. |
| M6 -Verification and final delivery | End-to-end demonstration; security and performance checks; 20 AI scenarios; 10 quantity cases; held-out cost evaluation; five-user usability study; documented results and limitations | All; each module owner produces evidence | Planned; dates to be agreed with supervisor. |

M3–M6 are sequencing milestones, not claims that implementation has already been completed. Their calendar dates must be entered into YouTrack after the supervisor confirms the next checkpoint. At every milestone, the team records the reviewed commit, open issues, known limitations, and next actions.

### 5. Dependencies and critical integration path

The main dependency chain is validated requirements → shared data model and API contracts → room measurements and photo upload → AI design generation → homeowner approval of design and finish specification → material quantities and preliminary material-cost estimate → fixed-labour renovation request → contractor selection → versioned agreement → progress updates → acceptance and rating. The backend data model and access controls are prerequisites for reliable integration; the estimate must refer to confirmed measurements and specification versions rather than infer quantities from generated images alone. Material costs and labour payment remain distinct across the interface, database and reports. Long-running AI requests require explicit job states and retry handling. The team will test intermediate service contracts before attempting the full demonstration so that failures can be isolated to one component.

A delay in the approved-design-to-estimate handoff or the shared schema can block several downstream functions; therefore, these interfaces receive early review priority.

### 6. Monitoring, quality gates and change control

The team will maintain a prioritized YouTrack backlog and hold short coordination check-ins at least weekly during implementation, with additional integration reviews before milestones. Each check-in records completed work, blocked tasks, decisions, responsible persons and the next review date. High-priority blockers are raised to the full team immediately and to the supervisor when they affect scope, evaluation feasibility or a submission deadline.

A task is considered Done only when (1) its deliverable is committed to the repository or linked as an approved external artifact, (2) its stated acceptance criteria have been checked, (3) another team member has reviewed the change where applicable, (4) supporting evidence or test results are linked, and (5) documentation and dependent tasks have been updated. The team monitors issue status, overdue work, unresolved blockers, PR review time, test failures and completion of milestone deliverables. These indicators are used to support decisions, not to inflate commit or ticket counts.

A requirement or architectural change is proposed in YouTrack with a reason, affected FR/NFR identifiers, impact on schedule and dependencies, and proposed tests. Affected owners review the change before it is accepted. Baseline changes are reflected in the requirements document, diagrams, UX prototype and verification plan. Supervisor comments are logged with the resulting decision and corresponding revision; unreceived feedback is never reported as completed review.

### 7. Risk assessment and mitigation register

Risks are evaluated qualitatively using Likelihood (L) and Impact (I) on a 1–3 scale (1 = low, 2 = medium, 3 = high). Risk score = L × I. Scores 1–2 are low, 3–4 medium and 6–9 high. These are planning judgments, not measured probabilities. The responsible owner reviews the score and mitigation at each milestone.

| ID | Risk and consequence | L | I | Score | Mitigation / contingency | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| R1 | Limited or unsuitable renovation cost data weakens ML accuracy and uncertainty estimates | 3 | 3 | 9 High | Define a documented price/quantity baseline first; source dated price data; split evaluation by project; report dataset limitations and MAE/WAPE transparently; retain deterministic estimates if ML underperforms | Arslan |
| R2 | AI-generated designs distort room geometry or fail to preserve required features | 3 | 3 | 9 High | Use pretrained structural controls, human approval and a constrained prompt/input workflow; evaluate at least 20 scenarios; offer retry or fallback generation and reject unsuitable outputs | Daryn |
| R3 | Incompatible interfaces or versions break the design → estimate → agreement chain | 3 | 3 | 9 High | Agree on shared IDs, schemas and versioned API contracts early; use integration tests and sample payloads; prevent estimates from using unapproved designs | Bayazit, Arslan, Daryn |
| R4 | Limited three-person capacity causes schedule slippage or excessive scope | 3 | 3 | 9 High | Prioritize mandatory nine-step workflow, assign one accountable owner per task, review blockers weekly, defer escrow/full BIM and other enhancements | All; Arslan coordinates |
| R5 | Room photos, user data or contract records are exposed through incorrect access control | 2 | 3 | 6 High | Server-side RBAC, private object storage, project-level authorization checks, secret management, negative access tests and data minimization | Bayazit |
| R6 | GPU/API availability, cost or latency prevents dependable design generation | 3 | 2 | 6 High | Prototype on available infrastructure early; define timeouts, queued jobs, status polling and retry; maintain replaceable provider fallback; separate generation time from ordinary API latency | Daryn, Bayazit |
| R7 | Users distrust automated quantities and estimates or misunderstand preliminary prices | 2 | 3 | 6 High | Show units, assumptions, consumption norms, price dates, ranges and labour separation; obtain feedback from representative homeowners and contractors | Arslan, Daryn |
| R8 | Marketplace and agreement workflow contains conflicting selections or inconsistent contract versions | 2 | 3 | 6 High | Transactional updates, one selected contractor per request, immutable agreement versions, confirmation timestamps, repeat-request/idempotency tests | Bayazit |
| R9 | Small qualitative interview sample and incomplete validation lead to overgeneralized claims | 2 | 2 | 4 Medium | Label four interviews as exploratory, preserve anonymized evidence, correct source-date inconsistencies, test the prototype with at least five representative users and report limitations | All |
| R10 | Unreviewed commits, missing YouTrack links or incomplete supervisor feedback weaken assessment traceability | 2 | 3 | 6 High | Require issue-linked branches/PRs and peer reviews; audit README, diagrams, prototype links and access; record supervisor feedback; tag the exact pre-defense revision | All |
| R11 | Inconsistent material prices or missing waste allowances make estimates misleading | 3 | 2 | 6 High | Record price dates, sources, units, waste factors and assumptions; verify at least ten reference quantity cases and allow controlled price-data updates | Arslan |
| R12 | Asynchronous job failures or retries create duplicate or orphaned records | 2 | 3 | 6 High | Persist job states and input versions, apply idempotency keys, test timeouts and retries, preserve previously accepted results | Bayazit, Daryn |

The highest-priority risks are R1–R4 because they directly threaten the project’s research contribution or the ability to demonstrate the connected MVP.

### 8. Verification responsibilities and release criteria

Each module owner is responsible for preparing test cases, recording failures and providing reproducible evidence. The team’s verification plan specifies: at least 20 AI design scenarios with a proposed technical success target of 90% and mean reviewer scores of at least 3.5/5 per quality dimension; at least 10 independent quantity-reference cases; a held-out material-cost comparison reporting MAE (KZT), WAPE and interval coverage, with an initial WAPE target of no more than 20% and improvement over the stated baseline; usability testing with at least five representative users, of whom at least four should independently complete core homeowner tasks; and a documented 10-user performance test in which at least 95% of ordinary requests finish within two seconds. These are planned acceptance targets, not achieved results. Security, reliability, agreement-version consistency and the complete end-to-end scenario must also be checked before an MVP is declared ready.

### 9. Conclusion

The management plan establishes accountable ownership, a reviewable GitHub/YouTrack workflow, milestone-based delivery, explicit technical dependencies and a prioritized risk register. It protects the project’s central objective: to demonstrate and evaluate one coherent renovation workflow rather than a collection of disconnected prototypes. Success will be assessed through traceable artifacts, verified acceptance criteria, reproducible tests, recorded supervisor decisions and an end-to-end MVP demonstration.
