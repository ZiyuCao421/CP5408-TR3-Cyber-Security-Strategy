# CP5408: Cyber Security Strategy, Governance and Risk Management

**Repository:** [CP5408-TR3-Cyber-Security-Strategy](https://github.com/ZiyuCao421/CP5408-TR3-Cyber-Security-Strategy)  
**Case organisation:** DJI (Da-Jiang Innovations)  
**Purpose:** Coursework learning record and staged preparation for Assignment 1

## Overview

This repository records the connected analysis developed across Weeks 1–5 of CP5408. DJI is used as a continuous case study so that organisational context, risk identification, quantitative assessment, evidence quality, strategy, and implementation planning remain aligned.

The overall sequence is:

**Understand the organisation → identify and prioritise risks → estimate losses and treatment effects → examine evidence and uncertainty → develop strategy, KPIs, initiatives, and a roadmap.**

> **Evidence limitation:** Unless explicitly supported by a cited source, numerical values are assessment estimates or assumptions rather than verified DJI internal data. Week 5's course-provided incident dataset is synthetic and must not be described as actual DJI incident data.

## Week-by-week progress

### Week 1 — Organisational context and information assurance

**Core question:** What needs protecting, and why does cybersecurity matter to DJI?

The work establishes DJI's organisational and industry context, identifies key assets and stakeholders, and applies information assurance concepts to realistic cyber risks.

Key activities:
- Describe the organisation, products and services, technologies, data, geographic scope, and stakeholders.
- Apply confidentiality, integrity, availability, authentication, nonrepudiation, and accountability where relevant.
- Map assets to threats, vulnerabilities, risk statements, and possible controls.
- Distinguish strategic, tactical, and operational security decisions.
- Connect risk management to governance, accountability, and risk-based strategy principles.

The selected core asset is the **drone flight-control and navigation systems**.

**Stage output:** Organisational profile, initial asset and risk analysis, information-assurance analysis, and governance considerations.

### Week 2 — Risk statements and risk register

**Core question:** What can go wrong, how serious could it be, and who should own the risk?

The Week 1 context is developed into formal risk statements and a structured risk register. Risk statements follow a cause–event–impact pattern and are evaluated using the Practical 2 qualitative likelihood and impact scale.

The three risks selected for quantitative analysis are:

| Risk ID | Risk focus | Likelihood | Impact | Qualitative score |
|---|---|---:|---:|---:|
| R3 | FlightHub administrator credential compromise and potential fleet-data exposure | 4 | 4 | 16 |
| R7 | Credential stuffing leading to customer-account takeover | 4 | 4 | 16 |
| R1 | GPS spoofing affecting drone navigation and potentially causing a safety incident | 3 | 5 | 15 |

These scores are **qualitative ranking indices**, not measured quantities and not directly comparable with dollar-denominated loss estimates.

Treatment directions carried forward:
- **R3:** Reduce likelihood through phishing-resistant MFA and stronger privileged-access controls.
- **R7:** Reduce likelihood through credential-stuffing detection, MFA, and authentication safeguards.
- **R1:** Reduce impact through resilient navigation, GPS-anomaly response, and appropriate fail-safe behaviour.

**Stage output:** Formal risk statements, a draft risk register, priority ranking, risk owners, and proposed treatment options.

### Week 3 — Security metrics, ALE, treatment effects, and visualisation

**Core question:** What is the estimated annual loss, and how might proposed controls change it?

The Practical 3 notebook models R3, R7, and R1 using:
- **ARO** — annualised rate of occurrence.
- **SLE** — estimated loss from one occurrence.
- **ALE** — ARO × SLE.
- Residual ARO and SLE after a proposed treatment.
- Residual ALE, estimated risk reduction, net benefit, and benefit-cost ratio (BCR).
- Visualisations comparing ALE, residual ALE, control cost, BCR, exposure, and qualitative risk ratings.

Where DJI-specific evidence is unavailable, inputs such as incident frequency, loss per event, control cost, and percentage reduction must be labelled as **assessment assumptions**. A BCR below 1 does not automatically mean a control should be rejected: safety, legal, privacy, and reputational considerations may justify treatment.

**Stage output:** Runnable Jupyter notebook, generated summary tables and figures, treatment calculations, and an assumptions log.

### Week 4 — Data quality, evidence, uncertainty, and robustness

**Core question:** How much confidence should decision-makers place in the estimates?

Week 4 examines the evidence and assumptions underlying Week 3. It distinguishes measurements from metrics, classifies data scales, evaluates source reliability, expresses uncertainty through low/most-likely/high scenarios, tests whether rankings or BCR decisions change, and checks whether figures support defensible management conclusions.

Key principles:
- Distinguish observed evidence, external benchmarks, proposed future sources, and assessment assumptions.
- Treat likelihood and impact ratings—and the matrix-derived score—as ordinal assessments rather than interval measurements.
- Treat ARO, SLE, and cost as quantitative estimates whose arithmetic is meaningful but whose accuracy depends on input quality.
- Do not describe scenario bounds as statistical confidence intervals unless a statistical method supports that interpretation.
- Make the scope of each figure explicit. Three modelled risks are not automatically the three highest-ALE risks in the full register if the other risks have not been modelled quantitatively.
- Connect each figure to an interpretation and management action.
- Preserve accountability by distinguishing risk owners from implementation teams.

**Stage output:** Source and reliability analysis, uncertainty ranges, robustness checks, improved figure captions, a more specific metric, and an updated assumptions log.

### Week 5 — Descriptive analysis, strategic objectives, and implementation roadmap

**Core question:** What should the organisation do, how will progress be measured, and in what order should the work happen?

Week 5 has two connected parts.

**Part A — Data analysis**
- Distinguish applied analysis from exploratory analysis.
- Calculate descriptive statistics and examine how outliers affect them.
- Inspect and clean a course-provided synthetic security-incident dataset.
- Record decisions about inconsistent labels, monetary formats, missing values, zero costs, incompatible severity scales, and outliers.
- Compare alternative cleaning choices and preserve a traceable cleaning log.
- Derive example ARO and SLE ranges from the teaching dataset and explain why those figures may not describe DJI.

**Part B — Strategy and implementation**
- Define three strategic cybersecurity objectives linked to business needs and priority risks.
- Define KPIs with a baseline—or a plan to establish one—a target, a data source, and an owner.
- Propose and prioritise initiatives across **people, process, and technology**.
- Build a three-year roadmap with time period, accountable role, dependencies, milestones, and assumptions.
- Explain delivery constraints, residual risks, and ethical or legal considerations that affect sequencing.

The Practical 5 notebook's incident records are **synthetic teaching data**, not observed DJI incidents. Their results support learning and method testing; they must not be presented as DJI operational measurements.

**Stage output:** Completed Practical 5 worksheet, notebook results and cleaning log, strategic objectives, KPI definitions, initiative priorities, and a three-year roadmap.

## Continuity of the three priority risks

| Risk | Main concern | Treatment direction | Strategic connection |
|---|---|---|---|
| R3 | Privileged-access compromise could expose enterprise fleet information and disrupt services. | Strengthen identity assurance and privileged-access governance. | Improve protection and monitoring of critical cloud services. |
| R7 | Credential stuffing could compromise customer accounts and expose account or flight information. | Improve authentication safeguards and detection of automated abuse. | Reduce account-takeover exposure and improve identity-related monitoring. |
| R1 | GPS spoofing or navigation interference could affect flight behaviour and create safety consequences. | Improve resilient navigation, anomaly response, and fail-safe capability. | Protect flight safety and demonstrate responsible risk governance. |

Maintain these risk IDs across the worksheets, notebook, KPIs, initiatives, and roadmap. If later evidence or sensitivity analysis changes the quantitative ranking, update the rationale and decision; do not silently rewrite the earlier qualitative ratings.

## Working principles

1. **Preserve traceability:** Link each objective and initiative to one or more risks and retain consistent risk IDs.
2. **Do not manufacture evidence:** Never imply access to DJI internal logs, costs, or interviews unless they were actually obtained.
3. **Separate qualitative ranking from quantitative loss:** The Practical 2 score and Week 3 ALE answer different questions.
4. **Make data-cleaning decisions explainable:** Record what changed, why, and how the decision affects results.
5. **Use metrics to support decisions:** A chart or KPI should clarify an action, not merely display a number.
6. **Establish baselines before promising trends:** If no credible baseline exists, baseline collection should be an explicit early milestone.
7. **Balance financial efficiency with obligations:** Do not use BCR alone to decide safety-critical or legally significant controls.
8. **Plan across people, process, and technology:** Cybersecurity strategy is broader than selecting technical products.
9. **Assign accountable owners and respect dependencies:** Each roadmap initiative should have an owner, prerequisite, and completion measure.
10. **Keep uncertainty visible:** Use scenario ranges where appropriate and state what additional data would narrow them.

## Suggested repository structure

The following is a suggested organisation for keeping source templates separate from completed work. It does not imply that every listed deliverable has already been finalised or committed.

```text
.
├── README.md
├── Week1/
│   └── Practical1_DJI_Completed.docx
├── Week2/
│   └── Practical2_DJI_Completed.docx
├── Week3/
│   ├── Practical3_DJI_Completed.docx
│   ├── CP5408_Practical_3_DJI_Completed.ipynb
│   └── outputs/
├── Week4/
│   └── Practical4_DJI_Completed.docx
└── Week5/
    ├── Practical5_DJI_Working.docx
    └── CP5408_Practical_5_Student_notebook.ipynb
```

## Current status and next steps

- [x] Establish DJI as the continuous case organisation.
- [x] Carry consistent risk IDs from Practical 2 into the Practical 3 quantitative model.
- [x] Establish an evidence-and-uncertainty review approach for Practical 4.
- [ ] Run and inspect Practical 5 notebook Sections 0–6.
- [ ] Record the cleaning-rule comparison and rationale in Practical 5.
- [ ] Complete the three strategic objectives and KPIs.
- [ ] Prioritise initiatives across people, process, and technology.
- [ ] Complete and check the three-year implementation roadmap.
- [ ] Review Assignment 1 against the course self-check and verify that sources and assumptions are accurately described.

## Disclaimer

This repository is a coursework learning record, not an official DJI risk assessment. It uses public-context reasoning and course-provided teaching data. Estimates, synthetic-data results, proposed metrics, and suggested initiatives must not be represented as DJI's verified internal measurements, approved controls, budgets, or commitments.
