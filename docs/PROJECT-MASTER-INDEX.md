# DecisionOS Civic: Project Master Index

## Purpose
This document acts as the primary navigation index for the entire DecisionOS Civic documentation system.

## Content
### Master Directory Structure

#### [01. Overview](01-overview/01-project-overview.md)
- [01-project-overview.md](01-overview/01-project-overview.md) - Summary of the DecisionOS Civic concept and pipeline.
- [02-executive-summary.md](01-overview/02-executive-summary.md) - High-level summary of problem, solution, and modes.
- [03-project-vision.md](01-overview/03-project-vision.md) - System vision, paradigm shift, and HITL guidelines.
- [04-project-objectives.md](01-overview/04-project-objectives.md) - Core academic and technical objectives.

#### [02. Problem Analysis](02-problem/01-problem-statement.md)
- [01-problem-statement.md](02-problem/01-problem-statement.md) - Context and background challenge.
- [02-existing-system.md](02-problem/02-existing-system.md) - Workflows of conventional complaint tracking.
- [03-existing-system-limitations.md](02-problem/03-existing-system-limitations.md) - Core system bottlenecks and limitations.
- [04-problem-analysis.md](02-problem/04-problem-analysis.md) - Data complexity and administrative gaps.

#### [03. Proposed Solution](03-solution/01-proposed-solution.md)
- [01-proposed-solution.md](03-solution/01-proposed-solution.md) - Sits-above middleware layout.
- [02-core-concept.md](03-solution/02-core-concept.md) - Input integration categories.
- [03-how-decisionos-works.md](03-solution/03-how-decisionos-works.md) - 10-step processing pipeline.
- [04-key-differentiators.md](03-solution/04-key-differentiators.md) - Feature-by-feature comparison chart.

#### [04. System Requirements](04-requirements/01-functional-requirements.md)
- [01-functional-requirements.md](04-requirements/01-functional-requirements.md) - Functional boundaries (FR-1.0 to FR-8.0).
- [02-non-functional-requirements.md](04-requirements/02-non-functional-requirements.md) - Performance, security, and scalability metrics.
- [03-user-requirements.md](04-requirements/03-user-requirements.md) - Personas (Citizen, Officer, Admin).
- [04-system-requirements.md](04-requirements/04-system-requirements.md) - Software and hardware dependencies.

#### [05. System Architecture](05-architecture/01-system-architecture.md)
- [01-system-architecture.md](05-architecture/01-system-architecture.md) - Architecture flow diagrams.
- [02-layered-architecture.md](05-architecture/02-layered-architecture.md) - Component layer breakdown.
- [03-data-flow.md](05-architecture/03-data-flow.md) - ETL and pipeline routing metrics.
- [04-ai-architecture.md](05-architecture/04-ai-architecture.md) - Multimodal model registry.
- [05-decision-intelligence-architecture.md](05-architecture/05-decision-intelligence-architecture.md) - Prioritization and explainability interface.
- [06-deployment-architecture.md](05-architecture/06-deployment-architecture.md) - Container deployment configuration.
- [07-integration-architecture.md](05-architecture/07-integration-architecture.md) - Ingestion adapter mapping.

#### [06. AI & Machine Learning](06-ai-ml/01-ai-ml-overview.md)
- [01-ai-ml-overview.md](06-ai-ml/01-ai-ml-overview.md) - ML subsystem summary.
- [02-nlp-intelligence.md](06-ai-ml/02-nlp-intelligence.md) - BERT classification.
- [03-computer-vision.md](06-ai-ml/03-computer-vision.md) - YOLOv8 road damage model.
- [04-multimodal-intelligence.md](06-ai-ml/04-multimodal-intelligence.md) - Feature-layer concatenation details.
- [05-duplicate-detection.md](06-ai-ml/05-duplicate-detection.md) - Similarity formulas.
- [06-severity-impact-prediction.md](06-ai-ml/06-severity-impact-prediction.md) - Vulnerability scoring.
- [07-risk-prediction.md](06-ai-ml/07-risk-prediction.md) - XGBoost and LSTM risk modeling.
- [08-hotspot-detection.md](06-ai-ml/08-hotspot-detection.md) - DBSCAN clustering.
- [09-priority-engine.md](06-ai-ml/09-priority-engine.md) - Multi-criteria ranking formulas.
- [10-resource-optimization.md](06-ai-ml/10-resource-optimization.md) - ILP solver mathematical layout.
- [11-intervention-recommendation.md](06-ai-ml/11-intervention-recommendation.md) - Dispatches and justifications.
- [12-what-if-simulation.md](06-ai-ml/12-what-if-simulation.md) - Sandboxing variables.
- [13-explainable-ai.md](06-ai-ml/13-explainable-ai.md) - SHAP value breakdown.

#### [07. Data Strategy](07-data/01-data-strategy.md)
- [01-data-strategy.md](07-data/01-data-strategy.md) - Baseline strategy.
- [02-data-sources.md](07-data/02-data-sources.md) - Open government datasets and collections.
- [03-dataset-requirements.md](07-data/03-dataset-requirements.md) - Ingestion schemas.
- [04-data-processing.md](07-data/04-data-processing.md) - Normalization and validation.
- [05-data-quality.md](07-data/05-data-quality.md) - Filter constraints.
- [06-data-privacy.md](07-data/06-data-privacy.md) - Privacy protections and masking.

#### [08. Domains](08-domains/01-domain-overview.md)
- [01-domain-overview.md](08-domains/01-domain-overview.md) - Domain plugins.
- [02-road-damage.md](08-domains/02-road-damage.md) - Pothole and road degradation scope.
- [03-waste-management.md](08-domains/03-waste-management.md) - Bin collection scheduling.
- [04-water-drainage.md](08-domains/04-water-drainage.md) - Leakage prioritization.
- [05-flood-risk.md](08-domains/05-flood-risk.md) - Monsoon risk mapping.

#### [09. User Workflows](09-users/01-user-roles.md)
- [01-user-roles.md](09-users/01-user-roles.md) - Role permission matrix.
- [02-citizen-workflow.md](09-users/02-citizen-workflow.md) - PWA submission sequence.
- [03-field-worker-workflow.md](09-users/03-field-worker-workflow.md) - Mobile updates.
- [04-officer-workflow.md](09-users/04-officer-workflow.md) - Queue review and overrides.
- [05-administrator-workflow.md](09-users/05-administrator-workflow.md) - Adjusting configuration weights.

#### [10. Database Schema](10-database/01-database-overview.md)
- [01-database-overview.md](10-database/01-database-overview.md) - Relational architecture choices.
- [02-data-model.md](10-database/02-data-model.md) - Tables schemas.
- [03-entity-relationships.md](10-database/03-entity-relationships.md) - Entity Relationship diagram.

#### [11. API Contracts](11-api/01-api-overview.md)
- [01-api-overview.md](11-api/01-api-overview.md) - Core protocol format.
- [02-authentication.md](11-api/02-authentication.md) - Sign-in contracts.
- [03-complaint-api.md](11-api/03-complaint-api.md) - Complaint submission.
- [04-incident-api.md](11-api/04-incident-api.md) - Queue access.
- [05-prediction-api.md](11-api/05-prediction-api.md) - Risk forecasting.
- [06-resource-api.md](11-api/06-resource-api.md) - Dispatch solutions.
- [07-simulation-api.md](11-api/07-simulation-api.md) - Simulator triggers.
- [08-analytics-api.md](11-api/08-analytics-api.md) - Hotspot heatmaps.

#### [12. Security & Responsibility](12-security/01-security-overview.md)
- [01-security-overview.md](12-security/01-security-overview.md) - Security overview.
- [02-authentication-authorization.md](12-security/02-authentication-authorization.md) - RBAC controls.
- [03-data-security.md](12-security/03-data-security.md) - Encryption standards.
- [04-responsible-ai.md](12-security/04-responsible-ai.md) - Human-in-the-loop logs.

#### [13. Research Focus](13-research/01-research-overview.md)
- [01-research-overview.md](13-research/01-research-overview.md) - Academic research layout.
- [02-research-questions.md](13-research/02-research-questions.md) - The 4 key RQs.
- [03-research-contribution.md](13-research/03-research-contribution.md) - Specific academic outputs.
- [04-experimental-design.md](13-research/04-experimental-design.md) - Baselines and comparators.
- [05-evaluation-metrics.md](13-research/05-evaluation-metrics.md) - Quantifiable statistics.

#### [14. Implementation Pathway](14-implementation/01-technology-stack.md)
- [01-technology-stack.md](14-implementation/01-technology-stack.md) - Codebase technologies.
- [02-development-roadmap.md](14-implementation/02-development-roadmap.md) - 8-month timeline.
- [03-mvp-scope.md](14-implementation/03-mvp-scope.md) - Scope boundary constraints.
- [04-advanced-features.md](14-implementation/04-advanced-features.md) - Post-MVP schedule.
- [05-future-scope.md](14-implementation/05-future-scope.md) - Long-term extensions.
- [06-team-responsibilities.md](14-implementation/06-team-responsibilities.md) - Resource organizational layout.

#### [15. Integration & Deployments](15-integration/01-government-integration.md)
- [01-government-integration.md](15-integration/01-government-integration.md) - System constraints.
- [02-integration-gateway.md](15-integration/02-integration-gateway.md) - Connection adapters.
- [03-authority-deployment.md](15-integration/03-authority-deployment.md) - Sandbox municipality pilots.

#### [16. Use Case Walkthroughs](16-use-cases/01-end-to-end-use-case.md)
- [01-end-to-end-use-case.md](16-use-cases/01-end-to-end-use-case.md) - Complete system pipeline scenario.
- [02-road-damage-use-case.md](16-use-cases/02-road-damage-use-case.md) - Pothole patch scenario.
- [03-water-drainage-use-case.md](16-use-cases/03-water-drainage-use-case.md) - Leak fix sequence.
- [04-flood-risk-use-case.md](16-use-cases/04-flood-risk-use-case.md) - Proactive monsoon mitigation.

#### [17. Project Management](17-project-management/01-project-phases.md)
- [01-project-phases.md](17-project-management/01-project-phases.md) - Milestone schedules.
- [02-deliverables.md](17-project-management/02-deliverables.md) - Code and thesis deliverable metrics.
- [03-risks.md](17-project-management/03-risks.md) - Risk analysis grid.
- [04-limitations.md](17-project-management/04-limitations.md) - System operational boundaries.

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Project Overview](01-overview/01-project-overview.md)
- [Problem Statement](02-problem/01-problem-statement.md)
- [Proposed Solution](03-solution/01-proposed-solution.md)
