# Non-Functional Requirements

## Purpose
This document outlines the performance, security, and scalability constraints of DecisionOS Civic.

## Content
### Performance Metrics
- **Latency**: API response time for complaint registration must be under 500ms. Image analysis must be complete within 3 seconds.
- **Throughput**: System must support up to 100 concurrent API requests/second.

### Security
- **Authentication**: JWT/OAuth2 mechanisms.
- **Role-Based Access Control (RBAC)**: Distinct permissions for Citizens, Officers, Supervisors, and Administrators.
- **Data Protection**: Encryption in transit (HTTPS/TLS) and at rest (PostgreSQL encryption).

### Scalability
- The system must use a microservices pattern to decouple the FastAPI backend from deep learning workers.
- Geospatial indexes must be optimized in PostGIS to handle querying millions of points.

## Related Documents
- [Functional Requirements](01-functional-requirements.md)
- [System Requirements](04-system-requirements.md)
