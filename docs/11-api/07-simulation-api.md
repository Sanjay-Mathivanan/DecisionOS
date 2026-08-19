# Simulation API

## Purpose
This document details simulation triggering endpoints.

## Content
### Run What-if Simulation (`POST /simulation/run`)
- **Request**:
  ```json
  {
    "variables": {
      "rainfall_delta": 0.20,
      "extra_workers": 2
    }
  }
  ```
- **Response**:
  ```json
  {
    "current": { "risk": 0.72, "resolution_time": 4.8 },
    "simulated": { "risk": 0.51, "resolution_time": 2.7 }
  }
  ```

## Related Documents
- [API Overview](01-api-overview.md)
- [What-if Simulation](../06-ai-ml/12-what-if-simulation.md)
