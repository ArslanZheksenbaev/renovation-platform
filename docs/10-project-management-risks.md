# 10. Project management and risks

## 1. Management approach and objectives

The project is managed as an iterative, evidence-driven software engineering effort. Requirements, architecture, user experience, implementation, and evaluation are developed in reviewable increments rather than delivered as a single final submission. The first pre-defense establishes the documented analysis and design baseline; later iterations will implement and validate the minimum viable product (MVP). The team uses GitHub for version control and peer review, YouTrack for task ownership and progress tracking, and Figma for UX prototyping. Supervisor feedback is recorded as actionable revisions. This approach supports individual accountability, early identification of integration issues, and traceability from requirements to delivered evidence.

The project targets an integrated residential renovation workflow: homeowner project and room creation; room-photo upload; AI-generated design concepts and human approval; transparent material quantities and preliminary material-cost estimation; homeowner-defined fixed contractor labour amount; contractor responses and selection; electronic agreement records; renovation stages and progress updates; and completion acceptance and contractor ratings. AI output is a design concept, not a construction-certified plan. Material estimates exclude the separate contractor labour payment. The platform does not process payments, train a generative model from scratch, or provide a full BIM editor.

## 2. Team structure and responsibility allocation

**Arslan Zheksenbaev**

Primary responsibility: Machine Learning and Cost Estimation Engineer

Principal deliverables: Quantity rules; documented price inputs; deterministic baseline; ML correction and uncertainty ranges; cost-related tests; evaluation metrics; project planning and risk register.

Review and coordination: Align estimate inputs and versions with the approved design and backend API; coordinate cross-module evaluation.

**Bayazit Abayev**

Primary responsibility: Backend and Marketplace Developer

Principal deliverables: Spring Boot APIs; PostgreSQL data model; authentication and role-based access; project/room records; contractor profiles and responses; agreements; progress and rating logic; architecture diagrams.

Review and coordination: Define API contracts, access permissions, persistence, and service integration.

**Daryn Maulen**

Primary responsibility: AI Design Generation Engineer

Principal deliverables: room-photo design pipeline using existing pretrained models; Figma mobile prototype; generation status and failure handling; design review and specification handoff; AI design evaluation.

Review and coordination: Align UX states and approved design versions with backend and estimation inputs.

**All three members**

Primary responsibility: Integration, testing, documentation and defense

Principal deliverables: Cross-module acceptance scenario; peer review; reproducible evidence; issue updates and presentation.

Review and coordination: Each member reviews another member’s changes and explains their own contribution.

Responsibilities identify accountable owners, not isolated workstreams. Changes to shared APIs, data schemas, user journeys, and acceptance criteria require coordination among affected members. The supervisor reviews major scope and architectural decisions.

## 3. Tools, repository and traceability

**GitHub repository:&#x20;**[Repository](https://github.com/ArslanZheksenbaev/renovation-platform)

**YouTrack project:&#x20;**[YouTrack](https://renovation-platform.youtrack.cloud/projects/DIP)

**Figma:&#x20;**[Prototype](https://www.figma.com/make/ShngS37t4GbtCX3zjj9Uba/High-Fidelity-Mobile-Prototype?fullscreen=1\&t=ZdXv8rB1sZVHp6sx-1\&code-node-id=0-6)

**Repository organization:&#x20;**&#x62;ackend/, ai-design-service/, cost-estimation-service/,docs/, diagrams/, prototype/, and config/,with tests maintained beside the relevant code or in a clearly documented test directory.

Each meaningful work item is tracked as a YouTrack issue with an assignee, priority, expected deliverable, deadline, and acceptance criteria. Its issue ID is included in the working branch and commit/PR title (for example, \`DIP-23-database-schema\` and \`DIP-23: Add database schema\`). A teammate reviews the pull request before merging into \`main\`. The issue links to the PR and relevant evidence and is closed only when acceptance criteria have been checked. Documentation and prototype changes follow the same workflow as code. Every contributor uses an individual Git account and identifiable commit author. Credentials, API keys, unredacted interview questionnaires, phone numbers, and private room photos must not be committed. The supervisor and committee should receive appropriate repository access.

The repository README must provide the project description, target users, scope, team roles, technologies, development status, documentation and YouTrack links, and-when runnable components exist-setup and test commands. The team will create the immutable Git tag \`pre-defense-1\` for the exact first-submission revision, with later tags \`pre-defense-2\` and \`final-pre-defense\`. Tags are created only after checking the corresponding repository state; this document does not claim that a tag already exists.

## 4. Work breakdown and milestone plan

| **Milestone**                             | **Deliverables and exit evidence**                                                                                                                                                                                                           | **Owner(s)**                                               | **Status at planning baseline**                                                                                                                          |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| M1 - Initial validation and scope         | Project proposal; four anonymized user questionnaires; evidence-to-requirements   mapping; documented MVP boundaries                                                                                                                         | All; Arslan coordinates evidence                           | Documented in the supplied diploma draft. Date inconsistencies in two   questionnaire headers require confirmation.                                      |
| M2 - First pre-defense (24 Oct 2026)      | Literature and existing-system review; technology alternatives;   prioritized requirements and acceptance criteria; context/use-case/component   diagrams; Figma prototype; verification plan; GitHub/YouTrack traceability;   risk register | All; deliverables assigned by section                      | Documentation and prototype described in diploma v0.3. Repository   access, final links, review history, and submission tag require live   verification. |
| M3 - Foundation and interface contracts   | Database schema and migrations; role-based authentication;   project/room APIs; versioned data contracts; runnable development environment                                                                                                   | Bayazit; Arslan and Daryn review                           | Planned; completion date to be agreed in YouTrack.                                                                                                       |
| M4 - AI design and cost services          | Photo/design workflow; human approval; quantity calculations; material-cost   baseline; ML experiment; uncertainty output                                                                                                                    | Daryn (design); Arslan (estimation); Bayazit (integration) | Planned; dependent on test data, model availability, and service   interfaces.                                                                           |
| M5 - Marketplace and progress integration | Requests with fixed labour amount; contractor responses and selection;   agreement versions; stage/task updates; completion acceptance; rating                                                                                               | Bayazit; all integrate and test                            | Planned; dependent on M3 and approved estimate/design data.                                                                                              |
| M6 -Verification and final delivery       | End-to-end demonstration; security and performance checks; 20 AI   scenarios; 10 quantity cases; held-out cost evaluation; five-user usability   study; documented results and limitations                                                   | All; each module owner produces evidence                   | Planned; dates to be agreed with supervisor.                                                                                                             |

M3–M6 are sequencing milestones, not claims that implementation has already been completed. Their calendar dates must be entered into YouTrack after the supervisor confirms the next checkpoint. At every milestone, the team records the reviewed commit, open issues, known limitations, and next actions.

## 5. Dependencies and critical integration path

The main dependency chain is validated requirements → shared data model and API contracts → room measurements and photo upload → AI design generation → homeowner approval of design and finish specification → material quantities and preliminary material-cost estimate → fixed-labour renovation request → contractor selection → versioned agreement → progress updates → acceptance and rating. The backend data model and access controls are prerequisites for reliable integration; the estimate must refer to confirmed measurements and specification versions rather than infer quantities from generated images alone. Material costs and labour payment remain distinct across the interface, database and reports. Long-running AI requests require explicit job states and retry handling. The team will test intermediate service contracts before attempting the full demonstration so that failures can be isolated to one component.

A delay in the approved-design-to-estimate handoff or the shared schema can block several downstream functions; therefore, these interfaces receive early review priority.

## 6. Monitoring, quality gates and change control

The team will maintain a prioritized YouTrack backlog and hold short coordination check-ins at least weekly during implementation, with additional integration reviews before milestones. Each check-in records completed work, blocked tasks, decisions, responsible persons and the next review date. High-priority blockers are raised to the full team immediately and to the supervisor when they affect scope, evaluation feasibility or a submission deadline.

A task is considered Done only when (1) its deliverable is committed to the repository or linked as an approved external artifact, (2) its stated acceptance criteria have been checked, (3) another team member has reviewed the change where applicable, (4) supporting evidence or test results are linked, and (5) documentation and dependent tasks have been updated. The team monitors issue status, overdue work, unresolved blockers, PR review time, test failures and completion of milestone deliverables. These indicators are used to support decisions, not to inflate commit or ticket counts.

A requirement or architectural change is proposed in YouTrack with a reason, affected FR/NFR identifiers, impact on schedule and dependencies, and proposed tests. Affected owners review the change before it is accepted. Baseline changes are reflected in the requirements document, diagrams, UX prototype and verification plan. Supervisor comments are logged with the resulting decision and corresponding revision; unreceived feedback is never reported as completed review.



## 7. Risk assessment and mitigation register

Risks are evaluated qualitatively using Likelihood (L) and Impact (I) on a 1–3 scale (1 = low, 2 = medium, 3 = high). Risk score = L × I. Scores 1–2 are low, 3–4 medium and 6–9 high. These are planning judgments, not measured probabilities. The responsible owner reviews the score and mitigation at each milestone.

| **ID** | **Risk and consequence**                                                                                      | **L** | **I** | **Score** | **Mitigation / contingency**                                                                                                                                                                                           | **Owner**               |
| ------ | ------------------------------------------------------------------------------------------------------------- | ----- | ----- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| R1     | Limited or unsuitable renovation cost data weakens ML accuracy and   uncertainty estimates                    | 3     | 3     | 9 High    | Define a documented price/quantity baseline first; source dated price   data; split evaluation by project; report dataset limitations and MAE/WAPE   transparently; retain deterministic estimates if ML underperforms | Arslan                  |
| R2     | AI-generated designs distort room geometry or fail to preserve   required features                            | 3     | 3     | 9 High    | Use pretrained structural controls, human approval and a constrained   prompt/input workflow; evaluate at least 20 scenarios; offer retry or   fallback generation and reject unsuitable outputs                       | Daryn                   |
| R3     | Incompatible interfaces or versions break the design → estimate →   agreement chain                           | 3     | 3     | 9 High    | Agree on shared IDs, schemas and versioned API contracts early; use   integration tests and sample payloads; prevent estimates from using   unapproved designs                                                         | Bayazit, Arslan, Daryn  |
| R4     | Limited three-person capacity causes schedule slippage or excessive   scope                                   | 3     | 3     | 9 High    | Prioritize mandatory nine-step workflow, assign one accountable owner   per task, review blockers weekly, defer escrow/full BIM and other enhancements                                                                 | All; Arslan coordinates |
| R5     | Room photos, user data or contract records are exposed through   incorrect access control                     | 2     | 3     | 6 High    | Server-side RBAC, private object storage, project-level authorization   checks, secret management, negative access tests and data minimization                                                                         | Bayazit                 |
| R6     | GPU/API availability, cost or latency prevents dependable design   generation                                 | 3     | 2     | 6 High    | Prototype on available infrastructure early; define timeouts, queued   jobs, status polling and retry; maintain replaceable provider fallback;   separate generation time from ordinary API latency                    | Daryn, Bayazit          |
| R7     | Users distrust automated quantities and estimates or misunderstand   preliminary prices                       | 2     | 3     | 6 High    | Show units, assumptions, consumption norms, price dates, ranges and   labour separation; obtain feedback from representative homeowners and   contractors                                                              | Arslan, Daryn           |
| R8     | Marketplace and agreement workflow contains conflicting selections or inconsistent   contract versions        | 2     | 3     | 6 High    | Transactional updates, one selected contractor per request, immutable   agreement versions, confirmation timestamps, repeat-request/idempotency tests                                                                  | Bayazit                 |
| R9     | Small qualitative interview sample and incomplete validation lead to   overgeneralized claims                 | 2     | 2     | 4 Medium  | Label four interviews as exploratory, preserve anonymized evidence,   correct source-date inconsistencies, test the prototype with at least five   representative users and report limitations                         | All                     |
| R10    | Unreviewed commits, missing YouTrack links or incomplete supervisor   feedback weaken assessment traceability | 2     | 3     | 6 High    | Require issue-linked branches/PRs and peer reviews; audit README,   diagrams, prototype links and access; record supervisor feedback; tag the   exact pre-defense revision                                             | All                     |
| R11    | Inconsistent material prices or missing waste allowances make   estimates misleading                          | 3     | 2     | 6 High    | Record price dates, sources, units, waste factors and assumptions;   verify at least ten reference quantity cases and allow controlled price-data   updates                                                            | Arslan                  |
| R12    | Asynchronous job failures or retries create duplicate or orphaned   records                                   | 2     | 3     | 6 High    | Persist job states and input versions, apply idempotency keys, test   timeouts and retries, preserve previously accepted results                                                                                       | Bayazit, Daryn          |

The highest-priority risks are R1–R4 because they directly threaten the project’s research contribution or the ability to demonstrate the connected MVP.

## 8. Verification responsibilities and release criteria

Each module owner is responsible for preparing test cases, recording failures and providing reproducible evidence. The team’s verification plan specifies: at least 20 AI design scenarios with a proposed technical success target of 90% and mean reviewer scores of at least 3.5/5 per quality dimension; at least 10 independent quantity-reference cases; a held-out material-cost comparison reporting MAE (KZT), WAPE and interval coverage, with an initial WAPE target of no more than 20% and improvement over the stated baseline; usability testing with at least five representative users, of whom at least four should independently complete core homeowner tasks; and a documented 10-user performance test in which at least 95% of ordinary requests finish within two seconds. These are planned acceptance targets, not achieved results. Security, reliability, agreement-version consistency and the complete end-to-end scenario must also be checked before an MVP is declared ready.



## 9. Conclusion

The management plan establishes accountable ownership, a reviewable GitHub/YouTrack workflow, milestone-based delivery, explicit technical dependencies and a prioritized risk register. It protects the project’s central objective: to demonstrate and evaluate one coherent renovation workflow rather than a collection of disconnected prototypes. Success will be assessed through traceable artifacts, verified acceptance criteria, reproducible tests, recorded supervisor decisions and an end-to-end MVP demonstration.