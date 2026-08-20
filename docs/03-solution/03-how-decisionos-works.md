# How DecisionOS Civic Works

## Purpose
This document explains the step-by-step logic of the DecisionOS processing pipeline, including developer pseudocode and ranking criteria.

## Content

### The 10-Step Processing Loop

1.  **Ingestion**: Citizen uploads a ticket (description, photo, GPS coordinates).
2.  **Linguistic Classification (NLP)**: The text is cleaned, and a model (DistilBERT) extracts the category and urgency.
3.  **Visual Classification (CV)**: The photo passes to a detector (YOLOv8) to locate the damage (e.g., a pothole) and score visual severity.
4.  **Spatial-Temporal Triage**: The database checks for existing incidents within a 120-meter radius.
5.  **Duplicate Assessment**: A similarity engine calculates if the new complaint matches an active incident. If it does, it links the complaint to avoid duplicate dispatches.
6.  **Recurrence Analysis**: The database checks for previous complaints in the area over the past 90 days.
7.  **Impact Rating**: Exposure is calculated based on population density and proximity to key assets (schools/hospitals).
8.  **Prioritization Ranking**: The incident is assigned a Priority Score (0-100) based on severity and exposure factors.
9.  **Constrained Optimization**: Google OR-Tools schedules worker dispatches to resolve the most critical issues first.
10. **Explainable AI (XAI)**: Simple, text-based explanations are generated for the officer's dashboard.

---

### Core Pipeline Loop Pseudocode
The following pseudocode outlines the execution sequence of the core processing loop:

```python
def process_new_complaint(complaint_data):
    # Step 1 & 2: NLP Analysis
    nlp_results = nlp_model.predict(complaint_data.description)
    category = nlp_results.category
    urgency_tag = nlp_results.urgency
    
    # Step 3: Computer Vision Analysis
    cv_results = cv_model.detect_fault(complaint_data.image_path)
    cv_severity = cv_results.severity_score # 0 - 100
    
    # Step 4 & 5: Spatial Duplicate Checks
    active_incidents = db.query_incidents_in_radius(
        lat=complaint_data.latitude, 
        lon=complaint_data.longitude, 
        radius_meters=120
    )
    
    matched_incident_id = None
    for incident in active_incidents:
        similarity = compute_multimodal_similarity(
            text_desc=complaint_data.description,
            incident_text=incident.summary_desc,
            img_path=complaint_data.image_path,
            incident_img=incident.sample_image_path,
            distance_meters=calculate_distance(complaint_data, incident)
        )
        if similarity >= 0.82:
            matched_incident_id = incident.id
            break
            
    if matched_incident_id:
        db.link_complaint_to_incident(complaint_data.id, matched_incident_id)
        db.recompute_incident_parameters(matched_incident_id)
        return {"status": "merged", "incident_id": matched_incident_id}
        
    # If no duplicate found: Initialize new Incident
    new_incident = db.create_incident(
        category=category,
        geom=point(complaint_data.latitude, complaint_data.longitude),
        base_severity=cv_severity
    )
    db.link_complaint_to_incident(complaint_data.id, new_incident.id)
    
    # Step 6, 7 & 8: Compute Priority Score
    recurrence_count = db.count_previous_complaints(new_incident.geom, days=90)
    vulnerability_index = db.get_zone_vulnerability(new_incident.geom)
    exposure_score = calculate_exposure(new_incident.geom)
    
    priority_score = calculate_priority(
        severity=cv_severity,
        exposure=exposure_score,
        recurrence=recurrence_count,
        vulnerability=vulnerability_index
    )
    
    db.update_incident_priority(new_incident.id, priority_score)
    
    # Step 9: Trigger Resource Optimization Solver
    trigger_optimization_solver()
    
    return {"status": "created", "incident_id": new_incident.id}
```

---

### Priority Scoring Criteria
The system calculates priority by combining five core factors, which are weighted based on city policies:
*   **Severity**: The physical extent of the damage (e.g., deep pothole vs. small crack).
*   **Population Exposure**: How many people are affected (e.g., busy high-traffic road vs. quiet side street).
*   **Recurrence**: How often complaints have occurred here over the past 90 days.
*   **Location Vulnerability**: Proximity to critical facilities (e.g., hospitals, schools).
*   **Environmental Flood Risk**: Probability of waterlogging from rain.

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Proposed Solution](01-proposed-solution.md)
- [Priority Engine](../06-ai-ml/09-priority-engine.md)
- [Resource Optimization](../06-ai-ml/10-resource-optimization.md)
- [Duplicate Detection](../06-ai-ml/05-duplicate-detection.md)
