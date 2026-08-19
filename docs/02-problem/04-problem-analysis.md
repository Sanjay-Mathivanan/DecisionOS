# Problem Analysis

## Purpose
This document presents a detailed analysis of unstructured civic data anomalies, detailing NLP linguistic variations and Computer Vision image drifts.

## Content

### Unstructured Data Anomalies
To build a reliable decision-intelligence platform, DecisionOS must handle significant noise in citizen submissions.

#### 1. NLP Linguistic Anomalies & Code-Switching
Citizen text inputs are rarely written in standard grammatically correct English. The NLP engine must process:
*   **Colloquial Misspellings**: "put-hole", "pot hole", "pothol", "drain block", "drin leak".
*   **Code-Switching (Multilingual Hybrid Text)**: Citizens often mix English and local languages (e.g., Tanglish: *"ABC school main gate kitta oru periya pothole iruku, pullainga cross panna kashtapaduranga"*).
*   **Vague Geospatial Descriptors**: Instead of coordinates, reports describe locations relative to landmarks: *"near the big banyan tree"* or *"opposite hospital gate"*.

```
[Raw Multilingual Text Input] ──► (Tokenizer & Named Entity Recognition) ──► [Structured Location & Issue Class]
```

To resolve these, the NLP pipeline utilizes multilingual embeddings and named entity recognition (NER) models fine-tuned on local municipal vocabulary.

#### 2. Computer Vision Visual Drift
Photos uploaded by citizens vary widely in quality and perspective, presenting several challenges for automated object detection:
*   **Occlusion**: The target defect (e.g., a pothole) may be partially blocked by parked vehicles, trash piles, water, or pedestrians.
*   **Illumination Drift**: Images captured under heavy rain, shadows, bright sunlight, or streetlights at night introduce severe lighting variations.
*   **Perspective Distortion**: Citizen photos are captured at slanted angles rather than from top-down angles, distorting the apparent size and depth of road damage.

To overcome these, our vision pipeline implements pre-processing filters to check image contrast, alongside YOLOv8 models trained on datasets representing diverse angles and weather conditions.

---

### The Computational Decision Gap
Municipal officers face a massive gap between receiving complaints and dispatching resources. Raw datasets are fragmented:

$$
\text{Data Influx} \quad \{ \text{Text}, \, \text{Image}, \, \text{GPS}, \, \text{Weather} \} \quad \not\implies \quad \text{Optimal Resource Dispatch}
$$

Bridging this gap requires three distinct computational layers:
1.  **AI Understanding**: Converts raw text and images into structured categories and severity scores.
2.  **Information Consolidation**: Clusters duplicate entries and extracts spatial-temporal metrics.
3.  **Operations Research Optimization**: Solves resource allocation models using Integer Linear Programming to output optimized dispatch schedules.

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Problem Statement](01-problem-statement.md)
- [Proposed Solution](../03-solution/01-proposed-solution.md)
- [Duplicate Detection](../06-ai-ml/05-duplicate-detection.md)
