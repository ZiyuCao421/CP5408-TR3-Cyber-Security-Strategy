# CP5408 Weekly Practical 04

**Course:** Cyber Security Strategy Governance and Risk Management

**Organisation used throughout:** DJI
**Focus:** Measurement scales, evidence sources, uncertainty ranges, and interpretation checks for the Week 3 risk model.
**Connection to the learning sequence:** Validates the Week 3 model's evidence boundaries and strengthens the assumptions carried into the Week 5 roadmap.

## Completed weekly practical

> **Scope note:** The course-provided worksheet set the prompts. This section presents the completed tables and notebook work; prompts remain in the first column where they are needed to make a response understandable. Claims and estimates are coursework scenario assumptions unless the submission itself identifies a source.

### Submitted response table 1

| Time | Activity |
| --- | --- |
| 10 min | Part 1: raw data, measurement, metric. |
| 15 min | Part 2: data scales and what they allow. |
| 20 min | Part 3: data sources for your risk values. |
| 25 min | Part 4: assumption quality, ranges, and a robustness check in the notebook. |
| 15 min | Part 5: figure check and caption. |
| 10 min | Part 6: Cisco lessons and a better question. |
| 5 min | Part 7: record what you improved. |

### Submitted response table 2

| Example | Raw data | Measurement | Metric |
| --- | --- | --- | --- |
| Example: vulnerability management | Scanner output listing vulnerabilities on hosts. | Number of high-severity vulnerabilities found this month. | Percentage of production hosts with unresolved high-severity vulnerabilities. |
| Example: incident response | Incident tickets and timestamps. | Time between detection and containment for each incident. | Average containment time over the past quarter. |
| Example: security awareness | Phishing simulation results. | Number of users who clicked a simulated phishing link. | Phishing failure rate by business unit. |

### Submitted response table 3

| Area in your organisation | Raw data | Measurement | Metric |
| --- | --- | --- | --- |
| FlightHub privileged-account access | Identity-provider sign-in and MFA enrolment logs. | Number of privileged accounts created without phishing-resistant MFA at the time of creation. | Monthly percentage of new FlightHub privileged accounts enrolled in phishing-resistant MFA within the required period. |
| Customer account protection | WAF, login, password-reset and account-lockout events. | Number of confirmed credential-stuffing attempts and resulting account takeovers in a month. | Monthly confirmed account-takeover rate per 100,000 active accounts, split by application channel. |

### Submitted response table 4

| Data item | Scale | Why | What you may do |
| --- | --- | --- | --- |
| Operating system type: Windows, Linux, macOS | Nominal | Categories with no natural order. | Count; mode; cross-tabulate. No median or mean. |
| Risk rating: Low, Medium, High | Ordinal | Ordered, but the gap between levels is not a fixed amount. | Count; mode; median. No mean; “High is twice Medium” has no meaning. |
| CVSS score 0–10 | Interval (as treated in the seminar) | Numeric, and differences are treated as meaningful. The seminar notes the line between ordinal and interval is fine. | Differences and means, with care. |
| Number of incidents in a month | Ratio | True zero; ratios are meaningful. | All of the above, plus “twice as many”. |
| Estimated incident cost in dollars | Ratio | True zero; proportional comparisons are meaningful. | All of the above. |

### Submitted response table 5

| Value in your notebook | Scale | What you may and may not do with it |
| --- | --- | --- |
| Treatment_Option (Reduce likelihood, Transfer, etc.) | Nominal | Use as labels/categories; count or cross-tabulate. Do not average or rank as a numerical scale. |
| Likelihood_1_to_5 and Impact_1_to_5 | Ordinal | Rank and band them; do not treat the gaps as equal or calculate a meaningful mean. |
| Qualitative score (likelihood x impact) and band | Ordinal | Use for matrix ranking/banding only. A product of ranks is still not an interval or ratio measurement. |
| ARO | Ratio | Calculate rates, multiply by SLE and compare proportions, while disclosing estimation uncertainty. |
| SLE and Control_Cost | Ratio | Calculate differences, totals and ratios; the values remain scenario estimates rather than observations. |
| Likelihood_Reduction_pct | Ratio | Calculate residual ARO and compare percentages, but do not imply precision beyond the supporting evidence. |
| Benefit-cost ratio | Ratio | Compare with 1 and test sensitivity. It inherits uncertainty from ARO, SLE, reduction and cost inputs. |

### Submitted response table 6

| Question | Response |
| --- | --- |
| Why can two reasonable matrices disagree about the same cell? | They use different definitions of likelihood, impact thresholds and band cut-offs. A matrix is a decision aid built from a chosen scale, not a universal measuring instrument. |
| What does that tell you about treating a likelihood x impact score as if it were a measured quantity? | The score is ordinal: it supports prioritisation within its own matrix, but not arithmetic claims such as '16 is twice 8' or a percentage difference between risks. |
| In Assignment 1, what should you state about your matrix so that a reader can interpret your ratings? | State the five-point likelihood and impact definitions, the multiplication/banding rule, the assessment basis and that qualitative scores are used for ranking and bands only. |

### Submitted response table 7

| Source type | Examples | Useful in Assignment 1 for | Watch for |
| --- | --- | --- | --- |
| System data | Logs, SIEM alerts, vulnerability scans, configuration records. | ARO, incident frequency, exposure, control effectiveness. | Narrow view; easy to collect, easy to misread. |
| Process data | Tickets, patching records, incident timelines, training records, budgets. | Detection and recovery time, control cost, process maturity. | Often incomplete or kept for another purpose. |
| Documentary data | Policies, audit reports, annual reports, contracts, industry and government reports. | Company context, legal obligations, SLE components, sector incident rates. | Not specific to your organisation; may be dated or written by a vendor with something to sell. |
| People data | Interviews, surveys, focus groups, expert judgement. | Percentage reductions, qualitative ratings, anything with no recorded history. | Subjective. Record who judged, on what basis, and how confident they were. |

### Submitted response table 8

| Risk ID | Value | Source type | Specific source | How reliable, and why? | What assumption remains? |
| --- | --- | --- | --- | --- | --- |
| R3 | ARO | People / documentary | Public equivalent: Microsoft Digital Defense Report 2024 on identity attacks; organisational source should be 12 months of privileged sign-in and incident records. | Medium for attack context, low for DJI frequency: the public report is broad, while DJI logs were not supplied. | The 0.50 ARO remains a coursework scenario estimate until DJI-specific privileged-account data is available. |
| R3 | SLE | Documentary / process | IBM Cost of a Data Breach Report 2024, supplemented in practice by incident, legal, notification and recovery cost records. | Medium as a cost component benchmark, but not company-specific and not a direct measure of this scenario. | The $350,000 SLE remains a reasoned scenario estimate rather than a DJI loss observation. |
| R7 | ARO | System | The appropriate source is 12 months of FlightHub WAF, identity-provider, fraud and account-recovery logs, deduplicated into confirmed takeovers. | Potentially high after validation because it is event-level organisational data; none was supplied for this coursework case. | The 2.00 ARO is an assessment assumption until the event definition and logs are reviewed. |
| R7 | SLE | Process | Incident tickets, customer-support records, remediation payments and investigation time for confirmed account takeovers. | Potentially medium/high if costs are complete; support records can omit indirect disruption and reputational effects. | The $45,000 SLE is a scenario estimate pending complete cost records. |
| R1 | ARO | Documentary / system | Public equivalent: aviation/GNSS interference advisories; organisational source should be DJI telemetry, anomaly reports and safety-event records. | Low/medium for this use: public notices show the hazard exists but cannot establish DJI event frequency. | The 0.20 ARO is a cautious scenario estimate, not a claim about DJI incidents. |
| R1 | SLE | Process / documentary | Safety investigation files, aircraft replacement costs, insurance/claims data, engineering records and legal-cost estimates for comparable incidents. | Low until scenario scope and cost categories are agreed; severe-event costs vary widely. | The $2,000,000 SLE remains the weakest financial assumption and is tested as a range below. |

### Submitted response table 9

| Risk ID | Input | Current estimate | Evidence or reasoning | Confidence (low / medium / high) | How could it be improved? |
| --- | --- | --- | --- | --- | --- |
| R1 | Impact reduction percentage | 50% | The Week 3 log labels it low confidence. It is a judgement about how VIO fallback and return-to-home reduce consequences, not an observed effectiveness result. | Low | Tested flight scenarios, safety-case review, simulation and post-deployment telemetry for comparable signal anomalies. |
| R1 | SLE | $2,000,000 | A severe-case total combines several uncertain components (response, asset, claims, legal and reputation impacts). | Low | A structured cost model using claims, safety, engineering and legal records; define inclusions consistently. |
| R3 | SLE | $350,000 | It is a scenario estimate for a privileged-account compromise and no DJI incident-cost history was supplied. | Low | Incident-response and business-continuity cost records, plus a documented comparable-incident model. |

### Submitted response table 10

|   | Low | Most likely | High |
| --- | --- | --- | --- |
| Example ARO | 0.10 | 0.25 | 0.50 |
| Example SLE | $300,000 | $500,000 | $900,000 |
| Example ALE | $30,000 | $125,000 | $450,000 |

### Submitted response table 11

| Risk ID | ARO low / likely / high | SLE low / likely / high | ALE low | ALE likely | ALE high |
| --- | --- | --- | --- | --- | --- |
| R3 | 0.25 / 0.50 / 0.75 | $200,000 / $350,000 / $600,000 | $50,000 | $175,000 | $450,000 |
| R7 | 1.00 / 2.00 / 3.00 | $30,000 / $45,000 / $70,000 | $30,000 | $90,000 | $210,000 |
| R1 | 0.10 / 0.20 / 0.30 | $1,000,000 / $2,000,000 / $3,500,000 | $100,000 | $400,000 | $1,050,000 |

### Submitted response table 12

| Question | Response |
| --- | --- |
| Does the order of your three risks stay the same in the low and high cases? If not, which pair swaps? | Yes. The order is R1, R3, R7 in all three aligned low, likely and high scenarios. This is a scenario-bound check, not proof that the ordering is fixed under every combination of inputs. |
| Does any treatment's benefit-cost ratio cross 1 between the low and high case? What would that mean for your recommendation? | Yes. R3 changes from 0.38 to 3.38, R7 from 0.42 to 2.94 and R1 from 0.20 to 2.10. The financial case is sensitive; use staged investment or collect evidence before relying on BCR alone. R1 also needs safety, legal and ethical review. |
| Write one sentence you could use in Assignment 1 to report a range and what it means for the decision. | For the assessed R1 GPS-spoofing scenario, ALE ranges from $100,000 to $1,050,000 (most likely $400,000); the ranking is stable in these scenarios, but the control's BCR ranges from 0.20 to 2.10, so safety justification and stronger effectiveness evidence are required. |

### Submitted response table 13

| Weak justification (as it stands) | Improved justification (source, reasoning, range, remaining assumption) |
| --- | --- |
| R1 impact reduction is 50% because VIO fallback and return-to-home reduce impact. | R1 impact reduction is assessed at 50% (range 25%-60%) because a fail-safe response can limit loss after a GPS anomaly; the range is a judgement pending evidence from representative test flights, simulations and safety-event telemetry. The remaining assumption is that the tested conditions represent operational flights. |

### Submitted response table 14

| Check | Yes / no | What needs fixing? |
| --- | --- | --- |
| Does the figure answer one clear question? Write the question. | Yes | Question: Which of the three selected DJI coursework risk scenarios has the largest estimated annualised loss before treatment? |
| Are the title, axes, units, and legend clear without reading the report text? | Yes | Retain the title 'Current ALE by risk', dollar-formatted x-axis and risk labels. Add 'estimated' in the report caption. |
| Can the reader tell that the values are estimates, not observations? | No | The notebook uses 'estimated' on the axis but the caption must state that ARO and SLE are assessment assumptions, not DJI internal observations. |
| Is it clear what is included and what is left out (for example, only three of ten risks)? | No | State that the figure includes only R1, R3 and R7 selected from the Practical 2 register; it is not a complete enterprise-risk ranking. |
| Could the figure suggest a trend, precision, or comparison the data does not support? | Yes | A bar ranking can look more precise than the inputs warrant. Present ranges in nearby text and avoid interpreting small differences as decisive. |
| Does it point to an action? What should management do differently after seeing it? | Yes | Use R1 as the priority safety-case investigation, while collecting stronger frequency, severity and control-effectiveness evidence before making an investment decision. |

### Submitted response table 15

| Item | Your text |
| --- | --- |
| Figure caption (what it shows, the basis of the values, the date or scope) | Figure 1. Estimated current annualised loss expectancy for three selected DJI coursework risk scenarios (R1, R3 and R7), calculated as ARO x SLE from the most-likely assessment assumptions recorded in the Week 3 notebook (13 October 2026). This is not an observed DJI loss history. |
| One interpretive sentence (what the reader should conclude and do) | R1 has the highest central ALE and remains highest in the aligned range scenarios, so management should prioritise its safety-case evidence and control validation; the financial case alone is uncertain. |

### Submitted response table 16

| Lesson from the case study | How it applies to your analysis or organisation |
| --- | --- |
| 1. Verify that the data you present actually supports the conclusion you draw (production and lab systems were mixed). | Do not treat public identity-attack or GNSS-interference data as DJI incident frequency. Label it as context and separate it from organisation-specific evidence. |
| 2. Manage executive expectations about the accuracy of initial metrics, and ask what they want to know. | Present ALE and BCR as ranges and first estimates. Ask whether management needs a safety decision, a budget decision, or both before refining the metric. |
| 3. Knowing who owns a host is more valuable than knowing what vulnerabilities are on it. | Assign a role owner to each risk and control: for example, Platform Identity Lead for R3/R7 and Flight Safety Engineering Lead for R1. |
| 4. Metrics are not about being pretty; they are about inciting corrective action. | Pair each figure with an action: validate R1 fail-safe effectiveness, improve privileged MFA coverage, and investigate confirmed account takeovers. |
| 5. Do not trend your data until you have a solid baseline. | Do not claim improvement from a single month. Define consistent event criteria and collect a baseline before setting trend targets. |
| 6. Create a sanity check on automated metric-generating processes. | Sample alerts and tickets against raw logs, check exclusions and duplicate handling, and review whether monitoring failures could create false reassurance. |
| 7. There is a trade-off between money spent and the increase in security posture ('how many vulnerabilities is too few?'). | Use BCR as one input, not a veto. R1 may still justify treatment because safety, legal, operational and reputational consequences are not fully represented in the financial estimate. |

### Submitted response table 17

| Your Practical 3 metric | Sharper version (time dimension, scope, owner) |
| --- | --- |
| Example: percentage of privileged accounts using phishing-resistant MFA | Days taken for a new privileged account on the cloud platform to be enrolled in phishing-resistant MFA, reported monthly by the platform team lead |
| Percentage of FlightHub privileged accounts using phishing-resistant MFA | Median days from creation to phishing-resistant MFA enrolment for new production FlightHub privileged accounts, reported monthly by the Platform Identity Lead; review the percentage enrolled within seven days alongside the median. |

### Submitted response table 18

| Question | Response |
| --- | --- |
| Which value did you strengthen today, and with what source? | R1 SLE and impact-reduction assumptions were strengthened by separating the relevant organisational evidence needed (safety, claims, engineering and test-flight records) from public hazard context; no DJI-specific source was supplied, so confidence remains low. |
| What range will you report for your highest-ALE risk? | R1 ALE: $100,000 low, $400,000 most likely and $1,050,000 high, based on ARO 0.10/0.20/0.30 and SLE $1.0m/$2.0m/$3.5m. |
| Did your ranking or any treatment decision change? If so, how? | The R1-R3-R7 ordering stays the same in the aligned scenarios, but every BCR crosses 1 across its range. No treatment should be approved or rejected on central BCR alone. |
| What uncertainty still remains? | The key uncertainty is the absence of DJI-specific incident frequency, loss, control-cost and control-effectiveness data. The ranges are transparent assessment judgments, not probabilistic confidence intervals. |


## Weekly reflection

- I examined what each risk-model input actually represents and identified the system, process, documentary, or people-based evidence that would support it.
- The most important learning was to label estimates honestly: public context can show that a hazard exists, but it does not establish DJI-specific incident frequency or loss.
- Range analysis and figure checks make uncertainty explicit and prevent a clear-looking chart from implying unsupported precision.

## Related case studies

- [Cisco metrics and evidence case study](../case-studies/cisco-metrics-and-evidence.md)
- [DJI cyber-risk governance case study](../case-studies/dji-cyber-risk-governance.md)

---

[Back to the course index](../README.md)
