# Field Worker Workflow

## Purpose
This document outlines the field worker mobile interface (Status: Proposed).

## Content
### Operational Cycle
- **To Be Defined**: Exact layout of the mobile application screen for field workers.
- **Missing Source Info**: The source document does not define how field workers mark coordinates of finished tasks or log supplies used.
- **Proposed Flow**:
  1. Receive active push notification for dispatch.
  2. Open map view for routing.
  3. Upload photo evidence of resolved task to trigger closing sequence.

### Operational Cycle Flowchart
```mermaid
flowchart LR
    A[Receive Notification] --> B[Open Route Map]
    B --> C[Perform Repair]
    C --> D[Upload Completion Photo]
```

## Related Documents
- [User Roles](01-user-roles.md)
