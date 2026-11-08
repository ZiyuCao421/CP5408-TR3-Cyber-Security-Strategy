# CP5408: Cyber Security Strategy, Governance and Risk Management

**Repository:** [CP5408-TR3-Cyber-Security-Strategy](https://github.com/ZiyuCao421/CP5408-TR3-Cyber-Security-Strategy)  
**Case Organisation:** DJI (Da-Jiang Innovations)  
**Project:** Cybersecurity Strategy for DJI's Commercial Drone Delivery Ecosystem  
**Assessment:** Assignment 1  
**Status:** Completed

---

## Overview

This repository records the coursework development and final assessment for CP5408: Cyber Security Strategy, Governance and Risk Management.

DJI is used as a continuous case study throughout the project. The final assessment focuses on the **DJI FlyCart 30 commercial cargo drone and DeliveryHub cloud platform**, examining cybersecurity risks associated with aircraft operations, navigation systems, cloud services, operator accounts, communications, and software dependencies.

The work developed progressively across Weeks 1–5, connecting organisational analysis, information assurance, risk identification, quantitative assessment, evidence evaluation, cybersecurity strategy, and implementation planning.

The overall analytical process is:

**Understand the organisation → Identify and prioritise risks → Estimate potential losses → Evaluate evidence and uncertainty → Develop strategy and KPIs → Plan implementation.**

The final deliverables consist of a project report and a supporting Jupyter Notebook containing quantitative calculations, visualisations, assumptions, and sensitivity analysis.

> **Evidence limitation:** This is an academic assessment, not an official DJI security audit. Numerical values are assessment estimates or assumptions unless explicitly supported by cited evidence. Course-provided synthetic incident data must not be interpreted as actual DJI operational data.

## Week-by-week Development

### Week 1 — Organisational Context and Information Assurance

**Core question:** What needs protecting, and why does cybersecurity matter to DJI?

The first stage established DJI's organisational and industry context, identified key assets and stakeholders, and applied information assurance concepts to the case.

Key activities:
- Describe the organisation, products and services, technologies, data, geographic scope, and stakeholders.
- Apply confidentiality, integrity, availability, authentication, nonrepudiation, and accountability.
- Map assets to threats, vulnerabilities, risk statements, and possible controls.
- Distinguish strategic, tactical, and operational security decisions.
- Connect risk management to governance, accountability, and risk-based strategy principles.

The selected core asset was the **drone flight-control and navigation systems**.

**Stage output:** Organisational profile, initial asset and risk analysis, information assurance analysis, and governance considerations.

### Week 2 — Risk Statements and Risk Register

**Core question:** What can go wrong, how serious could it be, and who should own the risk?

The organisational analysis was developed into formal risk statements and a structured risk register. Risk statements followed a cause–event–impact structure and were assessed using the course's five-point likelihood and impact scales.

The three risks selected for quantitative assessment were:

| Risk ID | Risk focus | Likelihood | Impact | Qualitative score |
|---|---|---:|---:|---:|
| R3 | Privileged account compromise and potential operational-data exposure | 4 | 4 | 16 |
| R7 | Credential stuffing leading to customer-account takeover | 4 | 4 | 16 |
| R1 | GNSS spoofing affecting drone navigation and potentially causing a safety incident | 3 | 5 | 15 |

These scores are **qualitative ranking indices**, not measured quantities and not directly comparable with dollar-denominated loss estimates.

Treatment directions carried forward:
- **R3:** Reduce likelihood through phishing-resistant MFA and stronger privileged-access controls.
- **R7:** Reduce likelihood through credential-stuffing detection, MFA, and authentication safeguards.
- **R1:** Reduce impact through resilient navigation, GNSS-anomaly response, and appropriate fail-safe behaviour.

The final report adapts the original practical risk descriptions to the selected FlyCart 30 and DeliveryHub scope. In particular, R3 is framed around DJI unified-account and privileged operator access rather than asserting a current FlightHub or DeliveryHub vulnerability.

**Stage output:** Formal risk statements, a ten-risk register, priority ranking, risk treatment directions, and supporting justification.

### Week 3 — Security Metrics, ALE, Treatment Effects, and Visualisation

**Core question:** What is the estimated annual loss, and how might proposed controls change it?

The quantitative model examines R1, R3, and R7 using:

- **ARO** — Annualised Rate of Occurrence.
- **SLE** — Single Loss Expectancy.
- **ALE** — Annual Loss Expectancy.
- Residual ARO and SLE after a proposed treatment.
- Residual ALE and estimated risk reduction.
- Net benefit and Benefit-Cost Ratio (BCR).
- Visualisations comparing current exposure, residual risk, and treatment economics.

The central calculation is:

`ALE = ARO × SLE`

Where DJI-specific evidence is unavailable, inputs such as incident frequency, loss per event, control cost, and percentage reduction are labelled as assessment assumptions.

A BCR below 1 does not automatically mean that a control should be rejected. Safety, legal, privacy, and reputational considerations may justify treatment even where the financial case alone is insufficient.

**Stage output:** Executable Jupyter Notebook, quantitative summary tables, generated figures, treatment calculations, and an assumptions log.

### Week 4 — Data Quality, Evidence, Uncertainty, and Robustness

**Core question:** How much confidence should decision-makers place in the estimates?

Week 4 examined the evidence and assumptions underlying the quantitative assessment. It distinguished measurements from metrics, considered data scales, evaluated source reliability, and used Low / Most Likely / High scenarios to test the robustness of results.

Key principles:
- Distinguish observed evidence, external benchmarks, proposed future sources, and assessment assumptions.
- Treat likelihood and impact ratings, and matrix-derived scores, as ordinal assessments rather than interval measurements.
- Recognise that ARO, SLE, and cost estimates depend on the quality of their underlying inputs.
- Do not describe scenario bounds as statistical confidence intervals without a supporting statistical method.
- Make the scope and limitations of each figure explicit.
- Connect each figure to an interpretation and management action.
- Distinguish risk owners from implementation teams.

The final assessment retains these principles by documenting assumptions, explaining evidence limitations, and avoiding claims that scenario estimates represent verified DJI measurements.

**Stage output:** Evidence and reliability review, uncertainty ranges, robustness checks, improved figure interpretations, and an updated assumptions log.

### Week 5 — Descriptive Analysis, Strategic Objectives, and Implementation Roadmap

**Core question:** What should the organisation do, how will progress be measured, and in what order should the work happen?

Week 5 connected data analysis with strategic planning.

**Part A — Data Analysis**
- Distinguish applied analysis from exploratory analysis.
- Calculate descriptive statistics and examine the effect of outliers.
- Inspect and clean the course-provided synthetic security-incident dataset.
- Record decisions involving inconsistent labels, monetary formats, missing values, zero costs, severity scales, and outliers.
- Compare alternative cleaning choices and preserve a traceable cleaning log.
- Derive example ARO and SLE ranges from teaching data while explaining why they may not describe DJI.

**Part B — Strategy and Implementation**
- Define three strategic cybersecurity objectives linked to business needs and priority risks.
- Define KPIs with baselines or baseline-establishment plans, targets, data sources, and accountable owners.
- Propose and prioritise initiatives across **people, process, and technology**.
- Develop a three-year roadmap with time periods, responsible roles, dependencies, and milestones.
- Consider delivery constraints, residual risks, ethical responsibilities, and regulatory requirements.

The Practical 5 incident records are synthetic teaching data. They support learning and method testing and must not be presented as actual DJI operational incidents.

**Stage output:** Strategic objectives, KPI definitions, initiative priorities, governance arrangements, and a three-year implementation roadmap.

## Continuity of the Three Priority Risks

The three priority risks are maintained across the practical exercises, quantitative notebook, final report, strategic objectives, and implementation roadmap.

| Risk | Main concern | Treatment direction | Strategic connection |
|---|---|---|---|
| R3 | Privileged-access compromise could expose operational information or disrupt services. | Strengthen identity assurance and privileged-access governance. | Protect cloud services and monitor account activity. |
| R7 | Credential stuffing could compromise customer or operator accounts. | Improve authentication safeguards and detection of automated abuse. | Reduce account-takeover exposure. |
| R1 | GNSS spoofing or navigation interference could affect flight behaviour and create safety consequences. | Improve navigation resilience, anomaly response, and fail-safe capability. | Protect flight safety and support responsible risk governance. |

The qualitative risk scores and quantitative loss estimates answer different questions. They are therefore retained as separate analytical measures.

## Working Principles

1. **Preserve traceability:** Link each strategic objective and initiative to one or more risks, retaining consistent risk IDs.
2. **Do not manufacture evidence:** Do not imply access to DJI internal logs, costs, or interviews unless they were actually obtained.
3. **Separate qualitative ranking from quantitative loss:** Qualitative risk scores and ALE calculations are different types of measures.
4. **Make data-cleaning decisions explainable:** Record what changed, why, and how the decision affects results.
5. **Use metrics to support decisions:** A chart or KPI should clarify an action, not merely display a number.
6. **Establish baselines before promising trends:** Where no credible baseline exists, baseline collection must be an explicit milestone.
7. **Balance financial efficiency with obligations:** Do not use BCR alone to decide safety-critical or legally significant controls.
8. **Plan across people, process, and technology:** Cybersecurity strategy is broader than selecting technical products.
9. **Assign accountable owners and respect dependencies:** Each roadmap initiative should have an owner, prerequisite, and completion measure.
10. **Keep uncertainty visible:** Use scenario ranges where appropriate and state what additional data would improve confidence.

## Final Project Deliverables

The completed assessment is supported by two principal deliverables:

| Deliverable | Description |
|---|---|
| Final Project Report (DOCX/PDF) | Presents the organisational context, ten-risk register, quantitative and qualitative assessment, cybersecurity strategy, governance, and three-year implementation roadmap. |
| Completed Risk Analysis Notebook (IPYNB) | Contains quantitative calculations, assumptions, visualisations, sensitivity analysis, and validation outputs. |

The report and notebook should be considered together. The report presents the management analysis and recommendations, while the notebook provides computational support for the quantitative results.

## Three-Year Strategic Roadmap

| Period | Main focus |
|---|---|
| Year 1 (Months 0–12) | Identity and account protection, flight-safety and navigation resilience, regulatory monitoring, and initial critical dependency inventory. |
| Year 2 (Months 13–24) | Incident data and loss-accounting standard, secure software and supplier assurance, and control-operation monitoring. |
| Year 3 (Months 25–36) | Market and supply-chain resilience, cross-functional incident and safety exercises, and continuous assurance. |

The roadmap is a proposed planning framework. Role assignments, costs, control effectiveness, and milestones should be validated against actual organisational resources and operational evidence before implementation.

## Evidence, Assumptions, and Limitations

This project is an academic assessment based on public information, course materials, and explicitly stated assessment assumptions.

The following limitations apply:
- Public sources do not provide access to DJI's internal incident logs, security budgets, or operational loss records.
- ARO, SLE, control costs, and treatment-effectiveness values are scenario estimates rather than verified company data.
- Historical security research is used to explain relevant attack mechanisms, not to claim that current FlyCart 30 or DeliveryHub systems have the same vulnerabilities.
- Sensitivity scenarios are not statistical confidence intervals.
- Proposed KPIs, controls, and roadmap activities are recommendations, not confirmed DJI commitments or existing operational targets.

The assessment distinguishes documented evidence from assumptions, analytical interpretation, and proposed management actions.

## Academic Contribution and AI Use

The project's research direction, conceptual framework, cybersecurity knowledge structure, risk identification and prioritisation, assessment assumptions, analytical decisions, interpretation of results, and strategic recommendations were developed through my own coursework, research, and independent judgement.

Generative AI tools were used to assist with document formatting and layout-related adjustments. The final content was reviewed by the author, who takes responsibility for the submitted work.

## Conclusion — Project Completion Summary

This project brings together the main CP5408 learning activities into a completed cybersecurity risk management and strategy assessment for DJI's commercial drone delivery ecosystem.

It progresses from organisational analysis and risk identification to quantitative risk assessment, evidence evaluation, strategic objectives, governance, and a three-year implementation roadmap. More importantly, it demonstrates how technical cybersecurity risks can be connected to business continuity, operational safety, accountable decision-making, and organisational strategy.

Through this work, I gained a more structured understanding of how cybersecurity risk management moves from identifying potential threats to evaluating their consequences and translating findings into practical management actions.

**The CP5408 Assignment 1 project is now complete.** This repository is retained as a record of the coursework development, analytical process, and final assessment deliverables.

---

**Disclaimer:** This repository is an academic project. It does not represent DJI's official security posture, internal measurements, approved controls, budgets, or organisational commitments.
