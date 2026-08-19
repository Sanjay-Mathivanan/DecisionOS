# Layered Architecture

## Purpose
This document describes the layered software architecture of DecisionOS Civic.

## Content
### Architectural Layers

```
┌────────────────────────────────────────────────────────┐
│                    Presentation Layer                  │
│       React SPA / Leaflet Maps / Tailwind CSS UI       │
├────────────────────────────────────────────────────────┤
│                       API Layer                        │
│            FastAPI REST API / JSON Web Tokens          │
├────────────────────────────────────────────────────────┤
│                   Business Logic Layer                 │
│ NLP/CV Inference / Similarity Clustering / OR-Tools    │
├────────────────────────────────────────────────────────┤
│                   Data Access Layer                    │
│        SQLAlchemy ORM / PostGIS Spatial Queries        │
├────────────────────────────────────────────────────────┤
│                      Database Layer                    │
│               PostgreSQL / PostGIS / Redis             │
└────────────────────────────────────────────────────────┘
```

### Decoupling Strategy
AI and Optimization tasks are computationally heavy. The API layer (FastAPI) routes tasks to asynchronous Celery workers backed by Redis, protecting API responsiveness.

## Related Documents
- [System Architecture](01-system-architecture.md)
- [Technology Stack](../14-implementation/01-technology-stack.md)
