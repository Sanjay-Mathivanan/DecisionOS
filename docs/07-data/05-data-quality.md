# Data Quality

## Purpose
This document sets standards for monitoring and maintaining data quality.

## Content
### Quality Controls
- **Image Filter**: Drop pictures with extremely low contrast or resolution.
- **GPS Drift Checker**: Flag reports with coordinates placed outside regional municipal bounds.
- **Text Anomaly Filter**: Discard complaints containing fewer than 3 words.

### Quality Control Pipeline
```mermaid
flowchart TD
    Input[New Complaint Influx] --> QC_Text{Text >= 3 Words?}
    QC_Text -->|No| Reject[Discard Report]
    QC_Text -->|Yes| QC_GPS{Within City Boundaries?}
    QC_GPS -->|No| Reject
    QC_GPS -->|Yes| QC_Img{Image Sharp & Bright?}
    QC_Img -->|No| Warning[Flag for Manual Review]
    QC_Img -->|Yes| Database[(Load into Database)]
```

## Related Documents
- [Data Strategy](01-data-strategy.md)
- [Dataset Requirements](03-dataset-requirements.md)
