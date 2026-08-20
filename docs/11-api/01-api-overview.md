# API Overview

## Purpose
This document presents the API design guidelines for the DecisionOS Civic services.

## Content
### Protocol Specification
- **Base Format**: JSON REST API.
- **Authentication**: JWT token inside HTTP headers (`Authorization: Bearer <token>`).
- **Base Endpoint**: `/api/v1`

### Authentication Flow
```mermaid
sequenceDiagram
    actor Client as Frontend Client
    participant API as FastAPI Backend
    Client->>API: Request + Bearer JWT Token
    API->>API: Verify Token Signature & Expiry
    alt Token Valid
        API->>Client: Return Requested Data (JSON)
    else Token Invalid / Expired
        API->>Client: Return 401 Unauthorized
    end
```

## Related Documents
- [Authentication API](02-authentication.md)
- [Complaint API](03-complaint-api.md)
