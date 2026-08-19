# Entity Relationships

## Purpose
This document visualizes the relationships between database tables.

## Content
### Entity Relationship Schema

![Database ER Diagram](../../diagrams/12-database-er.png)
*Figure 10. Entity-Relationship diagram showing the connection between Complaints, Incidents, Allocations, and Predictions.*

### ER Diagram (Mermaid Format)
```mermaid
erDiagram
    USERS ||--o{ COMPLAINTS : submits
    COMPLAINTS }o--o| INCIDENTS : clusters_into
    INCIDENTS ||--o{ ALLOCATIONS : receives
    RESOURCES ||--o{ ALLOCATIONS : assigned_to
    INCIDENTS ||--o{ PREDICTIONS : tracks
```

## Related Documents
- [Data Model](02-data-model.md)
- [Database Overview](01-database-overview.md)
