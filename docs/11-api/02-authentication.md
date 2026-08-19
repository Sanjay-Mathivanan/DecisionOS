# Authentication API

## Purpose
This document defines endpoints for authentication.

## Content
### Login Endpoint (`POST /auth/login`)
- **Request**:
  ```json
  {
    "email": "officer@decisionos.demo",
    "password": "password123"
  }
  ```
- **Response**:
  ```json
  {
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "token_type": "bearer"
  }
  ```

## Related Documents
- [API Overview](01-api-overview.md)
- [Authentication & Authorization Security](../12-security/02-authentication-authorization.md)
