# System Architecture

## Purpose
This document details the high-level system architecture of DecisionOS Civic.

## Content
### Architectural Overview
DecisionOS Civic is structured to handle data ingestion, AI inference, and optimization in a decoupled pipeline.

![System Architecture](../../diagrams/02-system-architecture.png)
*Figure 2. High-level architecture showing the flow from civic data sources through AI, prediction, decision intelligence, and human decision-making.*

### System Flow
```mermaid
flowchart TD
    Ext[External Sources] --> IG[Integration Gateway]
    IG --> UDM[Unified Data Model]
    UDM --> AIE[AI Engine]
    AIE --> NLP[NLP Engine]
    AIE --> CV[Computer Vision]
    AIE --> GIS[Geospatial Engine]
    NLP & CV & GIS --> II[Incident Intelligence]
    II --> PE[Prediction Engine]
    PE --> DE[Decision Engine]
    DE --> SE[Simulation Engine]
    SE --> XAI[Explainability Engine]
    XAI --> OD[Officer Dashboard]
```

## Related Documents
- [Layered Architecture](02-layered-architecture.md)
- [Data Flow](03-data-flow.md)
