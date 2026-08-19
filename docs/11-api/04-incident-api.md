# Incident API

## Purpose
This document details endpoints for viewing clustered incident groups.

## Content
### Get Incident Queue (`GET /incidents`)
- **Response**:
  ```json
  [
    {
      "incident_id": "c623910c-3fb3-48b0-a337-eead4ef6b7e8",
      "category": "Road Damage",
      "priority": 91.0,
      "severity": 87.0,
      "coordinates": [11.0168, 76.9558],
      "complaint_count": 20
    }
  ]
  ```

## Related Documents
- [API Overview](01-api-overview.md)
- [Duplicate Detection](../06-ai-ml/05-duplicate-detection.md)
