# CS524: Introduction to Optimization

Selected projects from CS524 (Introduction to Optimization) at the University of Wisconsin–Madison, Spring 2025. Implemented in Julia using JuMP and HiGHS.

---

## Final Project — Blood Transfusion Supply Chain Optimization

**Topic:** Blood Transfusion Supply and Demand

Motivated by Bucky's Blood Drive at UW–Madison, this project models the hospital blood bank inventory problem as a **maximum flow problem** on a bipartite compatibility graph to determine whether current blood supplies can meet patient demand.

### Problem Formulation

- **Sets:** 8 ABO/Rh blood types — A+, A−, B+, B−, O+, O−, AB+, AB−
- **Decision variable:** `x[i,j]` = units of blood type `i` transfused to patient needing type `j`
- **Objective:** Maximize total units transfused (maximize flow)
- **Constraints:**
  - Supply constraint: outflow ≤ available inventory per blood type
  - Demand constraint: inflow ≤ patient demand per blood type
  - Compatibility constraint: only medically compatible transfusions are allowed (e.g., O− is universal donor)
  - Non-negativity and integrality

### Data

Supply data sourced from Canadian Blood Services' real-time "days of inventory on hand" metric. Demand (4–6 units per type) generated randomly to simulate a realistic hospital scenario.

### Results

The model returned a maximum flow equal to the total demand (40 units), confirming the blood inventory is sufficient to meet all patient needs under the given supply levels and compatibility rules.

### Tech Stack

- Julia
- JuMP (mathematical programming framework)
- HiGHS (LP/MIP solver)

### Running

```bash
# Install Julia, then:
julia --project=. project/project.ipynb
# Or open in Jupyter with the Julia kernel
```

---

## Additional Notebooks

| File | Topic |
|---|---|
| `linear-programming.ipynb` | LP formulation and solving with JuMP |
| `network-flow.ipynb` | Network flow and transportation problems |

---

## Course Info

CS/ECE/ISyE 524 — Introduction to Optimization, Spring 2025  
University of Wisconsin–Madison
