# Data Privacy

## Purpose
This document defines protocols for protecting sensitive data.

## Content
### Privacy Principles
1. **PII Masking**: Citizen names, phone numbers, and home addresses must be stripped or encrypted at the database layer.
2. **Location Obfuscation**: For publicly visible heatmaps, exact coordinate values are rounded to a grid resolution of 100 meters to protect reporter anonymity.
3. **Access Controls**: Supervisors and officers can view exact coordinates, while public views are restricted.

## Related Documents
- [Responsible AI](../12-security/04-responsible-ai.md)
- [Data Security](../12-security/03-data-security.md)
