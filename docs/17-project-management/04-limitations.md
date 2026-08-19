# Project Limitations

## Purpose
This document lists the technical and operational boundaries of the project.

## Content
### Core Limitations
- **GPS Inaccuracy**: The duplicate clustering engine assumes citizen GPS sensors are accurate within 15 meters. Heavy cloud cover or urban canyons may degrade accuracy.
- **Synthetic Constraint**: Due to lack of real-world municipal operational data, resource solver efficiencies are validated against synthetic scenarios.
- **Domain Limits**: The MVP only includes road damage. Other domains are conceptual.

## Related Documents
- [Project Risks](03-risks.md)
- [Data Strategy](../07-data/01-data-strategy.md)
