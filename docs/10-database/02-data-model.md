# Data Model

## Purpose
This document outlines the database tables and schemas.

## Content
### Table Schemas (Proposed PostgreSQL)

#### Users
- `user_id` (PK, UUID)
- `email` (VARCHAR, Unique)
- `password_hash` (VARCHAR)
- `role` (VARCHAR: Citizen, Officer, Admin)

#### Complaints
- `complaint_id` (PK, UUID)
- `user_id` (FK, Nullable)
- `description` (TEXT)
- `image_path` (VARCHAR)
- `geom` (GEOMETRY(Point, 4326))
- `timestamp` (TIMESTAMP)
- `status` (VARCHAR: open, clustered, closed)

#### Incidents
- `incident_id` (PK, UUID)
- `category` (VARCHAR)
- `severity` (FLOAT)
- `priority` (FLOAT)
- `geom` (GEOMETRY(Point, 4326))
- `risk_score` (FLOAT)

#### IncidentReports
- `incident_id` (FK)
- `complaint_id` (FK)

#### Predictions
- `prediction_id` (PK, UUID)
- `geom` (GEOMETRY(Point, 4326))
- `prediction_type` (VARCHAR)
- `probability` (FLOAT)
- `timestamp` (TIMESTAMP)

#### Resources
- `resource_id` (PK, UUID)
- `worker_count` (INTEGER)
- `vehicle_type` (VARCHAR)
- `availability` (BOOLEAN)

#### Allocations
- `allocation_id` (PK, UUID)
- `incident_id` (FK)
- `resource_id` (FK)
- `cost` (NUMERIC)
- `expected_impact` (FLOAT)

#### Simulations
- `simulation_id` (PK, UUID)
- `scenario_name` (VARCHAR)
- `inputs` (JSONB)
- `outputs` (JSONB)
- `created_by` (FK)

## Related Documents
- [Database Overview](01-database-overview.md)
- [Entity Relationships](03-entity-relationships.md)
