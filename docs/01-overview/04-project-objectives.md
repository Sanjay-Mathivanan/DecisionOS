# Project Objectives

## Purpose
This document presents the detailed technical specifications, methodologies, and evaluation metrics for each of the ten core objectives of the DecisionOS Civic platform.

## Content

### Technical Goals & Methodologies

#### Objective 1 — Intelligent Civic Issue Understanding
*   **Technical Goal**: Parse incoming unstructured text reports in multiple languages and extract core metadata: issue category, location entity, duration, and urgency indicator.
*   **Methodology**: Utilize fine-tuned transformer networks (BERT/DistilBERT). Token classification heads perform Named Entity Recognition (NER) to isolate location nouns and duration parameters, while text classification heads categorize the issue type.
*   **Evaluation Metrics**: Micro-averaged F1-Score (target \(\ge 0.90\)) and Exact Match Accuracy for extracted entities.

#### Objective 2 — Multimodal Civic Analysis
*   **Technical Goal**: Concurrently analyze and fuse text descriptions and image uploads to determine incident severity and resolve conflicting signals.
*   **Methodology**: Apply late-fusion multimodal learning. Text features are mapped to a 384-dimensional dense space using `sentence-transformers`, while image layers are mapped to a 512-dimensional vector using `ResNet`. The outputs are concatenated and passed to a joint classifier.
*   **Evaluation Metrics**: Classification Accuracy comparison (Multimodal vs. Text-Only baseline).

#### Objective 3 — Duplicate Incident Detection
*   **Technical Goal**: Identify redundant complaints reporting the same physical defect, grouping them into a single core incident cluster.
*   **Methodology**: Calculate a weighted similarity metric combining text cosine similarity, ResNet image distance, spatial distance (via PostGIS R-tree indexing), and temporal differences.
*   **Evaluation Metrics**: Precision, Recall, and F1-score of the similarity engine (target Precision \(\ge 0.92\)).

#### Objective 4 — Civic Severity Prediction
*   **Technical Goal**: Predict the operational severity rating (0-100) of an incident.
*   **Methodology**: Train multiclass classifiers (e.g., Random Forest, XGBoost) using fused input representations, proximity parameters, and historical repeat flags.
*   **Evaluation Metrics**: Mean Absolute Error (MAE) of the predicted severity index compared to manual ratings.

#### Objective 5 — Predictive Civic Risk
*   **Technical Goal**: Forecast localized infrastructure failure hazards (e.g., waterlogging probabilities) before they occur.
*   **Methodology**: Model historical time-series datasets alongside daily environmental inputs (rainfall, elevation data, river level feeds) using XGBoost classifiers and LSTM networks.
*   **Evaluation Metrics**: Area Under the ROC Curve (AUC-ROC, target \(\ge 0.85\)) and Mean Absolute Percentage Error (MAPE).

#### Objective 6 — Civic Hotspot Detection
*   **Technical Goal**: Isolate persistent geographic concentrations of public service issues.
*   **Methodology**: Run **DBSCAN** or **HDBSCAN** spatial clustering algorithms on latitude and longitude coordinates. Apply Kernel Density Estimation (KDE) to generate smooth risk heatmaps.
*   **Evaluation Metrics**: Silhouette Coefficient of detected spatial clusters.

#### Objective 7 — Intelligent Prioritization
*   **Technical Goal**: Generate a prioritized queue of active incidents.
*   **Methodology**: Apply Multi-Criteria Decision Analysis (MCDA). The priority score is computed as a weighted linear combination of severity, vulnerability indices, recurrence metrics, and environmental risk.
*   **Evaluation Metrics**: Queue alignment comparison against manual dispatch order.

#### Objective 8 — Resource Allocation Optimization
*   **Technical Goal**: Maximize resolved community impact by scheduling optimal dispatches under constrained resources.
*   **Methodology**: Formulate and solve an **Integer Linear Programming (ILP)** problem. Define decision variables, linear constraints (personnel, vehicles, budgets, working hours), and maximize the objective function using Google OR-Tools.
*   **Evaluation Metrics**: Dispatch operational cost reductions and response time reductions compared to a greedy baseline.

#### Objective 9 — What-If Simulation
*   **Technical Goal**: Provide administrators with a sandbox workspace to model changes in system inputs.
*   **Methodology**: Recalculate priority queues and ILP constraints in real-time when inputs are modified (e.g., adding personnel or simulating high rainfall).
*   **Evaluation Metrics**: Database recomputation latency (target \(\le 1.5\) seconds for 1,000 active nodes).

#### Objective 10 — Explainable AI (XAI)
*   **Technical Goal**: Generate human-interpretable justifications for AI classifications and optimization choices.
*   **Methodology**: Implement SHAP (SHapley Additive exPlanations) values to explain ML predictions, alongside a detailed cost-benefit report showing selected vs. rejected alternatives.
*   **Evaluation Metrics**: User comprehension ratings collected via controlled administrator feedback surveys.

---

### Software Engineering vs. Academic Research Boundaries
To ensure project structure, the system is strictly split between software engineering deliverables and academic research questions:

```
┌──────────────────────────────────────┐     ┌──────────────────────────────────────┐
│       Software Engineering           │     │          Academic Research           │
│  - React Frontend UI / SPA           │     │  - Multimodal late-fusion layers     │
│  - FastAPI REST API Routing          │     │  - Coordinate weight formulas        │
│  - PostgreSQL / PostGIS Spatial DB   │     │  - Spatial DBSCAN density parameters │
│  - Celery Async Task Queues          │     │  - Constrained ILP formulations      │
└──────────────────────────────────────┘     └──────────────────────────────────────┘
```

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Project Overview](01-project-overview.md)
- [Research Focus](../13-research/01-research-overview.md)
- [Experimental Design](../13-research/04-experimental-design.md)
