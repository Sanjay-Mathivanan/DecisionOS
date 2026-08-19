# Prediction API

## Purpose
This document lists predictive analytics endpoints.

## Content
### Get Flood Risk Map (`GET /predictions/risk-map`)
- **Response**:
  ```json
  {
    "timestamp": "2026-08-19T22:42:00Z",
    "zones": [
      { "zone": "Zone A", "risk_probability": 0.86 },
      { "zone": "Zone B", "risk_probability": 0.63 }
    ]
  }
  ```

## Related Documents
- [API Overview](01-api-overview.md)
- [Predictive Civic Risk](../06-ai-ml/07-risk-prediction.md)
