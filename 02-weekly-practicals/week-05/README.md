# CP5408 Weekly Practical 05

**Course:** Cyber Security Strategy Governance and Risk Management

**Organisation used throughout:** DJI
**Focus:** Data cleaning, descriptive statistics, ARO/SLE interpretation, strategic objectives, KPIs, and a three-year roadmap.
**Connection to the learning sequence:** Converts the established DJI risk register and quantified scenarios into governed objectives, KPIs, initiatives, and a roadmap.

## Completed weekly practical

> **Scope note:** The course-provided worksheet set the prompts. This section presents the completed tables and notebook work; prompts remain in the first column where they are needed to make a response understandable. Claims and estimates are coursework scenario assumptions unless the submission itself identifies a source.

### Submitted response table 1

| Time | Activity |
| --- | --- |
| 5 min | Part 1: applied or exploratory? |
| 15 min | Part 2: descriptive statistics and outliers (notebook Sections 1–2). |
| 20 min | Part 3: clean a messy dataset and test your decisions (notebook Sections 3–5). |
| 10 min | Part 4: from statistics to Assignment 1 inputs (notebook Section 6). |
| 15 min | Part 5: strategic objectives and KPIs. |
| 15 min | Part 6: initiatives and prioritisation. |
| 20 min | Part 7: three-year roadmap, assumptions, and a self-check. |

### Submitted response table 2

| Scenario | Applied / exploratory / both | Reason |
| --- | --- | --- |
| Calculating ALE for a known ransomware risk using estimated ARO and SLE. | Applied | The risk and question are already defined; the calculation estimates its expected annual loss. |
| Looking through incident logs to see which kinds of event are increasing. | Exploratory | The analyst is looking for patterns and possible new questions before deciding on a specific explanation. A formal trend test would require suitable time-series data and a stable definition of incidents. |
| Comparing the cost of a proposed control with the expected reduction in ALE. | Applied | The analysis answers a defined investment question: whether the expected loss avoided is proportionate to the control's annual cost. |
| Exploring support tickets to find out why patching is slower for some teams. | Exploratory | The analyst is investigating possible causes and patterns rather than testing a single established hypothesis. The findings could later support applied analysis. |

### Submitted response table 3

| Statistic | Seminar data | With 0 and 200 added | Changed a little or a lot? |
| --- | --- | --- | --- |
| Mode | 27 | 27 | No change |
| Median | 27.50 | 27.50 | No change |
| Mean | 31.29 | 36.58 | Moderate increase (+5.29) |
| Range | 46 | 200 | Large increase |
| Interquartile range | 13 | 13 | No change |
| Standard deviation | 11.93 | 35.77 | Large increase |

### Submitted response table 4

| Question | Response |
| --- | --- |
| Which measures resisted the outliers, and which did not? Why? | The mode, median, and interquartile range did not change. They depend on the most common value or the central ordering of the data, so the two extreme observations did not move them. The mean increased from 31.29 to 36.58, the range increased from 46 to 200, and the standard deviation increased from 11.93 to 35.77. These measures are more sensitive to extreme values, particularly the range and standard deviation. |
| Incident costs usually include a few very large events. Which measure of “typical cost” would you report to management, and what would you say about the large events? | For the synthetic ransomware category, the cleaned data has a median cost of $610,000 and a mean cost of $1,275,714.29 (difference $665,714.29). The mean is much higher because of the unusually large $4,800,000 record (incident I27). I would report the median as the typical observed cost, while also reporting the high-cost tail and the $4.8 million outlier separately. The median does not make the large event unimportant; it prevents one extreme record from defining what is described as typical. |

### Submitted response table 5

| Problem | Example from the notebook (incident ID and value) | Why it matters for analysis |
| --- | --- | --- |
| Same category written different ways | I07 \`ransomware \` and I13 \`RANSOMWARE\`; I09 \`data-breach\` and I15 \`Data Breach\`; I11 \`Third party outage\` and I17 \`Outage (supplier)\`; I14 \`Phishing / account takeover\` | Without standardisation, equivalent incidents can be split across different categories, distorting counts, summaries, and comparisons. The notebook standardises 16 raw labels into five categories. |
| Cost recorded as text or with symbols | I08 \`32,000\`; I13 \`$380,000\`; I15 \`$1,100,000\`; I35 \`75,000\` | These values must be converted to numeric values before calculating statistics. Removing commas and currency symbols is mechanical when the meaning is unambiguous. |
| Cost missing, N/A, or unknown | I19 \`N/A\`; I20 \`N/A\`; I22 blank; I26 \`unknown\` | These records do not provide a usable cost. Treating the strings as numbers would fail; silently replacing them with zero would bias cost estimates. |
| Cost recorded as zero | I10 (Phishing) = 0; I17 (supplier outage) = 0 | A zero may mean that no cost was incurred, but it may instead mean that cost was not recorded. The decision changes the cost distribution and must be documented. Both zero values are treated as missing in the default run. |
| Severity recorded on two different scales | Text values \`Low\`, \`Medium\`, \`High\` and numeric values such as I05 = 2, I06 = 4, I07 = 5 | The values need a consistent ordered scale before comparisons. The notebook maps 1-2 to Low, 3 to Medium, and 4-5 to High. Severity is ordinal, so a mean severity is not appropriate. |
| A very unusual value | I27: Ransomware cost = $4,800,000 | The record is above the category-specific upper outlier fence. Removing or capping it materially reduces the ransomware mean, but removing it may hide a genuine severe event. The default analysis flags and retains it. |

### Submitted response table 6

| Run | ZERO_COST_RULE | MISSING_COST_RULE | OUTLIER_RULE | Ransomware median | Ransomware mean |
| --- | --- | --- | --- | --- | --- |
| Default | missing | drop | keep | $610,000 | $1,275,714.29 |
| Your change 1 | missing | drop | remove | $565,000 | $688,333.33 |
| Your change 2 | missing | median | keep | $610,000 | $1,192,500 |

### Submitted response table 7

| Decision | What you chose for your final run | Why this is defensible |
| --- | --- | --- |
| Is a cost of 0 a real zero, or “not recorded”? | Treat zero as missing. | For incidents such as phishing or supplier outage, a recorded cost of exactly zero may indicate incomplete cost capture. There is not enough evidence in the synthetic records to confirm that these events truly cost nothing. The cleaning log records this assumption. |
| Leave out incidents with no cost, or fill them with the category median? | Drop missing costs from cost statistics, but keep the incident in incident counts. | Median imputation can be used for a sensitivity test, but it creates synthetic cost values and can make the distribution look more complete than the evidence supports. Dropping costs avoids inventing amounts; the number of excluded cost values must be disclosed. |
| Keep, remove, or cap the outlier? | Keep I27, but flag it and report its influence. | A $4.8 million ransomware event may be extreme but real. Keeping it preserves the severe-loss tail. The comparison run shows how strongly it affects the mean, so both median and mean should be reported with the limitation explained. |

### Submitted response table 8

| Item | Value from the notebook |
| --- | --- |
| Category chosen, and which of your risks it resembles | Phishing (illustrative analogue for R7 — credential stuffing leading to customer-account takeover). Phishing and credential stuffing are different attack mechanisms; this category is used to practise the estimation method, not to claim it represents DJI. |
| Incidents in the dataset, and ARO per organisation | 10 incidents in the synthetic dataset. ARO per organisation = 10 ÷ (40 organisations x 5 years) = 0.05 incidents per organisation-year. |
| SLE low / likely / high | SLE low (Q1) = $21,000; SLE likely (median) = $26,500; SLE high (Q3) = $35,250. |
| ALE low / likely / high | ALE low = $1,050; ALE likely = $1,325; ALE high = $1,762.50. |
| ALE if the mean had been used instead of the median | $1,462.50 (using the mean SLE instead of the median). |

### Submitted response table 9

| Question | Response |
| --- | --- |
| The dataset has 8 ransomware incidents. Why is the ARO not 8, or 8 ÷ 5 = 1.6? What would happen to ALE if you made that mistake? | The synthetic dataset covers 40 organisations over five years, or 200 organisation-years. Therefore, the per-organisation ARO is 8 ÷ (40 x 5) = 0.04 ransomware incidents per organisation-year. The value 8 ÷ 5 = 1.6 is the average number of ransomware incidents per year across the entire 40-organisation sample, not per organisation. Using 8 or 1.6 as one organisation's ARO would overstate annual exposure and inflate ALE. |
| How does this range compare with the low / likely / high range you built by judgement in Practical 4? | The synthetic Phishing proxy produces an ARO of 0.05 and an ALE range of $1,050-$1,762.50, with a median-based estimate of $1,325. The Practical 4 assessment for R7 used ARO = 2.0 and SLE = $45,000, giving a central ALE of $90,000. The large difference shows the synthetic Phishing data is not a suitable replacement for the R7 judgement-based estimate: the category represents a different attack mix, the dataset is synthetic, and its population may not match DJI's exposure. The comparison is useful as a challenge to assumptions, not as proof that the Practical 4 estimate is wrong. |
| Give two reasons these figures might not describe your organisation (Cisco Lesson 1: does the data support the conclusion?). | Two reasons: (1) The dataset is synthetic and describes a hypothetical sample of 40 comparable organisations; it contains no verified DJI incident logs, account population, exposure rates, or internal cost records. (2) Phishing is not equivalent to credential stuffing, and DJI's platform architecture, attack volume, security controls, user base, and reporting practices may differ from those of the hypothetical sample. Both the category match and transfer from sample organisations to DJI are assumptions. |

### Submitted response table 10

| Strategic objective | Risks addressed | KPI | Baseline | Target: Year 1 / Year 3 | Data source and owner |
| --- | --- | --- | --- | --- | --- |
| 1. Reduce the risk of unauthorised access to privileged cloud services and customer accounts. | R3, R7 | Percentage of active privileged FlightHub accounts enrolled in phishing-resistant MFA before their first privileged session. | Unknown; establish using the privileged-account inventory and identity-provider records during Year 1. | Year 1: Establish baseline and achieve at least 95% coverage by year-end, with documented exceptions. Year 3: 100% coverage or formally approved, time-limited exceptions, reviewed quarterly. | Identity-provider enrolment records, account inventory, privileged-access audit logs. Owner: Head of Identity; accountable executive: CISO. |
| 2. Protect flight safety by improving the detection and safe handling of navigation anomalies. | R1 | Percentage of confirmed high-severity GPS/navigation anomaly events receiving a documented safety assessment and recorded fail-safe outcome within the approved response time. | Unknown; define event taxonomy and response-time criteria, then establish the baseline from validated telemetry and incident records. | Year 1: Establish baseline and approve the response-time criteria. Year 3: At least 95% of validated high-severity events handled within the approved criteria, subject to engineering validation. | Flight telemetry, anomaly records, safety/support tickets, post-incident reviews. Owner: VP Engineering with the Flight Safety lead. |
| 3. Improve security governance across critical software and supply-chain dependencies. | R4, R9 | Percentage of critical third-party software and supply-chain dependencies with a documented security review, accountable owner, and current regulatory/continuity assessment. | Unknown; establish a critical-dependency inventory and baseline in Year 1. | Year 1: Inventory critical dependencies and establish the baseline. Year 3: 100% of critical dependencies reviewed at the defined cadence, with exceptions and remediation plans recorded. | Software bill of materials (SBOM), supplier register, security review records, legal/regulatory register. Owner: Head of Product Security, with Chief Strategy Officer/Legal for market-access assessments. |
|   |   |   |   |   |   |

### Submitted response table 11

| Initiative | People / process / technology | Objective and risks it serves | Estimated annual cost | Expected effect (risk reduction or ratio from Practical 3, or a qualitative reason) | Priority (1 = first) |
| --- | --- | --- | --- | --- | --- |
| Integrated identity and account-takeover protection: privileged-account MFA, account inventory, and credential-stuffing detection. | People, process, technology | Objective 1; R3 and R7 | $130,000 combined planning estimate ($80,000 for R3 plus $50,000 for R7 in the Week 3 model) | Week 3 central estimates: R3 risk reduction $105,000; R7 risk reduction $63,000. Combined estimated reduction $168,000 against $130,000 cost (illustrative combined BCR about 1.29, subject to validating overlap and costs). | 2 |
| Flight-safety and navigation-resilience improvement, including validated GPS-anomaly handling, resilient-navigation fallback, and safe-state/return-to-home testing. | Process and technology; staff training supports use | Objective 2; R1 | $250,000 annual assessment estimate from Week 3 | Estimated risk reduction $200,000/year and BCR 0.80 in the central scenario. Prioritise despite BCR below 1 because safety impact may include injury, regulatory action, and severe reputational harm. | 1 |
| Security incident data and loss-accounting standard: consistent categories, timestamps, asset ownership, cost fields, and quarterly data-quality review. | People and process, supported by reporting systems | All priority risks; supports Objectives 1-3 | TBC after baseline and process scoping | Improves the reliability of future ARO/SLE estimates and management reporting. No defensible standalone BCR is available yet. | 3 |
| Secure software and supplier dependency assurance: maintain a critical-component/SDK inventory, document reviews, and define release and supplier assurance gates. | Process and technology | Objective 3; R4 (also supports R2/R10) | TBC after inventory and supplier-scope definition | Reduces exposure to compromised dependencies and improves traceability. Initial effect should be measured through coverage and exception closure rather than an unsupported dollar reduction. | 4 |
| Regulatory and market-access resilience: monitor relevant restrictions, map critical market/supplier dependencies, and maintain documented contingency options. | People and process | Objective 3; R9 | TBC following legal and supply-chain assessment | Cannot eliminate geopolitical risk, but can improve preparedness and reduce concentration/transition time. Prioritisation reflects strategic and regulatory exposure, not a quantified BCR. | 5 |
| Cross-functional incident and safety exercises; review detection coverage, response hand-offs, and lessons learned. | People and process | Objectives 1-2; R3, R7, R1 | TBC after exercise scope is agreed | Tests whether controls and monitoring work in practice; produces actions and evidence for KPI review. | 6 |

### Submitted response table 12

| Question | Response |
| --- | --- |
| Where you have numbers, which initiative gives the most risk reduction per dollar? | On the current Week 3 central estimates, the R3 control has the highest individual BCR at 1.31 ($105,000 estimated annual risk reduction / $80,000 annual control cost). R7 follows at 1.26 ($63,000 / $50,000). R1 has a BCR of 0.80 ($200,000 / $250,000). These are scenario outputs based on assumed inputs, not measured returns. The combined identity programme's provisional BCR should not replace the separate R3/R7 ratios until shared costs and overlapping effects have been reviewed. |
| Did you place any initiative higher than its numbers suggest? Give the reason (safety, legal duty, customer trust, or because other initiatives depend on it). | Yes. The R1 flight-safety initiative is prioritised first despite its central BCR of 0.80. The decision reflects the potential for serious injury, public-safety consequences, regulatory requirements, and customer trust. A BCR below 1 is not, by itself, sufficient reason to reject a safety-critical control. The proposed cost and effect must still be validated through engineering analysis and testing. |
| Is any top-five risk from Practical 2 not addressed by any initiative? Is that a decision to accept it, or a gap? | The Practical 2 top five were R3, R7, R1, R9, and R4. All five are covered by at least one initiative above: R3/R7 by identity and account-takeover protection; R1 by flight-safety resilience; R4 by software/supplier assurance; and R9 by regulatory and market-access resilience. Any risk not funded in the first period should remain explicitly owned and reviewed; delaying implementation must not silently become risk acceptance. |

### Submitted response table 13

| Period | Initiative | Owner (role) | Depends on | Milestone or KPI that shows it is done |
| --- | --- | --- | --- | --- |
| Year 1 (0-12 months) | Integrated identity and account-takeover protection for R3 and R7. | CISO (accountable); Head of Identity (delivery owner) | Inventory of privileged and customer accounts; baseline identity logging; approval of exception process. | Baseline established; at least 95% of active privileged accounts enrolled in phishing-resistant MFA by year-end; credential-stuffing detection and response workflow tested; exceptions have owners and expiry dates. |
| Year 1 (0-12 months) | Flight-safety and navigation-resilience improvement for R1. | VP Engineering; Flight Safety lead | Hazard analysis, current navigation architecture review, agreed GPS-anomaly scenarios, and test/safety criteria. | Safety criteria and response times approved; representative GPS-interference scenarios tested; test outcomes and unresolved hazards documented before deployment decisions. |
| Year 2 (13-24 months) | Security incident data and loss-accounting standard. | CISO / SOC Manager | Consistent event taxonomy, account/asset ownership from Year 1, and agreement on direct-cost fields. | At least 90% of material incidents have complete category, timestamps, affected asset, owner, response action, and available direct-cost fields; quarterly data-quality review is operating. |
| Year 2 (13-24 months) | Secure software and supplier dependency assurance for critical SDKs and components (R4). | Head of Product Security; Mobile Engineering Lead | Critical dependency inventory; supplier engagement; agreed security-review and exception processes. | Critical third-party SDKs and release dependencies are inventoried; all critical releases have a documented security review or an approved exception and remediation plan. |
| Year 3 (25-36 months) | Regulatory and market-access resilience for R9. | Chief Strategy Officer with Legal | Critical market and supplier-dependency map; current regulatory register; Year 2 supply-chain information. | Annual assessment of critical market restrictions and supplier concentration completed; contingency options and decision owners documented and reviewed. |
| Year 3 (25-36 months) | Continuous assurance and cross-functional exercises. | CISO and VP Engineering | Year 1-2 baselines, deployed controls, incident-data process, and risk-owner participation. | Annual tabletop exercise covers R3, R7, and R1; corrective actions have owners and due dates; KPI and data-quality results are reviewed quarterly and used to update the risk register. |

### Submitted response table 14

| Prompt | Response |
| --- | --- |
| Two challenges or constraints that could delay the roadmap (budget, staffing, technical complexity, supplier cooperation). | 1. Limited access to reliable internal evidence: ARO, SLE, and control-effectiveness assumptions cannot be validated without appropriately scoped incident, identity, support, telemetry, and cost records. Building consistent data collection may take time and require agreement across teams. 2. Safety-critical engineering and supplier dependencies: Navigation-resilience changes require testing across relevant hardware, software, operating environments, and failure modes. Supplier cooperation, specialist staff, and budget availability may delay the work. |
| Two assumptions the roadmap relies on. (Your Practical 4 assumptions are a good source.) | 1. Senior leadership will assign accountable risk owners and provide funding and cross-functional access to the identity, incident, engineering, and supplier data needed to establish baselines. 2. The Week 3 control costs and reduction percentages are provisional planning assumptions. They will be reviewed after implementation, testing, and at least 6-12 months of relevant monitoring data; they are not guaranteed outcomes. |
| One place where an ethical or legal consideration changed your sequencing, for example doing safety-critical or personal-data protections first even though another initiative had a better ratio. | The R1 flight-safety initiative is prioritised in Year 1 even though its central estimated BCR is below 1. The potential for injury and unsafe drone behaviour means that a purely financial ranking would be inadequate. The roadmap must also protect personal and operational data, preserve appropriate auditability, and review applicable safety, privacy, and market-access obligations. Any legal or regulatory requirement should be validated for the relevant jurisdiction rather than assumed to apply uniformly worldwide. |

### Submitted response table 15

| Check | Yes / not yet |
| --- | --- |
| Every top-five risk has at least one initiative, or a stated decision to accept it. | Yes - R3, R7, R1, R4, and R9 are each addressed by an initiative in the plan above. |
| Every objective has a KPI with a baseline (or a plan to get one) and a target. | Yes - baseline collection required - All three objectives state that DJI-specific baselines are currently unknown and define how to establish them. Targets are proposed and require approval. |
| Initiatives cover people, process, and technology, not technology alone. | Yes - The plan includes training/exercises, incident-data and governance processes, identity controls, software assurance, and flight-safety technology. |
| No objective names a product or a configuration setting. | Yes - Objectives describe strategic outcomes; implementation details appear in initiatives. |
| Every roadmap item has an owner, and dependencies are sequenced correctly. | Yes - subject to delivery planning - Each roadmap item has a role-based owner, dependency, and milestone. Delivery teams must confirm detailed sequencing and resourcing. |
| At least one regulatory or ethical obligation relevant to your sector is reflected. | Yes - Safety-critical treatment, privacy/data governance, and market-access/regulatory readiness are included. |


## Weekly reflection

- I documented data-cleaning decisions instead of silently converting missing, zero, and inconsistent values into convenient numbers.
- Using the median alongside outliers made the distinction between a typical loss and severe-loss exposure clearer.
- The final roadmap connects risk priorities to owners, baselines, measurable targets, dependencies, and explicit limitations of synthetic data.

## Related case studies

- [DJI cyber-risk governance case study](../case-studies/dji-cyber-risk-governance.md)
- [Cisco metrics and evidence case study](../case-studies/cisco-metrics-and-evidence.md)

---

[Back to the course index](../README.md)
