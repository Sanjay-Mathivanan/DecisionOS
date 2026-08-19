# Functional Requirements

## Purpose
This document lists the system's functional requirements.

## Content
### Core Requirements (Status: MVP)
- **FR-1.0 (Citizen Submission)**: The system must allow citizens to submit text, upload images, and tag GPS coordinates.
- **FR-2.0 (NLP Extraction)**: The system must categorize complaint text and extract duration and urgency.
- **FR-3.0 (CV Processing)**: The system must perform object detection (e.g., potholes) and predict damage severity.
- **FR-4.0 (Incident Clustering)**: The system must group related complaints using geospatial, temporal, and semantic similarity.
- **FR-5.0 (Priority Calculation)**: The system must compute a priority score (0-100) using weights.
- **FR-6.0 (Resource Optimization)**: The system must calculate the optimal allocation of resources under budget, vehicle, and personnel constraints.

### Advanced Requirements (Status: Proposed)
- **FR-7.0 (What-if Simulation)**: The system must allow administrators to modify inputs (rainfall, teams) and recompute risk and resolution times.
- **FR-8.0 (Explainability Breakdown)**: The system must display ML feature importance and optimization justifications.

## Related Documents
- [Non-Functional Requirements](02-non-functional-requirements.md)
- [User Requirements](03-user-requirements.md)
