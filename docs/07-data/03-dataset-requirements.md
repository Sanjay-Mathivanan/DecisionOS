# Dataset Requirements

## Purpose
This document defines schemas and validation formats for data assets.

## Content
### Ingestion Schema (CSV/JSON Format)
Every incoming complaint record must contain:
- `complaint_id`: String (UUID)
- `description`: Text
- `image_path`: Path string (optional)
- `latitude`: Float
- `longitude`: Float
- `timestamp`: DateTime
- `status`: String (open, assigned, closed)

### Self-Collected Data Guidelines
- Collect local road images.
- Tag each photo with GPS coordinate metadata and time.
- Label: `Pothole`, `Crack`, or `Normal`.

## Related Documents
- [Data Processing](04-data-processing.md)
- [Data Model](../10-database/02-data-model.md)
