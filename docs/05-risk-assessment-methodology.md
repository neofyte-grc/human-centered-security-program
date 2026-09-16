# Risk Assessment Methodology

## Purpose

This methodology defines how Peachtree Logistics Group (PLG) identifies, analyzes, evaluates, prioritizes, treats, and monitors cybersecurity risks. It creates a consistent scoring model for the risk register and supports transparent, repeatable decision-making.

The methodology is designed for a fictional, portfolio-based assessment. It uses a semi-quantitative model because PLG does not yet have sufficient historical loss data to support precise financial risk calculations.

## Framework Alignment

The methodology is informed by:

- [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework), which organizes cybersecurity outcomes across Govern, Identify, Protect, Detect, Respond, and Recover.
- [NIST SP 800-30 Revision 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final), which provides guidance for conducting organizational and information-system risk assessments.

These sources guide the assessment but do not make PLG a federal system or establish regulatory compliance. Any HIPAA, PCI DSS, contractual, or other compliance applicability must be validated separately.

## Assessment Principles

1. **Business context first:** Risks are evaluated according to their effect on PLG's operations, customers, workforce, safety, contractual commitments, and sensitive information.
2. **Evidence over assumption:** Findings should be supported by documentation, interviews, configuration evidence, logs, observation, or testing. Unverified conditions must be labeled as assumptions, hypotheses, or evidence gaps.
3. **People, process, technology, and third parties:** Risk analysis must consider human behavior and operational workflow alongside technical weaknesses.
4. **Inherent and residual risk are separate:** Inherent risk reflects exposure before considering relevant controls. Residual risk reflects the exposure expected after considering existing or proposed controls.
5. **Risk ownership belongs to the business:** The GRC Analyst facilitates and documents the assessment. Designated business leaders own risk-response and acceptance decisions.
6. **Operational practicality matters:** Recommendations should reduce risk without introducing unreasonable friction, unsafe driver behavior, or avoidable disruption to time-sensitive logistics services.

## Assessment Scope

The assessment covers the people, processes, information, systems, facilities, and third parties identified in:

- `docs/01-project-charter.md`
- `docs/02-stakeholder-analysis.md`
- `docs/03-data-flow-diagrams.md`
- `docs/04-asset-and-system-inventory.md`

The assessment does not include active exploitation, penetration testing, direct inspection of vendor-owned environments, vehicle mechanical systems, or physical building construction.

## Evidence Sources

Risk conclusions may use the following evidence:

- Leadership, system-owner, manager, and workforce interviews
- Policies, standards, procedures, and training materials
- Asset, software, vendor, and account inventories
- Identity-provider configuration and access-control documentation
- User, role, group, privileged-account, and access-review records
- Authentication, security, system, and operational logs
- Mobile-device management and BYOD configuration evidence
- Network diagrams, data-flow diagrams, and system integration records
- Vulnerability, patching, backup, and restoration evidence
- Vendor contracts, security exhibits, assurance reports, and incident-notification terms
- Physical-access records, visitor procedures, and facility walkthroughs
- Incident records, help-desk tickets, and exception documentation
- Data-retention schedules and secure-disposal evidence

## Risk Identification Approach

Risks will be identified by examining:

1. Critical business services and workflow dependencies
2. Information classification and data movement
3. Threat sources and plausible threat events
4. Vulnerabilities, control gaps, and unsafe workarounds
5. Existing safeguards and their operating evidence
6. Third-party dependencies and shared-responsibility boundaries
7. Legal, regulatory, contractual, privacy, safety, and operational consequences
8. Concentration risks involving IAM, logistics, dispatch, warehouse, billing, and archive services

## Risk Statement Format

Each risk should be written using a cause-event-impact structure:

> Because **[condition, vulnerability, or control gap]**, **[threat source]** could **[threat event]**, resulting in **[business, operational, privacy, legal, financial, safety, or reputational impact]**.

### Example

> Because PLG lacks a consistent process for promptly disabling contractor accounts, a former independent courier could retain access to the dispatch platform, resulting in unauthorized exposure of customer, recipient, route, or delivery information.

Risk statements should describe uncertain future events. Confirmed control deficiencies may be documented as findings that support one or more risk statements.

## Likelihood Scale

Likelihood represents the probability that the described risk event will occur within the assessment horizon, considering threat activity, exposure, ease of exploitation, frequency of opportunity, and existing conditions.

| Score | Rating | Definition |
|---:|---|---|
| 1 | Rare | The event is highly unlikely and would require unusual circumstances. No meaningful history or current indicators suggest occurrence. |
| 2 | Unlikely | The event could occur but is not expected under normal conditions. Exposure or threat activity is limited. |
| 3 | Possible | The event is credible and may occur. Relevant exposure, weaknesses, or industry threat activity exists. |
| 4 | Likely | The event is expected to occur or has occurred in similar environments. Exposure is recurring or controls are inconsistent. |
| 5 | Almost Certain | The event is occurring, has recently occurred, or is expected frequently because exposure is persistent and controls are absent or ineffective. |

## Impact Scale

Impact represents the reasonably foreseeable consequence if the risk event occurs. Assessors should consider operations, privacy, legal and contractual obligations, finances, safety, customers, and reputation. The final impact score should reflect the highest credible material consequence—not an average that hides a severe outcome.

| Score | Rating | Definition |
|---:|---|---|
| 1 | Minimal | Little operational effect; negligible cost or data exposure; recovery occurs through routine work. |
| 2 | Minor | Limited disruption or exposure affecting a small number of users, records, or tasks; manageable within normal departmental processes. |
| 3 | Moderate | Noticeable service disruption, customer impact, sensitive-data exposure, contractual concern, or remediation cost requiring coordinated management attention. |
| 4 | Major | Significant operational interruption, material privacy or financial harm, loss of an important client, major contractual consequences, or substantial recovery effort. |
| 5 | Severe | Prolonged or widespread operational failure, serious safety consequences, large-scale sensitive-data exposure, severe legal or regulatory consequences, or existential reputational or financial harm. |

## Impact Dimensions

Each risk should be evaluated across the following dimensions:

| Dimension | Evaluation Question |
|---|---|
| Operations | Could the event delay or stop dispatch, warehouse, delivery, medical-courier, billing, or customer-service operations? |
| Data and privacy | Could it expose, alter, destroy, or make unavailable PII, PHI/ePHI, financial information, credentials, shipment information, or business records? |
| Legal and contractual | Could it violate applicable law, client commitments, retention requirements, notification terms, or vendor agreements? |
| Financial | Could it create fraud, lost revenue, recovery expense, contractual penalties, legal costs, or customer loss? |
| Safety | Could it encourage unsafe driver behavior, disrupt time-sensitive medical deliveries, or affect physical security? |
| Reputation and customer trust | Could it materially reduce confidence among clients, recipients, partners, or the workforce? |

## Inherent-Risk Calculation

Inherent risk is scored before considering the effect of existing or proposed safeguards.

> **Inherent Risk Score = Likelihood × Impact**

| Score | Rating | Required Action |
|---:|---|---|
| 17–25 | Critical | Immediate executive attention; begin treatment planning promptly and consider interim safeguards |
| 10–16 | High | Prioritized treatment plan, accountable owner, target date, and management monitoring required |
| 5–9 | Moderate | Manage through planned remediation, monitoring, or documented acceptance by the appropriate owner |
| 1–4 | Low | Manage through routine controls and periodic review; document any acceptance decision |

### Risk Matrix

| Likelihood ↓ / Impact → | 1 Minimal | 2 Minor | 3 Moderate | 4 Major | 5 Severe |
|---|---:|---:|---:|---:|---:|
| 5 Almost Certain | 5 Moderate | 10 High | 15 High | 20 Critical | 25 Critical |
| 4 Likely | 4 Low | 8 Moderate | 12 High | 16 High | 20 Critical |
| 3 Possible | 3 Low | 6 Moderate | 9 Moderate | 12 High | 15 High |
| 2 Unlikely | 2 Low | 4 Low | 6 Moderate | 8 Moderate | 10 High |
| 1 Rare | 1 Low | 2 Low | 3 Low | 4 Low | 5 Moderate |

## Control-Effectiveness Scale

Control effectiveness is assessed using design, implementation, coverage, consistency, evidence, and sustainability.

| Score | Rating | Definition |
|---:|---|---|
| 0 | Not Present | No relevant control exists or the control is not implemented. |
| 1 | Weak | The control is informal, inconsistently applied, poorly designed, or unsupported by reliable evidence. |
| 2 | Partially Effective | The control addresses part of the risk but has coverage, consistency, ownership, evidence, or operating gaps. |
| 3 | Effective | The control is appropriately designed, implemented, consistently performed, and supported by evidence. Minor improvements may remain. |
| 4 | Strong | The control is well designed, broadly integrated, measured, routinely tested, and continuously improved. |

A policy or configured setting alone does not prove effectiveness. The assessment should seek evidence that the control operates consistently for the relevant users, systems, locations, and time period.

## Residual-Risk Assessment

Residual risk will be evaluated by reassessing likelihood and impact after considering relevant existing or proposed controls.

> **Residual Risk Score = Reassessed Likelihood × Reassessed Impact**

PLG will not apply a simple percentage discount to inherent risk. A control may reduce likelihood, impact, both, or neither. Reassessment must therefore explain:

- Which part of the risk scenario the control changes
- Whether the control is preventive, detective, corrective, deterrent, compensating, or recovery-oriented
- The evidence supporting the effectiveness rating
- Any remaining exposure, dependency, exception, or uncertainty

Proposed controls without operating evidence may support a **target residual risk** estimate, but they must not be represented as the current residual-risk level.

## Evidence-Confidence Rating

Each risk will receive an evidence-confidence rating so decision-makers can distinguish well-supported conclusions from hypotheses requiring validation.

| Rating | Definition |
|---|---|
| High | Conclusion is supported by multiple reliable sources, such as configuration evidence, logs, approved documentation, testing, and corroborated interviews. |
| Medium | Conclusion is supported by some reliable evidence but contains gaps, limited sampling, or dependence on interviews or incomplete documentation. |
| Low | Conclusion relies mainly on assumptions, unverified statements, missing documentation, or limited visibility. Additional evidence is required. |

A high risk score with low evidence confidence should trigger prioritized validation—not automatic dismissal or unqualified acceptance of the rating.

## Risk-Response Options

| Response | Description |
|---|---|
| Avoid | Stop or redesign the activity that creates the risk. |
| Mitigate | Implement or strengthen controls to reduce likelihood, impact, or both. |
| Transfer | Shift defined financial or operational consequences through insurance or contract while recognizing that accountability and reputational exposure may remain. |
| Accept | Formally acknowledge the residual risk and approve continued exposure within defined authority and review conditions. |

## Risk Ownership and Decision Authority

| Role | Responsibility |
|---|---|
| Risk owner | Accountable business leader who decides how the risk will be addressed and accepts the remaining exposure within delegated authority |
| Control owner | Person accountable for designing, implementing, operating, and evidencing a safeguard |
| Action owner | Person responsible for completing a specific remediation task by the approved target date |
| GRC Analyst | Facilitates assessment, challenges unsupported conclusions, maintains risk documentation, and reports status |
| Executive sponsor | Resolves priority or resource conflicts and reviews risks outside delegated tolerance or acceptance authority |

Critical and High risks should not be accepted informally. Acceptance must document the rationale, approver, duration, compensating safeguards, monitoring requirements, and next review date.

## Assessment Workflow

1. **Prepare:** Confirm scope, stakeholders, assumptions, constraints, scoring criteria, and evidence needs.
2. **Identify assets and processes:** Use the inventory, stakeholder analysis, and data-flow diagrams to identify critical services and information.
3. **Identify threats and weaknesses:** Document credible threat sources, threat events, vulnerabilities, control gaps, and unsafe workarounds.
4. **Develop risk statements:** Express each risk using the approved cause-event-impact format.
5. **Score inherent risk:** Assign likelihood and impact before considering relevant controls.
6. **Evaluate controls:** Assess design, implementation, coverage, consistency, evidence, and sustainability.
7. **Score residual risk:** Reassess likelihood and impact based on supported control effectiveness.
8. **Select a response:** Avoid, mitigate, transfer, or accept the risk.
9. **Assign accountability:** Name risk, control, and action owners with target dates.
10. **Monitor and report:** Track remediation, evidence, metrics, exceptions, and changes in risk exposure.

## Review and Monitoring Requirements

The risk assessment should be reviewed:

- At least annually
- After a significant incident or control failure
- When PLG introduces a material system, integration, vendor, location, or business service
- When legal, regulatory, contractual, or client requirements materially change
- When threat intelligence or vulnerability information indicates a meaningful change in exposure
- When repeated exceptions, workarounds, or KPI/KRI thresholds suggest a control is not operating as intended

## Methodology Limitations

- Scores are decision aids and should not be treated as precise predictions of loss.
- Rating consistency depends on evidence quality and calibrated assessor judgment.
- Missing documentation is not proof that a control is absent, but it reduces assurance and should be recorded as an evidence gap.
- The fictional scenario does not provide complete configuration, incident, financial-loss, or contractual data.
- Compliance applicability and legal conclusions require qualified review and are outside the authority of this portfolio assessment.

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. This methodology demonstrates a structured GRC assessment approach and does not constitute legal, regulatory, or compliance advice.
