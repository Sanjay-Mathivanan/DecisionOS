# Priority Engine

## Purpose
This document explains the multi-criteria prioritization logic of DecisionOS Civic.

## Content
### Priority Scoring Formula
The priority score determines the order of the municipal work queue:

\[
	ext{Priority} = 0.30 \cdot 	ext{Severity} + 0.20 \cdot 	ext{Population Impact} + 0.15 \cdot 	ext{Recurrence} + 0.15 \cdot 	ext{Location Vulnerability} + 0.10 \cdot 	ext{Infrastructure Importance} + 0.10 \cdot 	ext{Environmental Risk}
\]

*Note: The weights above are proposed baselines and must be experimentally evaluated rather than arbitrarily claimed to be optimal.*

### Example Queue
1. **Flood near hospital**: Priority = 97
2. **Drainage blockage near school**: Priority = 94
3. **Major pothole on highway**: Priority = 83
4. **Garbage accumulation**: Priority = 61
5. **Broken street light**: Priority = 42

## Related Documents
- [AI/ML Overview](01-ai-ml-overview.md)
- [Resource Optimization](10-resource-optimization.md)
