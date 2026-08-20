# MVP Scope

## Purpose
This document defines the boundary of the Minimum Viable Product (MVP).

## Content
### MVP Boundaries
To prevent scope creep, the MVP focuses on a single, complete end-to-end loop:

```mermaid
flowchart LR
    A[Citizen Road Damage Report] --> B[YOLO Detection]
    B --> C[Priority Queue Ranking]
    C --> D[OR-Tools Dispatch Solver]
```

### Scope Divisions

#### Must Build (MVP)
- Citizen PWA submission form (Photo + GPS).
- Multimodal similarity engine (duplicate detection).
- Basic resource scheduling solver.
- Officer Approve/Override dashboard.

#### Advanced / Optional
- What-if simulation engine.
- High-capacity LSTM risk forecasting.
- SHAP feature explainers.

#### Future
- Automated UMANG/CPGRAMS sync.
- Real-time IoT sensor network feeds.

![MVP Scope](../../diagrams/14-mvp-scope.png)
*Figure 11. MVP scope mapping, highlighting must-build elements vs advanced and future features.*

## Related Documents
- [Development Roadmap](02-development-roadmap.md)
- [Future Scope](05-future-scope.md)
