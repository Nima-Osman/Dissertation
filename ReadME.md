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

<p><a href = "assets/Dissertation Final version.pdf"  download>Complete dissertation pdf file</a></p>
<p><a href = "assets/1. EDA.ipynb"  download>EDA notebook</a></p>
<p><a href = "assets/2. data cleaning hospital activity.ipynb"  download>Data cleaning notebook</a></p>
<p><a href = "assets/3. final dataset merging.ipynb"  download>Final dataset merging notebook</a></p>
<p><a href = "assets/final_merged_complete_with_ml_features (2).xlsx"  download>final dataset created</a></p>
<p><a href = "assets/Copy_of_4_Final_dataset_processing.ipynb"  download>CoxPH model creation notebook</a></p>


## 🗂 Data

The dataset includes over **410k** operational observations from NHS trusts, covering:

- cancer waiting time pathways  
- elective and emergency admissions  
- waiting list patterns  
- trust-level operational indicators  

Sensitive raw data is excluded, with instructions for authorised reconstruction provided in `/data`.

---

## 🛠 Implementation Notes

The codebase includes:

- ingestion scripts
- EDA
- Merging of the datasets  
- engineered feature builders  
- model training modules  
- simulation utilities  


flowchart TD

    %% --- 1. Statistical Output (Input Phase) ---
    A["
    **1. Statistical Output (Input Phase)**

    **Block Type:** Input (Start)

    **Fitted CoxPH Model Parameters**
    ---------------------------------
    **Hazard Ratios (HRs):**
    • Activity Diversity: **2.943**
    • Daycase Ratio: **0.8784**
    • Emergency Ratio: **0.8314**

    (Output → Apply to Current Operational Data)
    "] --> B


    %% --- 2. Predictive Calculation (Processing Phase) ---
    B["
    **2. Predictive Calculation (Processing Phase)**  
    *(BreachRiskPredictor Class)*

    **Input**
    • Current Trust Operational Data  
      (Volumes, FTE, Ratios)

    **Process**
    • Apply HRs to current trust data  
    • Compute Predicted Survival Function

    **Output**
    • Trust Risk Score  
    • Forecast: Predicted Time to Breach (T)  
      *e.g., T = 18 months*
      
    (Output → Policy Diagnosis & Action Ranking)
    "] --> C


    %% --- 3. Decision & Policy Output (Output Phase) ---
    C["
    **3. Decision & Policy Output (Output Phase)**

    **Process: Policy Diagnosis & Action Ranking**
    • Compare trust's current ratios to optimal thresholds

    **Decision 1 — Highest Risk**
    • Diagnose failure cause  
      - Identify HR > 1  
      - e.g., Activity Diversity too high

    **Decision 2 — Mitigation**
    • Diagnose resilience gaps  
      - Identify HR < 1  
      - e.g., Daycase Ratio or Referral Conversion too low

    **Output (End)**
    **Tailored Policy Recommendations:**
    • Reduce Service Breadth  
    • Increase Daycase Capacity by *X%*  
    "] 
