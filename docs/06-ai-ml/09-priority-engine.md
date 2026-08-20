# Priority Engine

## Purpose
This document explains the multi-criteria prioritization logic of DecisionOS Civic.

## Content
### Priority Scoring
The priority score determines the order of the municipal work queue. It is calculated by combining several core factors:
*   **Severity**: How bad the physical damage is (Low, Medium, High, Critical).
*   **Population Impact**: How many citizens are affected by the issue.
*   **Recurrence**: Whether this is a recurring problem in the area.
*   **Location Vulnerability**: Proximity to critical sites like hospitals or schools.
*   **Environmental Risk**: Localized environmental risks (e.g., flood risk due to rain).

### Example Queue
1. **Flood near hospital**: Priority = 97
2. **Drainage blockage near school**: Priority = 94
3. **Major pothole on highway**: Priority = 83
4. **Garbage accumulation**: Priority = 61
5. **Broken street light**: Priority = 42

## Related Documents
- [AI/ML Overview](01-ai-ml-overview.md)
- [Resource Optimization](10-resource-optimization.md)
