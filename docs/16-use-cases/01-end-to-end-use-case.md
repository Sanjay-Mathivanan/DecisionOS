# End-to-End Use Case

## Purpose
This document presents an end-to-end walk-through of the DecisionOS Civic loop.

## Content
### The Scenario
- **Event**: 20 citizens submit complaints of water leakage near a school over 2 days. One citizen uploads a photograph showing water pooling.

### Steps in Action
1. **NLP Processing**: Identifies `Flooding/Drainage` category, `School Road` location.
2. **CV Processing**: Detects `Water Accumulation` and assigns `Severity = High`.
3. **Clustering**: Similarity engine notices spatial proximity and groups 20 complaints into a single incident: `#RD-1042`.
4. **Historical Lookup**: Identifies that drainage blocks here recurringly (June: 3, July: 5, August: 8).
5. **Risk Forecasting**: Calculates future hazard probability: `87%`.
6. **Prioritization**: Priority score computed as `95/100` (driven by high severity and nearby school).
7. **Optimization**: Solver allocates `Team 1` to resolve the incident based on proximity and overall budget.
8. **What-if Simulation**: Admin checks "What if we add a team?" -> Predicted resolution time decreases from 3.8 days to 1.9 days.
9. **Explainability**: Dashboard shows: "High Priority due to School Proximity and Recurring Nature."
10. **Action**: Officer clicks "Approve". `Team 1` is dispatched.

## Related Documents
- [Road Damage Use Case](02-road-damage-use-case.md)
- [How DecisionOS Works](../03-solution/03-how-decisionos-works.md)
