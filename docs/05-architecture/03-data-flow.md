# Data Flow

## Purpose
This document tracks the flow of data through DecisionOS Civic from ingestion to dashboard display.

## Content
### Ingestion to Recommendation Data Flow
1. **Ingestion**: Raw complaints arrive via CSV, REST API, or webhook.
2. **Validation**: Integration Gateway filters out empty records or invalid schemas.
3. **Extraction**: The NLP and CV engines extract features.
4. **Clustering**: The similarity engine checks if the complaint coordinates and semantic values overlap with an existing open `Incident`.
5. **Score Generation**: The priority score is generated.
6. **OR Solver**: The optimization engine runs the Integer Linear Programming solver to output allocations.
7. **Feedback**: The human decision is logged, closing the loop.

![Data Flow](../../diagrams/03-data-flow.png)
*Figure 3. Unified data flow diagram showing raw data ingestion, processing, modeling, and output routing.*

## Related Documents
- [System Architecture](01-system-architecture.md)
- [API Overview](../11-api/01-api-overview.md)
