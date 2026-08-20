# Development Roadmap

## Purpose
This document outlines the 8-month implementation timeline.

## Content
### Month-by-Month Development Timeline
- **Month 1 (Foundation)**: Auth, citizen portal database layout, basic PostGIS mapping.
- **Month 2 (Civic NLP)**: Fine-tune DistilBERT on text classification, extract entities.
- **Month 3 (Computer Vision)**: Train YOLOv8 on road damage, build image validator.
- **Month 4 (Incident Intelligence)**: Build the similarity engine for duplicate detection.
- **Month 5 (Prediction)**: Implement XGBoost risk forecasting and generate maps.
- **Month 6 (Decision Intelligence)**: Build OR-Tools optimization solvers.
- **Month 7 (Simulation + Explainability)**: Sliders for scenario parameters; write SHAP explanations.
- **Month 8 (Deployment + Thesis)**: Dockerization, performance evaluations, academic paper preparation.

### Project Gantt Timeline
```mermaid
gantt
    title 8-Month Project Timeline
    dateFormat  X
    axisFormat %d
    section Phases
    Month 1: Foundation (Auth, DB) :active, 0, 1
    Month 2: Civic NLP (DistilBERT) : 1, 2
    Month 3: Computer Vision (YOLOv8) : 2, 3
    Month 4: Incident Intel (Duplicates) : 3, 4
    Month 5: Prediction (XGBoost Risk) : 4, 5
    Month 6: Decision (OR-Tools Solver) : 5, 6
    Month 7: Sandbox & XAI (SHAP, Sliders) : 6, 7
    Month 8: Deployment & Testing (Docker) : 7, 8
```

## Related Documents
- [Technology Stack](01-technology-stack.md)
- [MVP Scope](03-mvp-scope.md)
