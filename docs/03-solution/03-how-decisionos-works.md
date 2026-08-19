# How DecisionOS Civic Works

## Purpose
This document explains the step-by-step logic of the DecisionOS processing pipeline, including pseudocode and mathematical scoring formulas.

## Content

### The 10-Step Processing Loop

1.  **Ingestion**: Citizen uploads a ticket (description, photograph, raw coordinates) to `/api/v1/complaints`.
2.  **Linguistic Classification (NLP)**: The text is tokenized. A fine-tuned transformer model (DistilBERT) predicts the issue category (e.g., `Road Damage`) and extracts details.
3.  **Visual Classification (CV)**: The image passes to a YOLOv8 bounding-box detector to locate potholes or cracks, and an EfficientNet classifier scores visual severity.
4.  **Spatial-Temporal Triage**: The PostGIS database queries active `Incidents` within a 120-meter buffer.
5.  **Duplicate Assessment**: A similarity engine evaluates combined cosine similarity (text + image + distance). If $\text{Similarity} \ge 0.82$, the complaint is linked to the existing `Incident`.
6.  **Recurrence Analysis**: The database checks for historical complaints at the coordinates over the past 90 days.
7.  **Impact Rating**: Exposure is calculated based on population density and proximity to key assets (schools/hospitals).
8.  **Prioritization Ranking**: The incident is assigned a Priority Score (0-100) using a weighted MCDA formula.
9.  **Constrained Optimization**: Google OR-Tools solves an Integer Linear Programming model, outputting optimal dispatch recommendations.
10. **Explainable AI (XAI)**: SHAP values and cost-benefit arguments are compiled, and the recommendations are presented on the supervisor's dashboard.

---

### Core Pipeline Loop Pseudocode
The following pseudocode outlines the execution sequence of the core processing loop when a new complaint is received:

```python
def process_new_complaint(complaint_data):
    # Step 1 & 2: NLP Analysis
    nlp_results = nlp_model.predict(complaint_data.description)
    category = nlp_results.category
    urgency_tag = nlp_results.urgency
    
    # Step 3: Computer Vision Analysis
    cv_results = cv_model.detect_fault(complaint_data.image_path)
    cv_severity = cv_results.severity_score # 0 - 100
    
    # Step 4 & 5: Spatial-Temporal Duplicate Checks (PostGIS Buffer)
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

### Priority Score Weighted Formula
The priority score determines queue rank and is calculated as:

$$
\text{Priority} = w_s \cdot S + w_p \cdot P_e + w_r \cdot R + w_v \cdot V_i + w_f \cdot F_r
$$

Where:
*   $S$: Severity score (0-100).
*   $P_e$: Population exposure factor.
*   $R$: Recurrence index (counts over past 90 days).
*   $V_i$: Location vulnerability index (proximity to hospitals, schools).
*   $F_r$: Localized environmental flood risk probability.
*   $w_s, w_p, w_r, w_v, w_f$: Variable weights. Target baseline weights: $w_s = 0.30, w_p = 0.20, w_r = 0.15, w_v = 0.15, w_f = 0.20$.

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Proposed Solution](01-proposed-solution.md)
- [Priority Engine](../06-ai-ml/09-priority-engine.md)
- [Resource Optimization](../06-ai-ml/10-resource-optimization.md)
- [Duplicate Detection](../06-ai-ml/05-duplicate-detection.md)
