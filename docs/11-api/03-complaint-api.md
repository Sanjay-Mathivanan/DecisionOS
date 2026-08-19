# Complaint API

## Purpose
This document lists the endpoints for submitting and tracking complaints.

## Content
### Submit Complaint (`POST /complaints`)
- **Request**:
  ```json
  {
    "description": "Huge pothole near school",
    "latitude": 11.0168,
    "longitude": 76.9558,
    "image_data": "base64..."
  }
  ```
- **Response**:
  ```json
  {
    "complaint_id": "8f8705f4-3d07-4e0c-a4be-a6b12df71891",
    "status": "received",
    "timestamp": "2026-08-19T22:42:00Z"
  }
  ```

## Related Documents
- [API Overview](01-api-overview.md)
- [Citizen Workflow](../09-users/02-citizen-workflow.md)
