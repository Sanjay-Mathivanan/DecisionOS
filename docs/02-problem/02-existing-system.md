# Existing System

## Purpose
This document analyzes the architecture and workflow of conventional grievance-management platforms currently used by local governments.

## Content
### Typical Workflow
1. **Citizen Submission**: A citizen fills out a web form or calls a hotline.
2. **Registration**: A unique complaint ID is generated.
3. **Manual Routing**: An administrator reads the text and assigns it to a department (e.g., Roads).
4. **Worker Dispatch**: The department supervisor manually assigns a worker based on convenience.
5. **Closure**: The worker reports completion, and the ticket is closed.

```mermaid
seqDiagram
    Citizen->>Grievance App: Reports Problem
    Grievance App->>Admin Portal: Registers Ticket
    Admin Portal->>Dept Supervisor: Assigns Department
    Dept Supervisor->>Field Worker: Assigns Task
    Field Worker->>Grievance App: Resolves & Closes
```

This workflow treats every single report as a siloed entity and provides zero analytical support.

## Related Documents
- [Problem Statement](01-problem-statement.md)
- [Limitations of Existing Systems](03-existing-system-limitations.md)
