# Data Processing

## Purpose
This document outlines the extraction, transformation, and loading (ETL) pipeline.

## Content
### Processing Stages
1. **Cleaning**: Strip HTML tags, fix character encodings in complaint texts.
2. **Validation**: Validate latitude/longitude ranges (ensure they fall within municipal borders).
3. **Geocoding**: Convert nearest address tags to spatial points.
4. **Normalizing**: Standardize date and time formats.

```mermaid
flowchart LR
    Ingest[Raw Ingestion] --> Clean[Clean Text]
    Clean --> Validate[Validate Spatial Bounds]
    Validate --> Load[Database Load]
```

## Related Documents
- [Data Strategy](01-data-strategy.md)
- [System Architecture](../05-architecture/01-system-architecture.md)
