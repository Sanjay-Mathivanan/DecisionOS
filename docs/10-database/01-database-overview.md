# Database Overview

## Purpose
This document explains the choice of database systems.

## Content
### Storage Architecture
- **Primary Relational DB**: PostgreSQL.
- **Spatial Extensions**: PostGIS (critical for fast geospatial queries, proximity matching, and routing).
- **In-Memory Store (Cache & Queue)**: Redis (used for queueing Celery tasks and storing short-term session counts).

## Related Documents
- [Data Model](02-data-model.md)
- [Entity Relationships](03-entity-relationships.md)
