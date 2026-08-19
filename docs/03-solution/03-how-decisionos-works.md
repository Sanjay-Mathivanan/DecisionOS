# How DecisionOS Civic Works

## Purpose
This document explains the end-to-end processing pipeline of the DecisionOS Civic engine.

## Content
### The 10-Step Processing Loop
1. **NLP Processing**: Extracts issue category, location entities, duration, and urgency from text.
2. **Computer Vision**: Detects objects (e.g., potholes) in uploaded images and estimates damage severity.
3. **Duplicate Detection**: Computes similarity across text, images, space, and time to group complaints.
4. **Historical Analysis**: Tracks previous reports in the area to flag recurrence.
5. **Risk Prediction**: Forecasts future hazard likelihood (e.g., flood risk) based on weather.
6. **Impact Estimation**: Evaluates population exposure and proximity to schools, hospitals, or critical assets.
7. **Priority Engine**: Computes a unified priority score (0-100) combining severity and impact.
8. **Optimization Engine**: Runs Integer Linear Programming to find the optimal allocation of resources.
9. **What-If Simulation**: Simulates the effect of user-adjusted variables (e.g., +2 teams).
10. **Explainable AI (XAI)**: Generates a clear breakdown of recommendations using SHAP values and cost-benefit lists.

## Related Documents
- [System Architecture](../05-architecture/01-system-architecture.md)
- [End-to-End Use Case](../16-use-cases/01-end-to-end-use-case.md)
