<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>MSc Dissertation — Predictive Early Warning System for NHS Cancer Services</title>
  <meta name="description" content="Predictive Early Warning System (EWS) for NHS Cancer Services — MSc dissertation repository overview." />
  <style>
    :root{--bg:#0f1724;--card:#0b1220;--muted:#94a3b8;--accent:#7c3aed;--text:#e6eef8}
    html,body{height:100%;margin:0;font-family:Inter,ui-sans-serif,system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial;background:linear-gradient(180deg,#071029 0%, #081025 60%);color:var(--text);}
    .wrap{max-width:980px;margin:40px auto;padding:28px;border-radius:16px;background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));box-shadow:0 8px 30px rgba(2,6,23,0.6)}
    header{display:flex;align-items:center;gap:18px}
    h1{margin:0;font-size:1.6rem}
    .meta{color:var(--muted);font-size:0.95rem}
    section{margin-top:20px;padding:18px;border-radius:12px;background:rgba(255,255,255,0.01)}
    h2{margin:0 0 8px 0;color:#f1f5f9}
    p{line-height:1.5;color:var(--muted);margin:8px 0}
    .kbd{font-family:monospace;background:rgba(255,255,255,0.02);padding:4px 8px;border-radius:6px;color:#cfe3ff}
    pre{background:#041025;color:#cfe3ff;padding:12px;border-radius:8px;overflow:auto}
    .grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
    footer{margin-top:18px;color:var(--muted);font-size:0.9rem}
    a{color:var(--accent);text-decoration:none}
    @media (max-width:720px){.grid{grid-template-columns:1fr}}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div>
        <h1>MSc Dissertation: Predictive Early Warning System for NHS Cancer Services</h1>
        <div class="meta">Repository overview • Complete codebase for an MSc dissertation</div>
      </div>
    </header>

    <section>
      <h2>Project Summary</h2>
      <p>
        This repository contains the complete codebase for a Master of Science (MSc) dissertation focused on modeling and mitigating systemic strain within the UK's National Health Service (NHS).
      </p>
      <p>
        The project develops a Predictive Early Warning System (EWS) to quantify the risk of NHS trusts breaching the critical <span class="kbd">62-day</span> cancer waiting time standard, using this breach as a proxy for organizational system failure.
      </p>
    </section>

    <section>
      <h2>Methodology</h2>
      <p>
        The core methodology employs Cox Proportional Hazards (CoxPH) Survival Analysis applied to over <strong>410,000</strong> observations of historical NHS operational data. The analysis was conducted with care to follow best practices in survival analysis, including proportionality checks, time-splitting where necessary, and the use of robust variance estimators where appropriate.
      </p>
      <div class="grid">
        <div>
          <h3>Feature Engineering</h3>
          <p>
            Extensive feature engineering transformed raw operational records into structural indicators such as the <em>Activity Diversity Index</em> and the <em>Emergency-to-Elective Ratio</em>. These engineered features capture systemic pressures and operational modes that correlate with breach risk.
          </p>
        </div>
        <div>
          <h3>Model Outputs</h3>
          <p>
            The final artefact generates trust-specific Hazard Ratios and enables policy simulations. These outputs support a shift from reactive auditing to proactive, evidence-based resource allocation and intervention design.
          </p>
        </div>
      </div>
    </section>

    <section>
      <h2>Data & Scale</h2>
      <p>
        The dataset comprises more than 410,000 operational observations from NHS trusts, spanning multiple years and capturing admissions, waiting lists, cancer pathway metrics, and trust-level attributes. All data handling steps, aggregation logic and de-identification procedures are documented in the <span class="kbd">/data</span> and <span class="kbd">/notebooks</span> folders of the repository.
      </p>
    </section>

    <section>
      <h2>Implementation</h2>
      <p>
        The codebase contains: data ingestion scripts, feature engineering pipelines, model training notebooks, evaluation utilities, and a lightweight results dashboard. The principal survival modeling is implemented using well-tested Python libraries and idiomatic data-science practices (vectorised operations, pipeline modularization, unit-tested utilities where appropriate).
      </p>
      <pre>
# Example (high-level)
# - data/prepare.py      -> loads & sanitises raw records
# - features/engineer.py -> computes Activity Diversity Index, E/E Ratio, etc.
# - models/coxph.py      -> trains CoxPH models per trust and pooled models
# - notebooks/analysis.ipynb -> exploratory analysis & proportionality checks
      </pre>
    </section>

    <section>
      <h2>Policy Simulations & Use Cases</h2>
      <p>
        Using trust-specific hazard functions, the system supports counterfactual simulations: the impact of added capacity, resource reallocation, or changes in referral patterns can be simulated to estimate downstream effects on breach risk. This enables commissioners and policymakers to prioritise interventions where marginal benefit is greatest.
      </p>
    </section>

    <section>
      <h2>Reproducibility & Repository Structure</h2>
      <p>
        The repository is organised to support reproducible research: environment specifications, notebooks used to generate figures, and scripts to reconstruct processed datasets are included. Sensitive raw data is not committed; instructions for authorised access and data recreation are provided in the README.
      </p>
      <pre>
repo/
├─ README.md
├─ data/            # ingestion & de-identification helpers
├─ features/        # feature engineering pipeline
├─ models/          # model training & persistence
├─ notebooks/       # analysis & validation notebooks
└─ dashboard/       # lightweight visualisation of hazards & scenarios
      </pre>
    </section>

    <section>
      <h2>Contact & License</h2>
      <p>
        This MSc dissertation and its codebase are provided for academic and research purposes. See the repository <a href="#">LICENSE</a> and <a href="#">README</a> for usage terms and citation instructions.
      </p>
    </section>

    <footer>
      Generated HTML summary of the dissertation repository — ready to use as an index or README conversion.
    </footer>
  </div>
</body>
</html>
