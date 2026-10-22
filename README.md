# Renovation Platform

Intelligent digital platform for renovation project management with AI-based design generation and cost estimation.

## Problem statement
Despite progress in certain areas of artificial intelligence and digital applications, the literature reviewed remains fragmented on individual tasks of design, evaluation, monitoring, and user interaction. Generative design research focuses on creating or editing layouts and visual concepts, while text-to-image conversion research primarily evaluates image generation methods, datasets, and quality metrics (Zeng et al., 2025; Chen et al., 2025a; Alhabeeb & Al-Shargabi, 2024). Other studies focus on classifying the authenticity of AI-generated interiors or the role of human designers in improving AI performance, indicating that using renovation tools requires more than just creating images (Liu & Deng, 2025; Alshboul et al., 2026). Cost and resource management research focuses on forecasting, uncertainty, prioritization, or resource allocation (Chen et al., 2025b; Zeng & Gao, 2024), while BIM-related research considers interoperability and progress tracking as separate technical issues (Seydgar et al., 2024; Xue et al., 2022). Therefore, it remains poorly understood how artificial intelligence-based design, cost and material assessment, BIM/project monitoring, human-centered interaction, and secure project management can be integrated and evaluated as a single coherent renovation workflow focused on homeowners and contractors.
## Target users
- Homeowners planning an apartment or house renovation, who need to visualize options, understand the budget and follow progress without technical expertise.
- Renovation contractors and small renovation teams, who need to turn client requirements into estimates, materials lists and schedules, and report progress to clients.
- Secondary: interior designers and project managers who use the platform to speed up concept drafts and estimates.

## Aim
To design and develop a web platform that integrates AI-based design generation, cost and material estimation, and project monitoring into a single renovation workflow for homeowners and contractors, and to evaluate it against a baseline of the current manual process.

## Expected outcomes
- A documented analysis package: literature review, system and technology comparisons, requirements specification, architecture description and diagrams.
- A UX prototype of the key user scenarios.
- An evaluation report with results on estimate accuracy against a reference, time saved compared with the manual process, and user feedback.
- A GitHub repository with documentation, tests and a YouTrack task history that shows the development process

## Team and supervisor
| Name               | Responsibilities | GitHub |
|--------------------|---------|--|
| Bayazit Abayev     | Backend and Marketplace Developer | Metsuk1 |
| Arslan Zheksenbaev | Machine Learning and Cost Estimation Engineer | ArsikIT |
| Daryn Maulen       | AI Design Generation Engineer | DarynMaulen |

Supervisor: Zhaksylyk Kozhakhmet Erdanuly

## Scope and status
## In scope: 
- Web application (backend plus user interface) for homeowners and contractors.
- Residential interior renovation (apartments and houses).
- AI design generation via existing models/APIs (integration and adaptation, not training a model from scratch).
- Cost and material estimation based on price data and project parameters (area, room type, work types, finish level).
- Project monitoring: stages, tasks, progress status, basic reporting.
- Authentication, role-based access and protection of project data.

## Out of scope:
- Training new generative AI models from scratch.
- Full BIM authoring or a complete BIM editor; only basic data exchange if feasible.
- Structural, engineering or legal calculations and building-permit approval.

**Current status:** analysis and design phase (preparation for pre-defense 1).

## Technologies
(will be updated after the technology comparison, see `docs/05-technology-comparison.md`).

## Links
- YouTrack: TBD
- Documentation: [docs/](docs/)

## Setup, run, test
Will be added as soon as runnable code is available.