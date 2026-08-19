# Resource Optimization

## Purpose
This document presents the mathematical model for resource allocation.

## Content
### Mathematical Formulation
The optimization engine solves a constrained resource allocation problem to maximize total resolved civic impact.

#### Objective Function
\[
	ext{Maximize} \quad \sum_{i \in 	ext{Incidents}} 	ext{Impact}(i) \cdot x(i)
\]

Where \(x(i) \in \{0, 1\}\) indicates whether Incident \(i\) is scheduled for resolution.

#### Constraints
1. **Personnel Constraint**:
   \[
   \sum_{i} 	ext{WorkersRequired}(i) \cdot x(i) \le 	ext{Available Workers}
   \]
2. **Vehicle Constraint**:
   \[
   \sum_{i} 	ext{VehiclesRequired}(i) \cdot x(i) \le 	ext{Available Vehicles}
   \]
3. **Budget Constraint**:
   \[
   \sum_{i} 	ext{Cost}(i) \cdot x(i) \le 	ext{Available Budget}
   \]
4. **Working Hours Constraint**:
   \[
   \sum_{i} 	ext{HoursRequired}(i) \cdot x(i) \le 	ext{Available Hours}
   \]

### Implementation Strategy
We utilize **Google OR-Tools** to solve this Integer Linear Programming (ILP) formulation and compare its execution performance against a simple greedy baseline.

![Resource Optimization](../../diagrams/07-resource-optimization.png)
*Figure 7. Optimization dashboard illustrating resource constraints and optimal team allocation output.*

## Related Documents
- [Priority Engine](09-priority-engine.md)
- [Experimental Design](../13-research/04-experimental-design.md)
