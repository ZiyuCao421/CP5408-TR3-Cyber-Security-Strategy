# Week 5 Assumptions and Data Provenance

This note explains which parts of the Week 5 notebook are course-provided exercises and which interpretations are carried forward from the DJI case developed in Weeks 1–4.

## 1. What changed in the Week 5 notebook

- Added a DJI case-bridge section to explain how the teaching dataset may inform, but cannot directly measure, the selected DJI risks.
- Clarified that the 36 incident records are **synthetic teaching data**, imagined as a five-year dataset from 40 comparable organisations.
- Kept the original descriptive-statistics exercise: the 24 weekly firewall-change-request values and the comparison after adding 0 and 200.
- Kept the teacher's default cleaning settings: `ZERO_COST_RULE = 'missing'`, `MISSING_COST_RULE = 'drop'`, and `OUTLIER_RULE = 'keep'`. These are starting settings for the exercise, not claims about DJI data.
- The cleaning and summary cells standardise inconsistent labels, parse costs, handle missing/zero values according to the selected rules, map severity labels, and calculate category-level counts, cost summaries, ARO, SLE ranges, and ALE ranges.

## 2. What comes from the previous weeks

The DJI case uses three continuing priority risks from Practical 2:

| Risk ID | Risk | Practical 2 rating | Treatment direction |
|---|---|---:|---|
| R3 | FlightHub administrator credential compromise and fleet-data exposure | Likelihood 4 × Impact 4 = 16 | Reduce likelihood through phishing-resistant MFA and stronger privileged-access controls |
| R7 | Credential stuffing leading to customer-account takeover | Likelihood 4 × Impact 4 = 16 | Reduce likelihood through account-abuse detection and MFA |
| R1 | GPS spoofing affecting drone navigation and potentially creating a safety incident | Likelihood 3 × Impact 5 = 15 | Reduce impact through resilient navigation and fail-safe response |

Practical 3 supplies the existing central assessment assumptions for these risks (ARO, SLE, annual control cost, and treatment-effect percentages). Practical 4 adds uncertainty ranges, source-quality notes, and sensitivity analysis. These values remain **assessment estimates**, not verified DJI internal incident frequencies, loss records, or measured control effectiveness.

The Week 5 synthetic dataset does not replace those Week 3–4 values. It is used to practise how data cleaning and descriptive statistics can generate an ARO/SLE range and how sensitive that result is to analytical choices.

## 3. Limits when connecting the teaching data to DJI

- **Phishing** is only a rough conceptual comparison for R7 (credential stuffing/account takeover). It is not a direct measure of DJI credential-stuffing frequency.
- **Data breach** can help illustrate consequences relevant to R3, but it does not directly measure FlightHub administrator compromise.
- The generic **Device compromise** category is not a defensible proxy for R1 GPS spoofing and drone navigation safety. Keep R1's Practical 3–4 assessment range separate unless suitable GPS-interference or drone-safety evidence is obtained.
- The calculated ARO values use the course dataset denominator of 40 organisations over 5 years. They describe the synthetic exercise, not DJI.
- Q1, median, and Q3 from the synthetic costs are descriptive scenario values. They are not statistical confidence intervals and should not be presented as DJI-specific loss ranges.

## 4. How to use the outputs in Practical 5

1. Report the Section 1–2 and Section 3–6 outputs as results from the **course-provided teaching data**.
2. In Part 3b, record the default cleaning run and at least one changed decision setting, explaining why the alternative is defensible.
3. In Part 4, choose a category only as an illustrative analogue, show the formula and denominator, and state why its result may not transfer to DJI.
4. In Parts 5–7, make the strategic objectives, KPIs, initiatives, owners, and roadmap DJI-specific. Where no valid DJI baseline exists, make baseline collection an explicit Year 1 milestone.
5. Do not mix qualitative Practical 2 scores with dollar-denominated ALE as if they were the same kind of measurement.

## Core assumption

The notebook demonstrates an analytical method. It does **not** establish DJI's actual incident rate, typical loss, control effectiveness, current KPI baseline, or approved budget. Any DJI-specific conclusion must be marked as an assessment assumption until supported by suitable organisation-specific evidence.
