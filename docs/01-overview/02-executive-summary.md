# Executive Summary

## Purpose
This document provides a simple, high-level summary of the DecisionOS Civic system, our deployment approach, and the feasibility of building this for our final-year project.

## Content

### The Core Problem
Conventional grievance portals (like citizen complaint apps or city websites) act as simple message logs. They receive complaints, route them manually to departments, and track tickets. They do not help city offices understand:
*   Which issues are most critical or urgent.
*   Whether multiple complaints refer to the exact same problem.
*   How to allocate limited teams, vehicles, and budgets to get the most work done.

### The Solution
DecisionOS Civic acts as an **intelligent support system** for municipal officers. It does not replace current systems; instead, it consumes complaint data, runs AI models to clean and group duplicates, ranks them by urgency, and recommends the best schedule for sending workers to fix the problems.

---

### Two Project Modes
To ensure our final-year project is fully feasible without needing access to real government databases or credentials, we define two modes of operation:

*   **Mode A: Academic / Demo Mode (Must Build)**: 
    *   This is what we will build and show to the project guide and examiners.
    *   It runs independently using public datasets (like weather and demographic data), citizen photos we collect ourselves, and synthetic (simulated) data for testing resource scheduling.
*   **Mode B: Government Pilot Mode (Future Scope)**:
    *   This is how the system would connect to a real municipality in the future.
    *   It would consume live data from official municipal systems (like CPGRAMS or UMANG) via secure APIs and return recommendations to city officers.

---

### Project Component Feasibility
The table below outlines our team's assessment of how feasible it is to implement each module of DecisionOS Civic for our final-year project:

| Project Component | Feasibility Rating | What We Need |
|---|---|---|
| **Web Platform (UI)** | **95%** | React and Map libraries (Leaflet) to display complaints on a city map. |
| **NLP Text Classifier** | **90%** | Pre-trained text models (BERT) to classify complaint text automatically. |
| **Computer Vision (CV)** | **85%** | Object detection models (YOLOv8) trained on road damage photos. |
| **Duplicate Detector** | **90%** | Simple calculations to check if reports are near each other and describe the same issue. |
| **Risk Mapping** | **85%** | Standard time-series models to predict flooding or road decay probability. |
| **Resource Allocator** | **85%** | Basic optimization solvers (Google OR-Tools) to schedule workers and trucks. |
| **What-if Simulator** | **80%** | Simple calculators to compare current resolution times against simulated resource changes. |
| **Real Government Integration**| **40%** | Not feasible for a college project; marked as future scope (Mode B). |

---

### Sandbox Municipality (Coimbatore Pilot)
For our project demonstration, we will set up a mock environment called the **Coimbatore Municipal Decision Intelligence Sandbox**. We will create a fictional but realistic set of departments (Roads, Water, Waste, Drainage) with specific worker pools and budgets to demonstrate how the AI schedules repairs dynamically.

---
*Source basis: DecisionOS Civic source document*

## Related Documents
- [Project Overview](01-project-overview.md)
- [Project Vision](03-project-vision.md)
- [Proposed Solution](../03-solution/01-proposed-solution.md)
- [Development Roadmap](../14-implementation/02-development-roadmap.md)
