# 6. Requirements Specification

## Purpose and scope

The proposed system is an intelligent web platform for residential renovation project management. It connects homeowners and renovation contractors through a marketplace and integrates AI-based interior design generation, cost and material estimation, electronic contract records, and project progress monitoring.

The platform supports a connected workflow: a homeowner creates a renovation project, provides room information, reviews an AI-generated design, obtains a preliminary estimate, selects a contractor, confirms the agreed scope, and monitors renovation progress.

These requirements represent an initial baseline derived from the project proposal. They must be validated through 3–5 discussions with potential users or a substantive agreement with an actual client. They do not represent confirmed interview findings.

## User roles

| Role | Main responsibilities |
| --- | --- |
| Homeowner | Create renovation projects, provide room information, review designs and estimates, select a contractor, confirm agreements, and monitor progress. |
| Contractor | Maintain a service profile, review renovation requests and respond to renovation requests with homeowner-defined fixed labour amounts, submit quotations, confirm agreements, and update assigned project stages. |
| Platform administrator | Manage accounts and marketplace records, assign project access, and maintain reference data within granted permissions. |

## Requirement priorities

Must: Required for the MVP and demonstration of the complete renovation workflow.

Should: Important functionality that may follow the core implementation.

Could: Optional functionality implemented if time and resources permit.

## Functional requirements

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

## Non-functional requirements

| ID | Requirement | Priority | Acceptance criteria |
| --- | --- | --- | --- |
| NFR-01 | The system should provide responsive interaction under the documented demonstration workload. | Must | With 10 concurrent users on the documented test environment, at least 95% of ordinary project, profile, and task requests complete within 2 seconds. AI generation and file transfer are measured separately. |
| NFR-02 | The system should handle AI-service failures without losing project data. | Must | When an AI request times out or fails, the project and previous successful results remain available. The request receives a visible failure status. Retrying does not create duplicate accepted designs, estimates, or contracts. |
| NFR-03 | The interface should be usable by users without technical expertise. | Must | In a usability session with at least five representative users, at least four complete project creation, design review, and estimate viewing without moderator intervention. Completion times, errors, and participant feedback are recorded. |
| NFR-04 | The system should preserve data consistency across its modules. | Must | An interrupted operation does not leave a contract without its accepted quotation or an estimate without its input references. Saving repeated confirmation requests does not create duplicate confirmations. |

## AI and ML acceptance criteria

## Design generation

Technical generation success and visual design quality should be evaluated separately. Returning an image alone does not demonstrate that the design meets the user’s requirements.

For the initial evaluation:

Prepare at least 20 room-and-style test scenarios with documented constraints.

At least 90% of valid requests should return a viewable result within the configured timeout on the documented environment.

Two reviewers independently assess style consistency, visual coherence, and preservation of required room features using a defined five-point rubric.

The proposed quality target is a mean score of at least 3.5 out of 5 for each dimension.

Failed generations and reviewer disagreements are included in the evaluation report.

Generated images should be presented as renovation concepts requiring user review.

## Cost estimation

The estimation model should be evaluated using renovation records excluded from model training and model selection. Records belonging to the same renovation project should remain in the same data partition to reduce information leakage.

Acceptance requires:

A documented dataset containing input features, target costs, units, price dates, and preprocessing rules.

Separate training, validation, and test partitions.

Comparison against a simple baseline, such as average renovation cost per square metre by finish level.

Reporting of Mean Absolute Error in KZT and Weighted Absolute Percentage Error on the held-out test set.

A proposed target of WAPE no greater than 20% and lower MAE than the baseline on the same test cases.

Evaluation of the reported cost ranges against actual costs, including their observed coverage and average width.

The 20% threshold is an initial research target. Its feasibility must be reviewed after examining the dataset. Any revision must be documented before final testing.

## Material quantities

Material quantity calculations should be checked separately from ML cost predictions.

For at least 10 reference cases, covering supported room shapes and work types, calculated quantities should match independently prepared calculations within the declared rounding tolerance. Each case should specify dimensions, deductions, units, and waste assumptions.

## MVP acceptance scenario

- The MVP should demonstrate the following connected scenario:

- A homeowner registers and creates a renovation project.

- The homeowner adds a room, measurements, photos, and renovation preferences.

- The platform generates an interior design concept.

- The homeowner reviews the concept and confirms its finish specification.

- The platform produces material quantities and a preliminary cost estimate.

- The homeowner publishes a renovation request.

- The homeowner publishes a renovation request with a fixed labour amount. A contractor responds to these conditions, and the homeowner selects the contractor.

- Both parties confirm the corresponding electronic contract record.

- The contractor updates a renovation stage, and the homeowner views the progress.

- The contractor submits completed work for acceptance. The homeowner accepts the work or requests corrections. After acceptance, the homeowner submits a rating, and the contractor’s average rating is recalculated.

## Requirements validation and traceability

Each mandatory requirement should be linked to a YouTrack task, a responsible team member, and at least one verification activity. A requirement may be marked as completed only when its acceptance criteria have been checked and supporting evidence has been recorded.

User discussions should validate the proposed workflow, required project inputs, contractor response information and homeowner-defined fixed labour terms, agreement confirmation process, and progress reporting needs. Changes resulting from these discussions should be recorded in the requirements revision history.

For the initial submission, acceptance means that the requirements are documented, prioritized, traceable, and reviewable. Implementation acceptance will be assessed during later project stages.
