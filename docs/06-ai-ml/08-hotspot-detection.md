# Hotspot Detection

## Purpose
This document describes the spatial clustering algorithms used to detect problem hotspots.

## Content
### Algorithms Used
- **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise)
- **HDBSCAN**
- **Kernel Density Estimation** (KDE)

### Operational Usage
By feeding latitude and longitude coordinate histories into DBSCAN, the system isolates high-density clusters. The administrator is presented with a heatmap identifying chronic failure zones (e.g., persistent garbage dumping locations).

## Related Documents
- [AI/ML Overview](01-ai-ml-overview.md)
- [Database Model](../10-database/02-data-model.md)
