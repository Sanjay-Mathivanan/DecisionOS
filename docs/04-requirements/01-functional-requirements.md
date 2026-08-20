# Functional Requirements

## Purpose
This document presents the detailed functional requirements of DecisionOS Civic, mapping system actions to target features and implementation status.

## Content

### Detailed Functional Requirements Specifications

#### FR-1.0: Citizen Complaint Submission
*   **Description**: The system must allow public citizens to submit civic infrastructure complaints without requiring account registration.
*   **Inputs**: Description (unstructured text), photo evidence (image file), and geospatial coordinates (automatic GPS coordinates or manual map pins).
*   **System Actions**:
    1.  Validate coordinates (must fall within target municipal boundaries).
    2.  Check image quality (filter out blurred or corrupt files).
    3.  Generate a unique tracking code.
*   **Output**: Complaint ID and status: `received`.

#### FR-2.0: Natural Language Processing (NLP) Triage
*   **Description**: The system must automatically parse complaint text to extract parameters.
*   **System Actions**:
    1.  Standardize text (remove special characters, HTML, and punctuation).
    2.  Classify the text into a core civic category (Roads, Water, Waste, Drainage).
    3.  Extract temporal details (e.g., "three days") and urgency indicators.
*   **Output**: Category class tag, duration parameter, and urgency tag.

#### FR-3.0: Computer Vision (CV) Analysis
*   **Description**: The system must analyze uploaded photos to identify infrastructure faults and score severity.
*   **System Actions**:
    1.  Locate visual anomalies (e.g., potholes, cracks) and generate bounding boxes.
    2.  Predict visual severity (Low, Medium, High).
*   **Output**: Bounding box coordinates, class label, confidence score, and severity level.

#### FR-4.0: Duplicate Incident Clustering
*   **Description**: The system must group redundant complaints reporting the same physical defect into a single Incident.
*   **System Actions**:
    1.  Query active incidents within a 120-meter spatial radius.
    2.  Calculate combined similarity (text cosine similarity, image distance, spatial distance, and time differences).
    3.  Link complaints with similarity scores $\ge 0.82$ to the matching Incident ID.
*   **Output**: Incident ID assignment (linked or newly created).

#### FR-5.0: Prioritization Engine
*   **Description**: The system must calculate a priority index (0-100) to rank active incidents.
*   **System Actions**:
    1.  Retrieve incident severity, zone population density, recurrence counts, and localized flood risks.
    2.  Compute the priority index using the multi-criteria weighted formula.
*   **Output**: Priority score (0-100) saved to the database.

#### FR-6.0: Resource Optimization Solver
*   **Description**: The system must calculate the optimal allocation of workers, vehicles, and budgets to active incidents.
*   **System Actions**:
    1.  Collect available personnel counts, transit assets, and budget ceilings.
    2.  Solve the Integer Linear Programming (ILP) optimization model using Google OR-Tools.
    3.  Generate dispatch recommendations.
*   **Output**: Optimized crew schedule allocations.

#### FR-7.0: What-If Simulation Sandbox
*   **Description**: The system must allow administrators to modify inputs and recompute outcomes.
*   **System Actions**:
    1.  Adjust input variables (rainfall percentage, crew count, budget limits) via slider UI.
    2.  Recompute priority indices and resource constraints.
    3.  Display a side-by-side comparison of baseline vs. simulated scenarios.
*   **Output**: Recomputed risk probabilities and resolution times.

#### FR-8.0: Explainability Visualizer
*   **Description**: The system must display clear justifications for ML predictions and solver dispatches.
*   **System Actions**:
    1.  Calculate SHAP values for priority predictions.
    2.  List active and rejected resource alternatives with cost-benefit metrics.
*   **Output**: Justification logs visible on the officer dashboard.

---

### Requirement Traceability Matrix

| Requirement ID | Feature Title | Component | Priority (MVP Status) |
|---|---|---|---|
| **FR-1.0** | Citizen Complaint Submission | Ingestion | **Must Build (MVP)** |
| **FR-2.0** | NLP Triage | AI Engine | **Must Build (MVP)** |
| **FR-3.0** | CV Analysis | AI Engine | **Must Build (MVP)** |
| **FR-4.0** | Duplicate Incident Clustering | Incident Intel | **Must Build (MVP)** |
| **FR-5.0** | Prioritization Engine | Decision Engine | **Must Build (MVP)** |
| **FR-6.0** | Resource Optimization Solver | Decision Engine | **Must Build (MVP)** |
| **FR-7.0** | What-if Simulation Sandbox | Simulation Engine| **Advanced / Optional** |
| **FR-8.0** | Explainability Visualizer | Explainability | **Advanced / Optional** |

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Non-Functional Requirements](02-non-functional-requirements.md)
- [User Requirements](03-user-requirements.md)
- [System Requirements](04-system-requirements.md)
- [How DecisionOS Works](../03-solution/03-how-decisionos-works.md)
