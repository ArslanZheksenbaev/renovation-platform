# 2. Evidence of the relevance

**Initial qualitative requirements validation | 4 participant questionnaires**

## 1. Purpose and project context

The diploma project, “The Development of an Intelligent Digital Platform for Renovation Project Management with AI-Based Design and Cost Estimation,” proposes a connected web workflow for residential renovation. Homeowners can describe rooms, review AI-generated interior concepts, obtain preliminary material and cost estimates, interact with contractors, record agreed terms, and monitor work progress. The target users are apartment and house owners and renovation contractors or small construction teams. This section evaluates whether those proposed capabilities address problems described by potential users.

## 2. Evidence collection method

Four completed written questionnaires were collected: two from construction/renovation professionals and two from homeowners (one apartment owner and one private-house owner). The professionals reported working in Aktobe, Kazakhstan, and completed their questionnaires on 23 October 2026. The homeowner forms state 24 October 2026; this date should be confirmed before submission because it is later than the current drafting date, 23 October. All four forms indicate consent to use responses in anonymized academic reporting. The questionnaires covered existing practices, budgeting, design decisions, contractor coordination, progress reporting, and reactions to the proposed solution. This is purposive, small-sample qualitative requirements discovery, not a representative survey. The study records self-reported experience and opinions; no platform usability test or objective accuracy test has yet been performed.

## 3. Participant profile

P1 - renovation/finishing contractor and team manager; approximately ten years’ experience reported in the answer; typically one or two projects per month. P2 - construction professional specializing in house construction; the profile states 30 years of experience; typically one to four projects per month. H1 - owner of a three-room apartment renovated with a private team. H2 - owner of a roughly 200 m² private house finished using several specialized crews. Participant identifiers are used in this report instead of names or contact details.

## 4. Findings grounded in participant responses

**F1. Fragmented and time-consuming estimation (P1, P2, H1, H2).** Both professionals reported using small Excel tables and determining quantities from measured areas/volumes and consumption norms. Both described the absence of specialized software and the manual maintenance of spreadsheets as time-consuming. H1 described a rough handwritten estimate and materials requested in stages; H2 had separate calculations from different teams without one consolidated estimate. These accounts support the need for a structured project-wide estimate and material breakdown.

**F2. Cost overruns and uncertain quantities (P1, P2, H1, H2).** Both professionals cited uneven surfaces, material quality and excess consumption as reasons estimates change. H1 reported a roughly 30–35% increase over her initial renovation budget; this is a single participant’s recollection, not an average or measured market statistic. H2 described additional putty and tile adhesive needed because of uneven preliminary plastering. A preliminary estimate should therefore display assumptions, waste allowances, price dates and a range rather than promise a final fixed cost.

**F3. Design ambiguity and change requests (P1, P2, H1, H2).** Both professionals noted that customers often lack formal design projects and change their preferences during execution. H1 described relocating sockets and changing wall colours, with rework and additional payments; H2 reported new lighting and finishing ideas leading to rework. Both professionals considered a visible design concept helpful for earlier agreement on intended finishes and for preparing an estimate. This supports AI-generated concepts with explicit homeowner review and approval, not fully automatic design decisions.

**F4. Contractor selection, agreements and coordination (P1, P2, H1, H2).** Both professionals obtain customers primarily through reputation or referrals and expressed interest in receiving requests through the platform. H1 found it difficult to assess contractor reliability and described verbal agreements without clearly fixed deadlines. H2 described coordination problems between specialist crews and a mix of written and verbal agreements. These findings support contractor profiles, comparable quotations, a versioned record of agreed terms, and visibility of work responsibilities; they do not establish the legal validity of an electronic signature.

**F5. Progress reporting and oversight (P1, P2, H1, H2).** Both professionals reported frequent on-site oversight and phone calls to clients. H1 visited the renovation almost daily and received receipts and photos through WhatsApp; H2 travelled to the site two or three times per week and received photos, videos and receipts through messaging apps. These experiences support a shared progress view with stage status and supporting evidence.

**F6. Trust depends on transparency (P1, P2, H1, H2).** Both professionals said they would initially check automated estimates manually and wanted the consumption norms to be visible. Both homeowners likewise conditioned trust on understandable norms or reference standards; H1 additionally wanted verified contractor reviews and photographs of completed projects. Therefore the estimation interface should expose inputs, calculation rules, units and assumptions and allow human checking.

## 5. Evidence-to-requirements traceability

| Finding | Participants | Requirements | Proposed response |
|---|---|---|---|
| F1: manual/fragmented estimates | P1, P2, H1, H2 | FR-02, FR-06, FR-07 | Measured room inputs; unified itemized estimate; material quantities |
| F2: overruns and variable quantities | P1, P2, H1, H2 | FR-06, FR-07 | Waste/assumptions; price data and preliminary ranges |
| F3: design changes and ambiguity | P1, P2, H1, H2 | FR-03, FR-04, FR-05 | Photo-based concepts and mandatory human approval |
| F4: contractor coordination and agreements | P1, P2, H1, H2 | FR-08, FR-09, FR-10 | Profiles, quotations, recorded agreement versions |
| F5: progress visibility | P1, P2, H1, H2 | MVP step 9; progress requirement needs explicit FR ID | Stage updates and homeowner progress view |
| F6: explainable results | P1, P2, H1, H2 | FR-06, FR-07; NFR-03 | Show norms, inputs, units, assumptions and allow checks |

## 6. Implications and decisions

The interviews support prioritizing a single connected renovation workflow rather than separate design, estimating and messaging tools. The MVP should emphasize: (1) measured room dimensions and finish specifications as estimation inputs; (2) human review of AI design concepts before an estimate is generated; (3) material quantities with units, calculation norms and waste assumptions; (4) a preliminary cost breakdown with uncertainty and a clear distinction between materials and contractor labour quotations; (5) contractor profiles, requests, quotations and recorded agreement versions; and (6) stage-based progress updates with photos or notes. These are proposed design responses to participant findings and still require prototype validation.

Two participants suggested functionality beyond the current MVP: H1 requested protected milestone-based payments or escrow, and H2 requested a schedule coordinating different specialist crews. Escrow/payment processing should be recorded as a future enhancement rather than silently added to the MVP. Detailed cross-contractor scheduling may also be considered for a later iteration after the core stage-tracking workflow is implemented.

## 7. Limitations and research integrity

The sample comprises only four participants, all reported from Aktobe; it cannot represent the entire renovation market in Kazakhstan. Recruitment was purposive and no random selection was used. The questionnaires were written and self-reported; the responses were not independently observed or verified. Participants were introduced to the proposed features before answering evaluation questions. The four professional questionnaires contain notably similar accounts in several areas.

## 8. Conclusion

The four questionnaires provide initial qualitative evidence that residential renovation users face fragmented estimation, material overrun, unclear design expectations, informal coordination, and limited progress visibility. Both user groups described practical reasons to value an integrated platform, especially transparent preliminary estimates, early design review and progress reporting. The evidence supports the relevance of the proposed problem and informs the initial requirements.
