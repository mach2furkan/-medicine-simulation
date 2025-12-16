# -medicine-simulation

```markdown
# 🧠🫀 Advanced Real-Time Multi-Organ ICU Physiology Simulator

> **High-Fidelity, Real-Time, Causally Coupled ICU Patient Simulation Engine**  
>  
> 🎓 Education • 🔬 Research • ⚙️ Systems Modeling  
>  
> ⚠️ **NOT a medical device — NOT for clinical use**

---

## 📌 Overview

This repository contains a **real-time, multi-organ ICU patient simulation engine** that models the human body as a **continuously evolving physiological system**.

Unlike traditional dashboards, mock simulators, or rule-based demos:

- ❌ Values are **not static**
- ❌ Widgets are **not independent**
- ❌ Scores are **not hard-coded**

✔ Every parameter is computed  
✔ Every change has a physiological cause  
✔ Every intervention propagates across organs  
✔ Every outcome is explainable  

This project behaves as a **living digital patient**, not a UI demo.

---

## 👁️ Visual Concept (System-Level View)


::contentReference[oaicite:0]{index=0}


---

## 🎯 Core Objectives

- Build a **true system-of-systems physiology engine**
- Demonstrate **cause → effect → outcome** chains in critical illness
- Simulate **delayed treatment effects** (PK/PD, fluids, antibiotics)
- Enable **explainable deterioration and recovery**
- Drive a **live real-time dashboard** via WebSocket

---

## 🧩 System Architecture (System-of-Systems)


::contentReference[oaicite:1]{index=1}


```

Lung ──→ Oxygenation ──→ Tissue O₂ Delivery ──→ Metabolism
│                                         │
└─→ CO₂ Clearance ────────────────────────┘

Heart ──→ MAP ──→ Brain (CPP, GCS)
└─→ Kidney (GFR, UO, Creatinine)

Sepsis / Shock / ARDS → Multi-Organ Coupling → Outcome

```

Each subsystem evolves continuously using **ODE-based dynamics** and influences the others at every simulation step.

---

## 🧬 Simulated Physiological Domains

### ❤️ Hemodynamics
- HR, SV, CO, MAP, SBP, DBP
- SVR, CVP, ScvO₂
- Shock Index
- Windkessel-based arterial pressure dynamics
- Fluid responsiveness & vasopressor PK/PD

### 🫁 Respiratory
- FiO₂, PEEP, RR, VT
- PaO₂, PaCO₂, SpO₂
- Dead space (Vd/Vt), shunt (Qs/Qt)
- Lung compliance & resistance
- ARDS recruitment / derecruitment

### 🧠 Neurological
- ICP, CPP, CBF
- GCS (3–15)
- BIS (0–100)
- FOUR Score
- Cerebral autoregulation

### 🧪 Renal & Fluids
- GFR, urine output
- Creatinine dynamics
- Plasma volume & fluid balance
- Capillary leak (sepsis)

### 🔥 Metabolic & Systemic
- Lactate kinetics
- Acid–base (pH)
- Core temperature
- Oxygen delivery (DO₂) vs consumption (VO₂)
- Oxygen debt & repayment

---

## ⚙️ Real-Time Simulation Engine


::contentReference[oaicite:2]{index=2}


- ⏱ Time step: **0.1–1.0 s** (default 0.25 s)
- 🧮 Numerical integration: **RK4** (Euler fallback)
- 🔄 Continuous ODE-based evolution
- 🧠 Delayed intervention effects
- 📡 Live WebSocket streaming to UI

### Deterministic Update Loop

```

Events
→ Delays (PK/PD)
→ ODE Integration
→ Derived Metrics
→ Organ Injury
→ Scores & Risk
→ Explainability
→ WebSocket → UI

```

No UI value updates outside this loop.

---

## 🚀 20 Advanced Active Modules (All Enabled)


::contentReference[oaicite:3]{index=3}


1. DO₂ / VO₂ balance & oxygen content  
2. Dynamic hemoglobin & hemodilution  
3. Microcirculation failure index  
4. Heart–lung coupling (PEEP ↔ venous return)  
5. Autonomic nervous system dynamics  
6. Myocardial oxygen demand (MVO₂)  
7. Electrolyte-driven arrhythmia risk  
8. Lung recruitment / derecruitment logic  
9. Irreversibility (point-of-no-return) tracker  
10. Delayed treatment effects (PK/PD)  
11. Vasopressor & sedation effect-site models  
12. Simplified DIC / microthrombosis  
13. Multi-compartment V/Q mismatch  
14. Cumulative organ injury integrators  
15. Decision Quality Score (education metric)  
16. Shock phenotypes (warm, cold, cardiogenic, neuro)  
17. Realistic monitor artifacts & noise  
18. Oxygen debt hysteresis  
19. Explainable causal attribution engine  
20. Automatic end-of-case clinical summary  

---

## 📊 Clinical Scores (Computed, Not Hard-Coded)

All scores are derived **directly from physiology**:

- qSOFA  
- SOFA  
- APACHE II (approximate)  
- SAPS II (approximate)  
- Shock Index  
- Mortality Risk (logistic model)  
- Time-to-Deterioration (trend forecast)

---

## 🖥️ Live Dashboard


::contentReference[oaicite:4]{index=4}


The dashboard displays:
- Real-time vitals
- Continuous trend graphs
- Trauma & sepsis panels
- Predictive analytics
- Advanced hemodynamics
- Explainable deterioration causes

All values originate from **one internal physiological state**.

---

## 🛠 Technology Stack

**Backend**
- Python 3.11+
- NumPy / SciPy
- Custom ODE engine (RK4)
- FastAPI + WebSocket

**Frontend**
- React
- Real-time charting
- ICU-style dark UI

---

## 📂 Repository Structure

```

/engine
simulation_engine.py
patient_model.py
integrators.py
events.py
interventions.py
scoring.py
explainability.py

/api
websocket_server.py

/ui
dashboard/
charts/
panels/

tests/
scenario_regression_tests.py

```

---

## 🧪 Validation Scenarios

- Normal physiology  
- Sepsis → septic shock  
- ARDS with ventilation response  
- Hemorrhagic shock  
- Fluid & vasopressor resuscitation  
- Recovery vs irreversible failure  

Each scenario is validated for **physiological plausibility**, not cosmetic output.

---

## ⚠️ Disclaimer

> **Educational & research use only.**  
> This software is **not a medical device**, **not clinically validated**, and **must not be used for patient care**.

---

## 👤 Project Lead

**Furkan Aşkın**  
Advanced Physiology & Systems Simulation  
Computer Engineering / Biomedical Systems

---

## ⭐ Why This Project Stands Out

✔ True continuous physiology  
✔ Explainable cause–effect chains  
✔ ICU-level complexity  
✔ Real-time simulation  
✔ Academic & engineering depth  
✔ Not a toy — not a demo  

---

## 🔜 Planned Extensions

- Patient-specific parameter fitting  
- PBPK drug models  
- Multi-patient simulation  
- Reinforcement-learning controllers  
- Exportable training reports

