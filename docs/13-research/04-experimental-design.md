# Experimental Design

## Purpose
This document defines the research methodology and test setups.

## Content
### Comparative Experiments
To answer the research questions, the project is tested under the following conditions:

#### Multimodal Severity Tests (RQ1)
- Test 1: Text Only (BERT classifier on description).
- Test 2: Text + Image (BERT features + ResNet classification features).
- Test 3: Complete Fusion (Text + Image + Location Proximity + Historical counts).

#### Optimization Tests (RQ4)
- **Baseline**: Manual selection.
- **Greedy**: Dispatch to nearest incident first.
- **Optimization Model**: Resource scheduling solver (using Google OR-Tools).

## Related Documents
- [Research Questions](02-research-questions.md)
- [Evaluation Metrics](05-evaluation-metrics.md)
