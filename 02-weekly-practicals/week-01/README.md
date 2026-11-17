# CP5408 Weekly Practical 01

**Course:** Cyber Security Strategy Governance and Risk Management

**Organisation used throughout:** DJI
**Focus:** Information assurance concepts, organisational context, and initial cyber-risk scoping for DJI.
**Connection to the learning sequence:** Establishes the DJI scope, critical assets, and initial risks used in every later practical.

## Completed weekly practical

> **Scope note:** The course-provided worksheet set the prompts. This section presents the completed tables and notebook work; prompts remain in the first column where they are needed to make a response understandable. Claims and estimates are coursework scenario assumptions unless the submission itself identifies a source.

### Submitted response table 1

| Time | Activity | Purpose |
| --- | --- | --- |
| 10 min | Concept warm-up | Reconnect with Seminar 1 terminology. |
| 20 min | Organisation scoping and sector incident | Begin Assignment 1 context selection and find a real incident to cite. |
| 20 min | Asset, threat, vulnerability, risk, and control mapping | Translate information assurance concepts into concrete risks. |
| 20 min | CIA/MSR application | Analyse one asset using the five information assurance services and the three countermeasure types. |
| 20 min | Strategic, tactical, and operational classification; strategy principles | Separate governance-level thinking from implementation detail and apply the strategy principles. |
| 10 min | Accountability and consequences | Connect risk management to leadership accountability and evidence of responsible governance. |

### Submitted response table 2

| Concept | Student explanation |
| --- | --- |
| Confidentiality | Only the right people can see the information. |
| Integrity | The information is correct and has not been changed wrongly. |
| Availability | The system and information are available when people need them. |
| Authentication | The system checks who a user or device really is. |
| Nonrepudiation | A person cannot easily deny that they sent a message or did something.(3 handshake.) |
| Accountability | The system records who did what so actions can be traced. |
| Asset | Something valuable that the organisation needs to protect. |
| Threat | Something that could cause harm to the organisation or its assets. |
| Vulnerability | A weakness that a threat could take advantage of. |
| Risk | The possibility that a threat will use a weakness and cause harm. |
| Control | Something the organisation does to reduce or manage a risk. |

### Submitted response table 3

| Prompt | Student response |
| --- | --- |
| Organisation name | DJI (Da-Jiang Innovations) |
| Real or fictional? | Real |
| Industry context | Drone and unmanned aerial systems technology |
| Main products or services | DJI develops consumer and professional drones, cameras, flight-control systems, software, and related services. |
| Approximate size | Large technology company with a global customer base and thousands of employees. |
| Geographic scope | Global |
| Key technologies used | Autonomous flight systems, GPS, cameras and sensors, wireless communication, AI and computer vision, mobile applications, firmware, and cloud services. |
| Key data handled | Customer information, flight and location data, images, videos, device information, telemetry data, and flight records. |
| Main stakeholders | Customers, employees, business partners, suppliers, regulators, government agencies, and national-security organisations. |
| Why cybersecurity matters for this organisation | Cybersecurity is important because DJI drones collect and transmit sensitive information and depend on software and wireless communication. A security failure could expose data, disrupt drone operations, or create safety and national-security risks. |
| A recent cybersecurity incident in your sector | In 2017, the U.S. military raised cybersecurity concerns about DJI drones and stopped using DJI systems. The concerns included potential risks involving sensitive data, communications, and drone security, increasing government scrutiny of commercially available drones in sensitive environments. |

### Submitted response table 4

| Asset | Threat | Vulnerability | Risk statement | Possible control |
| --- | --- | --- | --- | --- |
| Aerial images and videos collected by DJI drones | Unauthorised access or data theft | Sensitive media may be exposed if user accounts, devices, or storage systems are compromised | Confidential images could be accessed by unauthorised parties, causing privacy, commercial, or national-security concerns | Multi-factor authentication, encryption, access control, and regular access reviews |
| Drone flight-control and navigation systems | GPS spoofing or malicious manipulation of navigation signals | The drone may rely on external positioning signals that can potentially be manipulated | A drone could be misdirected or lose its intended route, causing operational disruption, property damage, or safety risks | GPS anomaly detection, signal validation, redundant navigation methods, and failsafe procedures |
| Drone firmware and flight-control software | Malicious or compromised software update | An attacker or compromised update process could introduce unauthorised changes to software | Modified firmware could affect drone behaviour, potentially causing unsafe flight or loss of operational control | Digitally signed firmware, secure boot, update verification, and controlled software distribution |
| Wireless communication between drone and controller | Communication interception or command manipulation | Wireless signals may be targeted by attackers attempting to interfere with communication | Attackers could disrupt communication or potentially interfere with drone-control operations, affecting availability and safety | Strong encryption, mutual authentication, secure communication protocols, and key management |
| Flight records, telemetry, and location data | Unauthorised collection or disclosure | Large amounts of operational data may be stored or transmitted through connected applications and services | Exposure of flight locations and operational information could create privacy, commercial, or security risks | Data minimisation, encryption, strict access permissions, secure storage, and monitoring |

### Submitted response table 5

| Question | Student response |
| --- | --- |
| Asset selected? | Drone flight-control and navigation systems |
| Is the asset stored, transmitted, processed, or all three? | All three. Flight-control software and configuration data are stored on the drone and related systems; control commands and navigation information are transmitted between the drone, controller, and connected systems; and the flight-control system processes navigation, sensor, and control data during operation. |
| What could affect confidentiality? | Unauthorised access to flight-control data, flight records, or communication data could expose sensitive operational or location information. |
| What could affect integrity? | GPS spoofing, manipulated sensor data, unauthorised commands, or compromised firmware could cause the system to make incorrect navigation or flight-control decisions. |
| What could affect availability? | Wireless interference, denial-of-service attacks, system failures, or malicious software could prevent the drone from receiving commands or operating normally. |
| What could affect authentication? (Can the system be sure who or what is acting?) | An attacker may attempt to impersonate an authorised controller, device, or software component and send unauthorised commands to the drone. |
| What could affect nonrepudiation? (Could someone deny having sent a command or made a change?) | If commands or software changes are not properly recorded and linked to authenticated users or devices, it may be difficult to determine who issued a command or made a change. |
| What role do people play in protecting it? | Staff and users need to follow secure operating procedures, protect their accounts and devices, report suspicious activity, and receive appropriate cybersecurity training. |
| What role does policy play? | Security policies can define requirements for access control, firmware updates, incident reporting, data protection, and the secure operation of drones. |
| What role does technology play? | Technology can provide encryption, authentication, secure boot, signed firmware, GPS anomaly detection, monitoring, and other technical protections. |
| Which information assurance service is most important for this asset, and why? | Integrity is the most important service because incorrect navigation data, commands, or flight-control software could directly affect the drone's behaviour and potentially create safety and operational consequences. |

### Submitted response table 6

| Decision/action | Strategic, tactical, or operational? | Why? |
| --- | --- | --- |
| The board approves a three-year cybersecurity strategy. | Strategic | It sets the organisation's long-term cybersecurity direction and is approved by senior leadership. |
| The CISO selects priority controls for the next 12 months. | Tactical | It translates the overall strategy into medium-term priorities and specific security actions. |
| IT staff configure MFA for administrator accounts. | Operational | It is a day-to-day technical implementation of a security control. |
| A policy states that customer data must be encrypted. | Tactical | It defines a specific organisational security requirement that supports the broader cybersecurity strategy. |
| A helpdesk worker follows the account recovery procedure. | Operational | It involves following an established procedure as part of routine operational work. |
| The organisation chooses its cyber risk appetite. | Strategic | Risk appetite is a high-level organisational decision that determines how much cyber risk the organisation is willing to accept. |
| The strategy document requires a particular vendor's endpoint detection product. | Too detailed for the main strategy | The strategy should define the security objective or capability required rather than prescribe a specific vendor product. The product selection belongs at a lower implementation level. |

### Submitted response table 7

| Principle | What it implies for your organisation's strategy |
| --- | --- |
| Risk-based | DJI should prioritise cybersecurity investments according to the likelihood and potential impact of risks. For example, risks affecting drone flight control, navigation, sensitive customer data, and communications should receive appropriate priority because failures could affect safety, privacy, and business operations. |
| Independent (vendor-neutral) | DJI's cybersecurity strategy should define required security capabilities and outcomes rather than being written around a particular security vendor or product. This allows the organisation to select suitable technologies as its needs change. |
| Consistent with legal and regulatory requirements | DJI operates in a global market, so its cybersecurity strategy should consider applicable laws, regulations, standards, privacy requirements, and aviation-related requirements in the countries where its products and services are used. |

### Submitted response table 8

| Prompt | Student response |
| --- | --- |
| What evidence would show the organisation is acting responsibly? | DJI could demonstrate responsible cybersecurity management through documented risk assessments, security policies, access controls, security testing, incident response procedures, staff training, and records showing that identified risks are being addressed. Regular security reviews and evidence of compliance with relevant legal and regulatory requirements would also provide assurance to executives, regulators, and customers. |
| How would the organisation show it is improving over time (plan, do, check, act)? | Plan: identify and prioritise cybersecurity risks and define security objectives. Do: implement controls such as encryption, authentication, secure software updates, monitoring, and staff training. Check: conduct security testing, audits, incident reviews, and measure whether controls are effective. Act: fix weaknesses, update policies and controls, and adjust priorities based on new threats and lessons learned. |
| What might happen if leadership ignores known risks? | Ignoring known cybersecurity risks could increase the likelihood and impact of security incidents. For DJI, this could result in unauthorised access to customer or flight data, disruption of drone operations, compromised systems, financial losses, legal or regulatory consequences, and damage to customer trust and the organisation's reputation. |
| Which of those consequences would matter most to this organisation's customers or regulators? | Customers would be particularly concerned about the privacy and security of their images, videos, location data, and flight information, as well as the safe and reliable operation of their drones. Regulators would be concerned about data protection, cybersecurity controls, compliance with applicable requirements, and risks that could affect public safety or national security. |


## Weekly reflection

- I moved from generic CIA definitions to concrete DJI assets such as flight-control systems, firmware, telemetry, and customer media.
- Integrity emerged as the leading concern for flight control because a manipulated command or navigation input can affect safety, not only data quality.
- The next improvement is to support sector examples and likelihood assumptions with traceable evidence rather than relying primarily on contextual judgement.

## Related case studies

- [DJI cyber-risk governance case study](../case-studies/dji-cyber-risk-governance.md)

---

[Back to the course index](../README.md)
