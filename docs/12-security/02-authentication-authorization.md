# Authentication and Authorization

## Purpose
This document details the verification and access rules.

## Content
### Access Control Layout
We enforce Role-Based Access Control (RBAC):
- **Citizen**: Write permissions on complaints; read-only on public maps.
- **Officer**: Edit permissions on resource allocations; read-only on simulations.
- **Admin**: Full access.

JWT tokens with expiration claims protect backend API routes.

## Related Documents
- [Security Overview](01-security-overview.md)
- [Authentication API](../11-api/02-authentication.md)
