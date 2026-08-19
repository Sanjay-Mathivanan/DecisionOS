# Resource API

## Purpose
This document defines endpoints for resources and allocations.

## Content
### Get Allocation Recommendation (`GET /resources/allocations`)
- **Response**:
  ```json
  {
    "allocations": [
      { "team": "Team A", "zone": "Zone 4", "cost": 15000, "priority": 91.0 }
    ],
    "expected_response_reduction": 0.31
  }
  ```

## Related Documents
- [API Overview](01-api-overview.md)
- [Resource Optimization](../06-ai-ml/10-resource-optimization.md)
