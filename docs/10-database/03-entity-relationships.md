# Entity Relationships

## Purpose
This document visualizes the relationships between database tables.

## Content
### Entity Relationship Schema

![Database ER Diagram](../../diagrams/12-database-er.png)
*Figure 10. Entity-Relationship diagram showing the connection between Complaints, Incidents, Allocations, and Predictions.*

```mermaid
erDiagram
    USERS {
        uuid user_id PK
        string email
        string password_hash
        string role
    }
    COMPLAINTS {
        uuid complaint_id PK
        uuid user_id FK
        text description
        string image_path
        geometry geom
        timestamp timestamp
        string status
    }
    INCIDENTS {
        uuid incident_id PK
        string category
        float severity
        float priority
        geometry geom
        float risk_score
    }
    RESOURCES {
        uuid resource_id PK
        integer worker_count
        string vehicle_type
        boolean availability
    }
    ALLOCATIONS {
        uuid allocation_id PK
        uuid incident_id FK
        uuid resource_id FK
        numeric cost
        float expected_impact
    }
    
    USERS ||--o{ COMPLAINTS : submits
    COMPLAINTS }o--o| INCIDENTS : groups_into
    INCIDENTS ||--o{ ALLOCATIONS : receives
    RESOURCES ||--o{ ALLOCATIONS : assigned_to
```

## Related Documents
- [Data Model](02-data-model.md)
- [Database Overview](01-database-overview.md)
