# Multimodal Intelligence

## Purpose
This document details how text, image, and location signals are fused in DecisionOS Civic.

## Content
### Multimodal Fusion Strategy
Instead of running text and images in isolation, DecisionOS fuses the signals at the feature layer:
- Text is converted to a 384-dimensional semantic embedding via `sentence-transformers`.
- Images are converted to a 512-dimensional embedding via `ResNet`.
- GIS coordinates are transformed to local coordinates.
- Fused vectors are fed into classification heads for combined severity scoring.

### Advantage
Fusing signals prevents misclassification (e.g., a text saying "road is bad" might look low severity, but the image showing a huge crater raises the combined rating to High).

## Related Documents
- [AI Architecture](../05-architecture/04-ai-architecture.md)
- [Duplicate Detection](05-duplicate-detection.md)
