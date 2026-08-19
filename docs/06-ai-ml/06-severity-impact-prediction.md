# Severity and Impact Prediction

## Purpose
This document describes the algorithms that evaluate incident severity and community impact.

## Content
### Severity Evaluation
The severity score (0-100) is predicted using:
- Issue category.
- Computer Vision damage extent.
- Recurrence flags.

### Community Impact Calculation
Impact represents population vulnerability:
- Proximity to critical sites (Hospitals = High, Schools = Medium).
- Population density of the zone.
- Traffic flow impact (e.g., arterial road blockage vs. residential lane).

## Related Documents
- [Priority Engine](09-priority-engine.md)
- [Road Damage Domain](../08-domains/02-road-damage.md)
