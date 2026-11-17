# CP5408 Assignment 2 - Case 3: `.io` Domain Name Crisis

> **Status:** Research and writing plan for review - not a submitted report.
>
> **Chosen case:** Option 3, *IO domain name crisis*.
>
> **Working role:** Strategic adviser to a technology company whose customer-facing products and services depend on one or more `.io` domains.

## 1. Assignment alignment

This README translates the A2 brief into a research plan. The final individual report should be submitted as one PDF or DOCX, use IEEE in-text citations and references, and be written as an evidence-backed strategic case study. The marking priorities are:

| Criterion | Weight | How this plan addresses it |
| --- | ---: | --- |
| Research quality and problem understanding | 30% | Separate verified DNS/governance facts from media claims; use primary IANA, government, ICANN and registry/registrar material. |
| Analysis, solutions and strategic recommendation | 40% | Compare credible response options, choose a risk-appetite-aware recommendation, and specify ownership, execution, controls and monitoring. |
| Clarity, structure and communication | 30% | Build a concise executive summary, use a decision table and risk register, and maintain correct IEEE citation practice. |

## 2. The case in one paragraph

The `.io` string is currently an active country-code top-level domain (ccTLD) associated in IANA's root-zone database with the British Indian Ocean Territory (BIOT) [1]. Its commercial popularity among technology companies creates a strategic dependency: a change in territorial, ISO-code, delegation, registry, or policy arrangements could affect continued use, renewal economics, brand trust, and migration cost. The UK-Mauritius agreement on the Chagos Archipelago creates a concrete governance context, but it does **not** by itself prove that `.io` will disappear or that a specific registrant will lose a name [2]. The report should therefore distinguish verified current status, plausible scenarios, and speculation.

## 3. Recommended research question and position

### Main question

**How should a technology company that relies on `.io` domains govern and reduce the combined continuity, security, legal, and reputational risks created by uncertainty around the `.io` ccTLD?**

### Proposed thesis

The company should not treat `.io` as an immediately failing asset, nor should it accept unmanaged concentration risk. It should adopt a **phased domain-resilience strategy**: retain `.io` where commercially valuable, establish equivalent primary domains under a stable alternative TLD, harden registrar and DNS governance, prepare customer communications, and use decision triggers to escalate migration if governance or operational indicators deteriorate.

This is a strategic recommendation to test against research, rather than a conclusion already established by evidence.

## 4. Scope and guardrails

### In scope

- ccTLD governance and delegation/redelegation concepts.
- Business continuity if a registry, registrar, renewal, DNS, certificate, or routing dependency changes.
- Cybersecurity controls for domain and DNS administration.
- Reputation and ethics relating to the Chagos/BIOT context.
- Cost, customer-experience, search, email, certificate, API, and supply-chain effects of domain migration.
- Governance of all material TLD and registrar dependencies, not only `.io`.

### Out of scope unless supported by evidence

- Claiming that `.io` is certain to be retired, transferred, or unavailable.
- Treating geopolitical reporting as a technical ICANN/IANA decision.
- Assessing a real organisation's confidential domain portfolio, security posture, or legal advice.
- Repeating unverified revenue figures or social-media commentary as factual evidence.

## 5. Key distinctions to keep accurate

| Topic | Correct treatment in the report |
| --- | --- |
| `.io` | ccTLD associated with BIOT in the current IANA record. Its future must be analysed as a governance and continuity uncertainty, not asserted as settled fact. |
| `.ai` | A different ccTLD associated with Anguilla. Its commercial value can be a useful comparative case about country-code domains and public revenue, but it is not evidence about `.io` operations. |
| UK-Mauritius agreement | Evidence of a changing political/legal context. Research whether and how this could affect ISO 3166-1 eligibility, IANA policy, delegation, registry arrangements, and registrants. |
| Bilibili video supplied in the brief | Useful for discovering public narratives and questions, but not a primary or sufficient academic source. Verify every factual claim independently before citing it. |

## 6. Research sub-questions

1. What does ownership or control of a top-level domain mean in practice? Distinguish the DNS root, IANA delegation records, registry operation, registrar services, registrant rights, and national/territorial governance.
2. What is `.io`'s current technical and administrative status, and what events would be required for a material change?
3. Which risks matter most to a hypothetical `.io`-dependent technology company: availability, renewal, DNS integrity, TLS/certificate continuity, phishing/typosquatting, legal/contractual exposure, migration cost, or reputation?
4. What public-relations and ethical risks arise from continued `.io` use, and how should the company communicate without making unsupported political claims?
5. Which options are feasible: retain and monitor; defensive registrations; dual-domain operation; staged migration; or accelerated migration?
6. How should the firm govern all domain assets and third parties: inventory, ownership, registrar lock, MFA, DNSSEC, renewal controls, escrow/backup arrangements, supplier review, and incident response?
7. What leading indicators should trigger an executive decision to accelerate migration or invoke continuity plans?

## 7. Proposed report structure

| Section | Purpose | Indicative evidence/output |
| --- | --- | --- |
| Executive summary | State the scenario, material findings, recommendation, and next actions. | 1-page decision summary. |
| Problem definition and scope | Explain why `.io` is a cyber-strategy and governance issue, not merely a branding issue. | Dependency map and precise research questions. |
| Context and evidence | Explain ccTLD governance, current `.io` status, and Chagos/BIOT context. | IANA/IETF/ICANN and government sources. |
| Risk assessment | Evaluate scenario likelihood, impact, owners, controls, uncertainty, and risk appetite. | Risk register with assumptions clearly labelled. |
| Options analysis | Compare retain-and-monitor, dual-domain resilience, staged migration, and rapid migration. | Weighted decision matrix; costs and trade-offs. |
| Recommendation and roadmap | Select one option or a phased combination. | 0-30 / 31-90 / 91-180 day plan. |
| Governance and monitoring | Show how the recommendation will be enforced and measured. | RACI, KPIs/KRIs, escalation triggers. |
| Conclusion | Restate the decision and residual risk. | Clear link back to the research question. |

## 8. Initial risk register

| ID | Risk statement | Example controls | Owner | Early indicator |
| --- | --- | --- | --- | --- |
| R1 | If `.io` governance, registry, or eligibility changes, then the company may incur migration, availability, and customer-trust impacts. | Alternate domain reserved; documented migration runbook; DNS architecture tested. | CIO / Head of Platform | Official IANA/ISO/registry notices or contract changes. |
| R2 | If the registrar or DNS account is compromised, then attackers may redirect traffic, disrupt services, or obtain certificates. | Hardware-backed MFA, least privilege, registrar lock, DNSSEC where appropriate, change alerts, emergency contacts. | CISO / Domain owner | Unauthorised change attempt, expiring credentials, missing audit log. |
| R3 | If stakeholders associate `.io` use with exploitation or political controversy, then the company may face reputational harm. | Ethics position, factual FAQ, communications approval process, stakeholder listening. | Communications / Legal | Sustained negative coverage, customer concern, campaign activity. |
| R4 | If migration is rushed, then email, SSO, OAuth redirects, APIs, certificates, SEO, and customer integrations may fail. | Dependency inventory, dual operation, test environment, rollback plan, customer notice. | CTO / Product | Untested critical dependency or failed migration exercise. |

## 9. Preferred strategy: phased domain resilience

### Phase 1 - establish control (0-30 days)

- Build an authoritative inventory of every domain, DNS zone, registrar account, certificate, redirect, email domain, API endpoint, OAuth callback, and third-party dependency.
- Assign a named business owner and technical owner for each critical domain.
- Enforce strong authentication, least privilege, registrar locks, renewal safeguards, and change monitoring.
- Register and validate a suitable alternative primary domain; do not announce a migration before technical and communications plans are ready.

### Phase 2 - reduce concentration risk (31-90 days)

- Implement and test dual-domain routing, canonical URLs, redirects, certificate issuance, email deliverability, and identity-provider integrations.
- Perform a tabletop exercise for loss of `.io` renewal, registry/registrar disruption, DNS hijack, and public controversy.
- Publish an internal decision log, risk appetite statement, and external FAQ draft.

### Phase 3 - maintain optionality (91-180 days)

- Decide whether to retain `.io` as primary, adopt a dual-brand model, or begin staged migration using defined triggers.
- Review supplier contracts, data portability, incident notification, continuity commitments, and exit support.
- Report residual risk and migration readiness to executive governance on a regular cadence.

## 10. Decision triggers and metrics

| Area | Example metric / trigger |
| --- | --- |
| Governance | Confirmed IANA, ISO, ICANN, registry, or registrar change affecting `.io` eligibility, delegation, service terms, or renewability. |
| Resilience | % of critical services tested on the alternate domain; target 100% before any forced migration. |
| Security | % of registrar/DNS privileged accounts protected by phishing-resistant MFA; target 100%. |
| Renewal | Days to expiry for every critical domain; escalation if below the organisation's defined threshold. |
| Reputation | Material customer/partner concern or sustained adverse coverage above a defined threshold. |
| Execution | Migration exercise pass rate, rollback time, and number of unresolved critical dependencies. |

## 11. Evidence plan

Use current, citable sources for the final report. Start with the following, then expand to scholarly literature, relevant standards, and primary contractual/technical documentation.

1. **IANA root-zone record for `.io`** - current classification, manager, technical status, and contacts [1].
2. **IANA ccTLD delegation/transition guidance** - clarify the process and avoid treating a territorial change as an automatic domain deletion [3].
3. **UK-Mauritius agreement and related official statements** - establish the geopolitical/legal context and its timing [2].
4. **ICANN/IETF/DNS standards and registrar agreements** - support recommendations about delegation, DNS security, registry/registrar roles, and operational resilience.
5. **NIST CSF 2.0 / ISO 27001-family material** - frame governance, ownership, supplier risk, continuity, and measurement.
6. **Peer-reviewed research and credible industry incident reports** - support claims about brand migration, DNS abuse, domain hijacking, and communication impacts.

### Source-quality rules

- Cite primary sources for status, rules, and technical processes.
- Treat news articles as contextual evidence, not the sole basis for a technical claim.
- Use the supplied Bilibili link only as a discovery lead unless its claims can be independently verified.
- In the final report, convert all retained sources to IEEE citation and reference-list format.

## 12. Starter IEEE-style reference list

The final report must check access dates and exact IEEE formatting before submission.

[1] Internet Assigned Numbers Authority, “.io Top-Level Domain,” *IANA Root Zone Database*. [Online]. Available: https://www.iana.org/domains/root/db/io.html. [Accessed: 17-Nov-2026].

[2] UK Foreign, Commonwealth & Development Office, “UK/Mauritius: Agreement concerning the Chagos Archipelago including Diego Garcia,” 22-May-2025. [Online]. Available: https://www.gov.uk/government/publications/ukmauritius-agreement-concerning-the-chagos-archipelago-including-diego-garcia-cs-mauritius-no12025. [Accessed: 17-Nov-2026].

[3] Internet Assigned Numbers Authority, “Common Questions on delegating and transferring country-code top-level domains.” [Online]. Available: https://www.iana.org/help/cctld-delegation-answers. [Accessed: 17-Nov-2026].

## 13. Next research actions

1. Read the `.io` IANA record and IANA transition guidance in full; record only claims that can be cited.
2. Build a factual timeline for BIOT/Chagos developments, clearly marking completed events versus proposed or conditional changes.
3. Identify a hypothetical company profile (for example, a SaaS firm with APIs and global customers) and define its risk appetite.
4. Research at least three comparable domain-governance or domain-migration incidents.
5. Develop a decision matrix with explicit criteria: continuity, security, cost, brand, customer impact, legal/contractual feasibility, and reversibility.
6. Draft the executive summary last, after the evidence and recommendation are stable.

## 14. Review questions for you

- Do you want the hypothetical company to be a startup, a mature global SaaS company, or another type of organisation?
- Do you want `.ai`/Anguilla to be a short comparison only, or a dedicated comparative subsection?
- Should the report recommend keeping `.io` with resilience controls, or do you want to argue for proactive migration as the preferred strategy?

