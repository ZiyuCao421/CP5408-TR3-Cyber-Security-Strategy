# CP5408 Weekly Practical 02

**Course:** Cyber Security Strategy Governance and Risk Management

**Organisation used throughout:** DJI
**Focus:** Structured risk statements, a preliminary risk register, prioritisation, and risk-treatment ownership for DJI.
**Connection to the learning sequence:** Builds the Week 1 asset analysis into a risk register that becomes the input to quantitative modelling.
 
 index URl：https://fastidious-brioche-20d24d.netlify.app
## Completed weekly practical

> **Scope note:** The course-provided worksheet set the prompts. This section presents the completed tables and notebook work; prompts remain in the first column where they are needed to make a response understandable. Claims and estimates are coursework scenario assumptions unless the submission itself identifies a source.

### Submitted response table 1

| Time | Activity |
| --- | --- |
| 10 min | Review key risk management terms from the seminar. |
| 10 min | Confirm organisation scope and risk criteria. |
| 10 min | Identify important assets and relevant CIA impacts. |
| 15 min | Map threats, vulnerabilities, and risk events. |
| 25 min | Write risk statements and build the draft risk register. |
| 15 min | Prioritise risks using likelihood and impact. |
| 10 min | Reflect on controls and treatments. |
| 5 min | Decide how the register will be kept up to date. |

### Submitted response table 2

| Prompt | Response |
| --- | --- |
| Chosen organisation | DJI (Da-Jiang Innovations) |
| Industry context | Drone technology / unmanned aerial systems (UAS); consumer, professional and industrial drone operations. |
| Real or fictional organisation? | Real company |
| Scope of this risk assessment | Consumer and commercial drone product lines, DJI Fly / Pilot apps, FlightHub cloud, OTA firmware infrastructure, customer accounts, and key supply-chain components. |

### Submitted response table 3

| Term | Brief explanation | Example in your organisation |
| --- | --- | --- |
| Asset | Something valuable to the organisation that needs protection. | Drone hardware/firmware, FlightHub cloud platform, customer flight data, navigation algorithms, AI models |
| Threat | A potential source or event that can cause harm. | External attacker (GPS spoofer, ransomware crew), supply chain attacker, malicious insider |
| Attacker | A person or group that carries out or enables an attack. | Nation-state adversary targeting dual-use technology, organised crime seeking customer data, hobbyist exploiting firmware |
| Vulnerability | A weakness that could be exploited by a threat. | Single-key firmware signing; OcuSync protocol weaknesses; lack of MFA on FlightHub admin |
| Risk | The possibility that a threat exploits a vulnerability and causes harm. | A GPS spoofing attack causes a Mavic drone to crash in a populated area |
| Control | A safeguard used to prevent, detect, or reduce risk. | Signed firmware + secure boot, OcuSync encryption + mutual authentication, phishing-resistant MFA |
| Impact | The consequence or damage caused if a risk occurs. | Safety incident, regulatory ban, brand collapse (e.g. US/EU expansion of restrictions) |
| Likelihood | The chance that a risk event will occur. | GPS interference incidents reported monthly worldwide; sanctions risk elevated given geopolitics |
| Residual risk | The risk that remains after controls are applied. | After firmware signing, supply chain compromise risk remains (chips, build tools) |

### Submitted response table 4

| Question | Your answer |
| --- | --- |
| What parts of the organisation are included in this risk assessment? | Consumer + commercial drone product lines, DJI Fly / Pilot apps, FlightHub cloud, OTA firmware infrastructure, customer accounts, supply chain (key components) |
| What parts are excluded? | Internal HR/Finance IT, retail store physical security, third-party app developers |
| Who are the main stakeholders affected by cyber risk? | Drone operators (consumers + enterprise), regulators (FAA / EASA / CAAC), government customers, suppliers (chip makers), employees |
| What types of harm matter most: financial, operational, safety, privacy, legal, reputational, or ethical? | Safety (drone crashes causing injury), regulatory/sanctions (country bans), privacy (images, location), IP theft (autonomous flight algorithms), financial (product recall, lost market access) |
| What would make a risk unacceptable for this organisation? | (1) Mass safety incident triggering global recall, (2) data breach exposing customer flight/location data, (3) sanctions/ban in any top-3 markets, (4) compromise of firmware signing key |

### Submitted response table 5

| Score | Likelihood | Likelihood guide | Impact | Impact guide |
| --- | --- | --- | --- | --- |
| 1 | Rare | Would require exceptional circumstances; not seen in comparable organisations. | Trivial | Negligible disruption or cost; absorbed in normal operations. |
| 2 | Unlikely | Could occur but not expected within the next few years. | Minor | Limited disruption, low cost, minor inconvenience, easily recoverable. |
| 3 | Possible | Plausible within the next year or two, especially if controls are weak. | Moderate | Noticeable disruption, moderate cost, customer concern, management attention required. |
| 4 | Likely | Expected within the next year; observed in similar organisations. | Serious | Major disruption, significant financial loss, regulatory notification, or a safety near-miss. |
| 5 | Almost certain | Expected more than once a year or already occurring. | Severe | Injury or loss of life, loss of operating licence, existential financial or reputational damage. |

### Submitted response table 6

| Asset | How it is stored, transmitted, or processed | Most important security objective | Why this asset matters |
| --- | --- | --- | --- |
| Example: customer health data | Stored in cloud databases and backups; transmitted between device, app, APIs, and cloud; processed to generate health insights. | Confidentiality and integrity | Unauthorised access or incorrect processing may harm customers and expose the organisation to legal and reputational consequences. |
| Drone flight-control & navigation systems (selected in Week 1) | Stored on-drone + ground control SDK; transmitted OcuSync to controller + 4G to cloud; processed for autonomous flight | Integrity (Week 1) | Compromised navigation = safety incident = recall + regulatory action |
| OTA firmware update infrastructure | Build pipeline → signed firmware → CDN → device-side verification | Integrity | A malicious firmware push could ground millions of devices |
| FlightHub cloud platform | Hosts customer fleet management, flight logs, live streaming; AWS-backed | Confidentiality + Availability | Outage stops enterprise customers; breach exposes fleet data |
| Customer images, video, flight logs | Encrypted at rest; streamed via app; processed by DJI Mimo / editing cloud | Confidentiality | Sensitive (inspection, public safety, defence-adjacent) imagery; leak = legal liability |
| DJI Fly / Pilot mobile apps | Distributed via App Store / Play Store; OAuth with FlightHub; uses map SDKs | Integrity | Compromised app = credential theft + downstream account takeover |
| Autonomous flight AI models | Trained on internal dataset; deployed on-device and in cloud | Confidentiality + Integrity | IP theft = competitive loss; poisoning = unsafe autonomous behaviour |
| Customer accounts (DJI account) | SSO + password; sometimes linked to social login; admin access for enterprise | Confidentiality + Authentication | Account takeover = control of fleet + access to flight logs |
| Supply chain: chips, sensors, modules | Sourced from US/Taiwan/Korea/China vendors; firmware co-developed | Integrity | A compromised chip could silently exfiltrate data across all devices |

### Submitted response table 7

| Asset | Threat | Vulnerability | Potential consequence |
| --- | --- | --- | --- |
| Example: drone navigation system | GPS spoofing or signal interference | Weak validation of navigation signals | Drone route deviation, service disruption, safety hazard, or asset loss. |
| Flight-control & navigation | GPS spoofing / signal interference | Drone relies on GPS without mandatory inertial fallback | Drone deviates, crashes in populated area, safety + brand collapse |
| OTA firmware infrastructure | Nation-state / criminal — signing key theft | Single signing key with weak rotation; limited dual control | Malicious firmware pushed to millions of devices simultaneously |
| FlightHub cloud | External attacker — credential theft | Admin accounts not all on phishing-resistant MFA | Enterprise fleet data exfiltrated; service disrupted |
| Customer images & video | External attacker — cloud storage misconfig | Legacy buckets lack customer-managed encryption keys | Mass image leak; privacy breach |
| DJI Fly / Pilot app | Supply chain — malicious dependency | No full SBOM enforcement; map SDK updated frequently | User credentials harvested at scale |
| AI models | Internal actor — IP exfiltration | Model weights accessible to many engineers; no DLP on model artefacts | Competitive loss; reverse engineering by rivals |
| Customer accounts | External attacker — credential stuffing | Some accounts still on password-only; weak rate limiting | Mass account takeover + drone control hijack |
| Supply chain components | Nation-state — chip-level implant | No full hardware bill of materials verification | Silent telemetry exfiltration across entire fleet undetectable by software |

### Submitted response table 8

| Threat type | Examples to consider |
| --- | --- |
| External attacker | Credential theft, ransomware, malicious code, denial of service, data theft, API abuse, GPS or radio interference. |
| Internal actor | Accidental data exposure, policy noncompliance, misuse of privileges, malicious insider. |
| Technical failure | Cloud outage, software defect, configuration error, weak access control, inadequate logging, unsafe autonomous behaviour after a faulty update. |
| Third party | Supplier breach, outsourced IT failure, insecure integration, vendor downtime, compromised component or firmware. |
| Physical/environmental | Fire, flood, theft, power loss, equipment damage, insecure storage areas, physical tampering with devices in the field. |
| Governance/procedural | Lack of policy review, inadequate documentation, undefined responsibilities, poor change control. |

### Submitted response table 9

| Weak risk wording | Improved risk statement |
| --- | --- |
| Phishing | Because staff may not recognise targeted phishing emails and privileged accounts are not consistently protected by MFA, an attacker may compromise an employee account, resulting in unauthorised access to sensitive systems and possible data exposure. |
| Cloud outage | Because the organisation relies heavily on a single cloud provider with limited failover capability, a provider outage may interrupt customer services, resulting in lost revenue, reputational damage, and reduced customer trust. |
| Privacy breach | Because customer data is collected and shared across multiple systems without clear retention and access controls, personal information may be exposed or misused, resulting in regulatory scrutiny, customer harm, and reputational damage. |
| Robot malware | Because warehouse robot firmware updates are not cryptographically signed and the robot network is not segmented from the office network, an attacker may push a malicious update, resulting in unsafe robot behaviour, injury risk to staff, and a halt to warehouse operations. |

### Submitted response table 10

| Risk ID | Risk statement |
| --- | --- |
| R1 | Because drone navigation relies on GPS signals without mandatory inertial fallback, a criminal or state actor may broadcast spoofed GPS signals near a sensitive area, resulting in a Mavic drone crashing in a populated zone, triggering a global safety review and brand collapse. |
| R2 | Because OTA firmware updates rely on a single signing key with limited rotation and no enforced dual control, a nation-state attacker who compromises an insider or build tool may push malicious firmware to millions of devices, resulting in mass device compromise and a recall costing hundreds of millions USD. |
| R3 | Because FlightHub admin accounts are not all protected by phishing-resistant MFA, an external attacker may steal credentials via spear phishing, resulting in enterprise fleet data exfiltration and service disruption affecting commercial customers. |
| R4 | Because the mobile app uses third-party SDKs (maps, analytics, crash reporting) without full SBOM verification and signed dependency policy, an attacker may publish a trojanised SDK update, resulting in mass credential theft and downstream FlightHub account compromise. |
| R5 | Because legacy cloud storage buckets were created without customer-managed encryption keys and have not been fully audited, a misconfigured bucket may be accessed by an external party, resulting in mass leak of customer images, video and flight logs and GDPR-like regulatory action. |
| R6 | Because AI model weights and training data are accessible to a large engineering population without effective DLP, a malicious insider may exfiltrate autonomous flight algorithms, resulting in competitive loss and potential safety risk if reverse-engineered controls reach the market. |
| R7 | Because DJI account password policies lack consistent enforcement and rate limiting is uneven, an attacker may conduct credential stuffing using leaked passwords from other breaches, resulting in mass account takeover and unauthorised access to flight logs and drone control. |
| R8 | Because critical components (flight controllers, image processors, GPS modules) are sourced from multiple countries without full hardware bill-of-materials verification, a nation-state supplier may introduce a hardware implant, resulting in silent telemetry exfiltration across the entire fleet undetectable by software controls. |
| R9 | Because DJI operates in a geopolitically sensitive industry and US/EU regulators are expanding restrictions on Chinese-made drones, a further regulatory action may be taken in a major market, resulting in revenue loss in the hundreds of millions and forcing emergency redesigns. |
| R10 | Because DJI wireless protocols (OcuSync, Lightbridge) are proprietary and have limited public security audit, a sophisticated researcher or attacker may discover a protocol-level vulnerability, resulting in remote hijack of drones in flight and emergency firmware rollout. |

### Submitted response table 11

| ID | Risk statement (short form) | Asset / service | Impact (1–5) | Likelihood (1–5) | Score (I × L) | Justification | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R1 | GPS spoofing → drone crash → safety incident | Flight-control / Navigation | 5 | 3 | 15 | GPS interference incidents reported monthly worldwide (industry data); impact severe due to safety + regulatory | VP Engineering |
| R2 | Firmware signing key theft → mass malicious update | OTA firmware infrastructure | 5 | 2 | 10 | Rare but catastrophic; nation-state capability assumed given geopolitical context | Head of Product Security |
| R3 | FlightHub admin credential theft → fleet data exfil | FlightHub cloud | 4 | 4 | 16 | Phishing remains top initial-access vector (industry data); partial MFA rollout is known gap | CISO |
| R4 | Mobile SDK compromise → credential harvest | DJI Fly / Pilot app | 4 | 3 | 12 | Mobile supply-chain attacks growing; SBOM gap documented (internal audit) | Mobile Engineering Lead |
| R5 | Misconfigured cloud bucket → mass image leak | Cloud storage | 5 | 2 | 10 | Major misconfigurations occur across industry; legacy buckets not fully audited (assumption) | Head of Cloud Security |
| R6 | Malicious insider exfiltrates AI model weights | Autonomous flight AI models | 4 | 2 | 8 | Insider attacks rare but impactful; large engineering access is known risk | CISO |
| R7 | Credential stuffing → mass account takeover | DJI customer accounts | 4 | 4 | 16 | Credential stuffing is constant background noise; weak password policy amplifies | Head of Identity |
| R8 | Hardware implant in component → silent exfiltration | Supply chain (chips/sensors) | 5 | 1 | 5 | Very rare; nation-state capability; hard to detect (stated assumption) | VP Supply Chain |
| R9 | Geopolitical ban in major market → revenue loss | Market access | 5 | 3 | 15 | Trend already established (US military ban 2017; expanding restrictions); real and ongoing risk | Chief Strategy Officer |
| R10 | Wireless protocol exploit → remote drone hijack | OcuSync / Lightbridge | 5 | 2 | 10 | Proprietary protocols often have hidden flaws; public audit would help (assumption) | Head of Product Security |

### Submitted response table 12

| Impact ↓ / Likelihood → | 1 Rare | 2 Unlikely | 3 Possible | 4 Likely | 5 Almost certain |
| --- | --- | --- | --- | --- | --- |
| 5 Severe | 5 | 10 | 15 | 20 | 25 |
| 4 Serious | 4 | 8 | 12 | 16 | 20 |
| 3 Moderate | 3 | 6 | 9 | 12 | 15 |
| 2 Minor | 2 | 4 | 6 | 8 | 10 |
| 1 Trivial | 1 | 2 | 3 | 4 | 5 |

### Submitted response table 13

| Rank | Risk ID | Score | Why this risk is a priority (including any safety, legal, or privacy reason that outweighs the score) |
| --- | --- | --- | --- |
| 1 | R3 | 16 | Highest score; phishing is constant; admin compromise = immediate fleet data exposure |
| 2 | R7 | 16 | Same score but mass customer impact; credential stuffing is ongoing background threat |
| 3 | R1 | 15 | Safety-critical; one incident could ground the brand globally |
| 4 | R9 | 15 | Geopolitical reality — already happening; can lose entire markets |
| 5 | R4 | 12 | Mobile app is the customer trust surface; supply chain is the fastest-growing attack vector |

### Submitted response table 14

| Risk ID | Existing controls | Treatment option | Proposed next control or action | Reasoning |
| --- | --- | --- | --- | --- |
| R3 | Basic SSO + password policy on FlightHub | Reduce likelihood | Enforce phishing-resistant MFA (FIDO2 keys) for all FlightHub admins within 90 days; add conditional access | Direct mitigation of credential theft; aligns with NIST 800-63B AAL3 |
| R7 | Some rate limiting; basic password rules | Reduce likelihood | Deploy credential-stuffing detection (e.g. Have I Been Pwned feed + behavioural signals); mandate MFA for all accounts | Eliminate the most common attack vector at the auth layer |
| R1 | GPS receivers with anomaly detection in some models | Reduce impact | Mandate visual-inertial odometry (VIO) fallback for all new drones; in-flight return-to-home on signal anomaly | Reduces impact when GPS is unreliable, regardless of cause |
| R9 | Legal & government relations team monitoring regulations | Reduce impact | Build a 'China-plus-one' component sourcing plan; expand R&D footprint to non-restricted regions | Cannot prevent geopolitics; can reduce blast radius |
| R4 | App store review, code signing | Reduce likelihood | Implement SBOM + dependency scanning (e.g. Snyk, Sigstore) in CI/CD; certificate pinning | Industry-standard mobile supply chain hygiene |

### Submitted response table 15

| Risk ID | Review frequency | What would trigger an earlier review? | Who reviews it? |
| --- | --- | --- | --- |
| R3 | Monthly | New phishing campaign targeting aviation sector; new admin onboarded | CISO + IAM Lead |
| R7 | Monthly | Major password leak reported (e.g. another massive breach dump) | Head of Identity |
| R1 | Quarterly | New GPS interference incident reported in any operating region | VP Engineering + Safety Team |
| R9 | Monthly | Any new sanctions legislation, entity-list addition, or major customer government restriction | Chief Strategy Officer + Legal |


## Weekly reflection

- I converted asset-threat-vulnerability thinking into explicit cause-event-impact risk statements and assigned accountable roles.
- The register makes safety, identity, supply-chain, and geopolitical issues comparable without treating them as identical problems.
- Several ratings remain scenario assumptions; future work should distinguish public threat context from DJI-specific frequency and impact evidence.

## Related case studies

- [DJI cyber-risk governance case study](../case-studies/dji-cyber-risk-governance.md)

---

[Back to the course index](../README.md)
