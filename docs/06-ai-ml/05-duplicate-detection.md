# Duplicate Detection

## Purpose
This document details the similarity engine used for duplicate complaint grouping.

## Content
### Similarity Matching
To check if a new complaint is a duplicate of an active incident, the system calculates a combined similarity score using:
- **Text Similarity**: Comparing complaint descriptions.
- **Image Similarity**: Comparing complaint photos.
- **Location Similarity**: Checking the spatial distance on the map (PostGIS).
- **Time Similarity**: Checking the time difference between submissions.

If this combined similarity score exceeds a threshold (82%), the complaint is automatically merged into the existing incident.

## Related Documents
- [AI/ML Overview](01-ai-ml-overview.md)
- [Research Questions](../13-research/02-research-questions.md)
