# 1. Project Proposal

## Team

1) Arslan Zheksenbaev Serikovich,

Group: SE-2403,

Phone: +7 776 298 8401,

Email: [usenbaeva1994@gmail.com](mailto:usenbaeva1994@gmail.com)

2) Bayazit Abayev Kazymbetovich

Group: SE-2403

Phone: +7 771 033 5826,

Email: [bayazit439@gmail.com](mailto:bayazit439@gmail.com)

3) Daryn Maulen Arkabayuly,

Group: SE-2403,

Phone: +7 771 535 00 98,

Email: [darynmaulen12@gmail.com](mailto:darynmaulen12@gmail.com)

## Topic

ENG: «The Development of an Intelligent Digital Platform for Renovation Project Management with AI-Based Design and Cost Estimation»

RUS: «Разработка интеллектуальной цифровой платформы для управления ремонтными проектами с использованием ИИ для генерации дизайна и оценки стоимости»

KZ: «Дизайнды генерациялау мен құнын бағалауда ЖИ қолданатын, жөндеу жобаларын басқаруға арналған зияткерлік цифрлық платформаны әзірлеу»

## Supervisor

Kozhakhmet Zhaksylyk

## Problem statement

Renovation planning today is split across disconnected tools: AI image generators for design ideas, separate spreadsheets or estimators for costs and materials, and separate BIM or tracking tools for progress. Existing research also treats these tasks in isolation: generative design (Zeng et al., 2025; Chen et al., 2025a), cost and resource forecasting (Chen et al., 2025b; Zeng & Gao, 2024), and BIM interoperability and progress tracking (Seydgar et al., 2024; Xue et al., 2022). Studies also show that AI-generated interiors need human oversight and authenticity checks (Liu & Deng, 2025; Alshboul et al., 2026). As a result, homeowners and contractors lack a single workflow that connects an AI-generated design with a cost and material estimate and with project monitoring. It remains unclear how such a workflow can be built and evaluated as one coherent, user-centered and secure system.

## Target users

Homeowners planning an apartment or house renovation, who need to visualize options, understand the budget and follow progress without technical expertise.

Renovation contractors and small renovation teams, who need to turn client requirements into estimates, materials lists and schedules, and report progress to clients.

Secondary: interior designers and project managers who use the platform to speed up concept drafts and estimates.

## Aim

To design and develop a web platform that integrates AI-based design generation, cost and material estimation, and project monitoring into a single renovation workflow for homeowners and contractors, and to evaluate it against a baseline of the current manual process.

## Objectives

- Collect and verify requirements through 3-5 discussions with homeowners and contractors (or an agreement with a real client).

- Review the literature (at least 12 sources, including at least 8 scientific ones) and compare 3-5 existing systems against 6-10 criteria.

- Justify the technology stack by comparing alternatives for at least three key decisions (backend platform, data storage, AI/ML integration approach).

- Specify functional and non-functional requirements with priorities and acceptance criteria.

- Design the architecture (system context, use case and component diagrams) and a UX prototype of the key scenarios.

- Implement the backend core: project and user management, role-based access, secure storage of project data.

- Implement the design module: AI generation and editing of renovation concepts from user input, with a human review step.

- Implement the estimation module: cost and material estimates linked to the selected design, with uncertainty ranges.

- Implement the monitoring module: tasks, stages and progress tracking, with a BIM-related data exchange (e.g. IFC import/export) if feasible within the scope.

- Evaluate the platform: testing, usability testing with real users, and comparison with the baseline using defined metrics.

## Expected outcomes

- A working MVP of the platform, with design, estimation and monitoring modules connected in one workflow.

- A documented analysis package: literature review, system and technology comparisons, requirements specification, architecture description and diagrams.

- A UX prototype of the key user scenarios.

- An evaluation report with results on estimate accuracy against a reference, time saved compared with the manual process, and user feedback.

- A GitHub/GitLab repository with documentation, tests and a YouTrack task history that shows the development process.

## Scope

## In scope

- Web application (backend plus user interface) for homeowners and contractors.

- Residential interior renovation (apartments and houses).

- AI design generation via existing models/APIs (integration and adaptation, not training a model from scratch).

- Cost and material estimation based on price data and project parameters (area, room type, work types, finish level).

- Project monitoring: stages, tasks, progress status, basic reporting.

- Authentication, role-based access and protection of project data.

## Out of scope

- Training new generative AI models from scratch.

- Full BIM authoring or a complete BIM editor; only basic data exchange if feasible.

- Structural, engineering or legal calculations and building-permit approval.
