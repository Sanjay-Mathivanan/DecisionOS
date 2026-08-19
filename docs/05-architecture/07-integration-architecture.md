# Integration Architecture

## Purpose
This document explains how DecisionOS Civic integrates with external government databases and third-party APIs.

## Content
### Integration Gateway
The gateway sits at the entry point of the network and abstracts integration formats:

```mermaid
graph LR
    CSV[CSV Files] --> IG[Integration Gateway]
    Rest[REST API] --> IG
    WebH[Webhooks] --> IG
    DB[DB Adapters] --> IG
    
    IG --> UDM[Unified Data Model]
```

This allows the platform to remain system-agnostic. Municipalities can upload simple CSV dumps (e.g., `complaints.csv`) if they do not support live API synchronization.

## Related Documents
- [Government Integration](../15-integration/01-government-integration.md)
- [Integration Gateway](../15-integration/02-integration-gateway.md)
