# Duplicate Detection

## Purpose
This document details the similarity engine used for duplicate complaint grouping.

## Content
### Similarity Formula
To check if a new complaint refers to an active incident, we compute a weighted similarity score:

\[
	ext{Similarity} = w_1 \cdot 	ext{Sim}_{	ext{text}} + w_2 \cdot 	ext{Sim}_{	ext{image}} + w_3 \cdot 	ext{Sim}_{	ext{location}} + w_4 \cdot 	ext{Sim}_{	ext{time}}
\]

Where:
- \(	ext{Sim}_{	ext{text}}\): Cosine similarity of sentence embeddings.
- \(	ext{Sim}_{	ext{image}}\): Cosine similarity of image feature vectors.
- \(	ext{Sim}_{	ext{location}}\): Geospatial distance metric (e.g., \(1 - d_{	ext{meters}} / d_{	ext{max}}\)).
- \(	ext{Sim}_{	ext{time}}\): Temporal distance score.

If the combined similarity exceeds a predefined threshold (e.g., 0.82), the complaint is merged into the existing incident.

## Related Documents
- [AI/ML Overview](01-ai-ml-overview.md)
- [Research Questions](../13-research/02-research-questions.md)
