# Analytics API

## Purpose
This document defines spatial and metric analytics endpoints.

## Content
### Get Hotspots (`GET /analytics/hotspots`)
- **Response**:
  ```json
  {
    "hotspots": [
      { "cluster_id": 1, "size": 42, "geom": { "type": "Point", "coordinates": [...] } }
    ]
  }
  ```

## Related Documents
- [API Overview](01-api-overview.md)
- [Hotspot Detection](../06-ai-ml/08-hotspot-detection.md)
