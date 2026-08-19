# Proposed Solution: DecisionOS Civic

## Purpose
This document presents the detailed architectural and operational parameters of **DecisionOS Civic** as a decision-support layer for public authorities.

## Content

### Sits-Above Integration Middleware
DecisionOS Civic is not built to replace existing municipal databases, customer portals, or national grievance management portals (such as CPGRAMS or UMANG). Instead, the platform is engineered as an **AI-Powered Middleware Integration Layer** that processes data from existing systems and feeds optimized results back to municipal supervisors.

```
┌──────────────────────────────────────┐
│     Existing Grievance Systems       │ (CPGRAMS, UMANG, Web Portals)
└──────────────────┬───────────────────┘
                   │
                   ▼ (REST APIs / Webhooks / CSV Ingestion)
┌──────────────────────────────────────┐
│           DECISIONOS CIVIC           │
│  - AI Multimodal Inference Engine    │ (NLP Category Extractor, CV Object Detector)
│  - Spatial-Temporal Clustering       │ (DBSCAN duplicate grouping)
│  - Dynamic Prioritization Module     │ (0-100 Weighted scoring)
│  - Mathematical Dispatch Optimization│ (Integer Linear Programming Solver)
│  - Explainable Recommendations       │ (SHAP Feature Importance & Cost-Benefit logs)
└──────────────────┬───────────────────┘
                   │
                   ▼ (Supervisor Dashboard Queue)
┌──────────────────────────────────────┐
│    Authorized Municipal Decisions    │ (Approve / Override with reason log)
└──────────────────┬───────────────────┘
                   │
                   ▼ (Worker Dispatch commands)
┌──────────────────────────────────────┐
│     Existing Departmental Queues     │ (Roads, Water, Waste, Disaster Teams)
└──────────────────────────────────────┘
```

---

### Core Engineering Components

The system decouples data ingestion, AI inference, and optimization solving to ensure high throughput:

1.  **Frontend Single Page Application (SPA)**: Built using React and TypeScript. Integrates Leaflet and MapLibre for localized spatial coordinate rendering, incident heatmaps, and route updates.
2.  **FastAPI API Gateway**: An asynchronous Python backend that handles JWT verification, complaint creation, database queries, and simulation execution.
3.  **Celery Distributed Task Queue**: Offloads high-computation AI modeling (PyTorch, Hugging Face BERT) and optimization solving (Google OR-Tools) to asynchronous worker pools, preventing API network timeouts.
4.  **Spatial Relational Database**: PostgreSQL with the **PostGIS** extension, enabling high-performance spatial-temporal indexing and R-tree clustering queries.
5.  **In-Memory Storage (Redis)**: Backs the Celery message broker and handles short-term session counts.

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Core Concept](02-core-concept.md)
- [How DecisionOS Works](03-how-decisionos-works.md)
- [Key Differentiators](04-key-differentiators.md)
- [System Architecture](../05-architecture/01-system-architecture.md)
- [Layered Architecture](../05-architecture/02-layered-architecture.md)
