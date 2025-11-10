# MSc Dissertation: Predictive Early Warning System for NHS Cancer Services

This repository contains the complete codebase for a Master of Science (MSc) dissertation focused on modelling and mitigating systemic strain within the UK's National Health Service (NHS).

The project develops a **Predictive Early Warning System (EWS)** to quantify the risk of NHS trusts breaching the critical **62-day cancer waiting time standard**, using the breach as a proxy for organisational system failure.

---

## 📌 Research Overview

The system leverages **Cox Proportional Hazards (CoxPH) Survival Analysis**, applied to more than **410,000** historical NHS operational observations.  
The goal is to shift NHS monitoring from reactive audit to **proactive, data-driven resource allocation**.

---

## 🧠 Methodology

### Survival Analysis  
CoxPH modelling was used to estimate hazard ratios for breach risk at the trust level. Model development included:

- proportional hazards checks  
- time-splitting where required  
- robust variance estimation  
- trust-level and pooled modelling

### Feature Engineering  
Raw NHS data was transformed into deeper system indicators, including:

- **Activity Diversity Index (ADI)**  
- **Emergency-to-Elective Ratio (EER)**  
- Capacity and flow-based structural variables  
- Referral pattern indicators  

These features aim to capture operational pressure and systemic strain.

---

## 📊 Outputs

The final artefact generates:

- **Trust-specific hazard ratios**
- **Predicted risk trajectories**
- **Counterfactual policy simulations** (capacity increases, referral changes, etc.)

This enables NHS analysts and policymakers to prioritise interventions with the highest marginal impact.

---

## 📁 Repository Structure


