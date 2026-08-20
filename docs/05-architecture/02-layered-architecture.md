# Layered Architecture

## Purpose
This document describes the layered software architecture of DecisionOS Civic.

## Content
### Architectural Layers

```mermaid
flowchart TD
    UI[Presentation Layer<br/>React SPA / Leaflet / Tailwind]
    API[API Layer<br/>FastAPI / JWT]
    Logic[Business Logic Layer<br/>NLP / CV / OR-Tools]
    Data[Data Access Layer<br/>SQLAlchemy ORM / PostGIS]
    DB[Database Layer<br/>PostgreSQL / PostGIS / Redis]
    
    UI --> API
    API --> Logic
    Logic --> Data
    Data --> DB
```

### Decoupling Strategy
AI and Optimization tasks are computationally heavy. The API layer (FastAPI) routes tasks to asynchronous Celery workers backed by Redis, protecting API responsiveness.

## Related Documents
- [System Architecture](01-system-architecture.md)
- [Technology Stack](../14-implementation/01-technology-stack.md)
