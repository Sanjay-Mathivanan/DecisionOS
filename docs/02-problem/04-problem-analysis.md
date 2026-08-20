# Problem Analysis

## Purpose
This document analyzes the practical issues that arise when processing unstructured citizen reports (text and images).

## Content

### Unstructured Data Anomalies

To build a reliable system, our project must handle the messy, inconsistent data submitted by citizens:

#### 1. Text Classification Challenges (NLP)
Citizen text inputs are rarely perfect:
*   **Colloquial Terms & Typos**: Citizens type words differently ("pot-hole", "kuzhi", "pothol").
*   **Mixed Languages (Code-Switching)**: In multilingual areas, reports mix languages (e.g., *"Road damage near school gate kitta, children cross panna mudila"*).
*   **Vague Locations**: Citizens often type landmarks instead of coordinates (e.g., *"opposite the temple"*).
*   *Solution*: The NLP engine must be trained to clean text, identify location keywords, and translate/categorize hybrid languages into standard categories.

#### 2. Visual Variations in Photos (Computer Vision)
Photos taken by citizens present several challenges:
*   **Occlusion**: The road defect might be blocked by parked cars, garbage, puddles, or people.
*   **Lighting Drift**: Photos might be taken at night under streetlights, in bright sunlight, or in rainy weather with shadows.
*   **Perspective Distortions**: Citizen photos are captured at slanted angles, making it hard to measure the size and depth of a pothole.
*   *Solution*: The vision engine must perform basic preprocessing checks for blur/contrast, and the YOLO detector must be trained on photos taken from different angles.

---

### The Decision Gap
There is a massive gap between receiving complaints and dispatching teams:

```
[Raw Citizen Reports] ──► (AI Analysis & Grouping) ──► (Optimization Engine) ──► [Optimized Dispatch]
```

To bridge this gap, our final-year project implements:
1.  **AI Understanding**: Classifying issues and severity.
2.  **Duplicate Detection**: Grouping reports to clean the queue.
3.  **Resource Scheduling**: Recommending dispatches to supervisors.

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Problem Statement](01-problem-statement.md)
- [Proposed Solution](../03-solution/01-proposed-solution.md)
- [Duplicate Detection](../06-ai-ml/05-duplicate-detection.md)
