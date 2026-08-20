# Computer Vision

## Purpose
This document outlines the computer vision pipeline for processing image evidence.

## Content
### Visual Processing Pipeline
1. **Image Quality Check**: Identifies blurred, dark, or invalid images.
2. **Object Detection (YOLOv8)**: Detects potholes, cracks, garbage piles, or leaks.
3. **Severity Estimation**: ResNet/EfficientNet models classify damage severity (Low, Medium, High).

### Vision Processing Pipeline Flow
```mermaid
flowchart LR
    Photo[Uploaded Photo] --> QC[Quality Check: Blur/Darkness]
    QC -->|Pass| YOLO[YOLOv8 Detector]
    YOLO -->|Locates Defect| Classifier[ResNet Classifier]
    Classifier --> Output[Output: Bounding Box & Severity Rating]
```

### Example
- **Input**: Image of a road.
- **Output**: Bounding box: `Pothole`, `Confidence`: `94%`, `Severity`: `Severe`.

## Related Documents
- [AI/ML Overview](01-ai-ml-overview.md)
- [Road Damage Domain](../08-domains/02-road-damage.md)
