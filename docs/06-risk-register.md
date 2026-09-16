# Cybersecurity Risk Register

## Purpose

This register documents and prioritizes cybersecurity risks across Peachtree Logistics Group's people, processes, technology, facilities, information, and third-party relationships. It connects the approved scope, data flows, asset inventory, and risk methodology to accountable decisions and treatment actions.

This is a scenario-based portfolio artifact. Current-control descriptions and current residual-risk ratings are preliminary assumptions requiring validation through interviews, documentation, configuration review, logs, sampling, and control testing.

## Scoring Reference

Scores follow `docs/05-risk-assessment-methodology.md`.

> **Risk Score = Likelihood × Impact**

| Score | Rating |
|---:|---|
| 17–25 | Critical |
| 10–16 | High |
| 5–9 | Moderate |
| 1–4 | Low |

- **Inherent risk:** Exposure before safeguards.
- **Current residual risk:** Estimated exposure after assumed current safeguards.
- **Target residual risk:** Expected exposure after proposed treatment is implemented and proven effective.
- **Evidence confidence:** Strength of evidence supporting the condition and control assessment.

## Prioritized Risk Register

| ID | Risk Title | Primary Assets | Risk Owner | Inherent Risk | Current Residual | Confidence | Response | Target Residual | Status |
|---|---|---|---|---:|---:|---|---|---:|---|
| R-01 | Phishing and Account Compromise | A-01, A-02, A-03, A-05, A-06, A-13, A-14 | IT Director | 5 × 5 = **25 Critical** | 4 × 5 = **20 Critical** | Medium | Mitigate | 2 × 5 = **10 High** | Open |
| R-02 | Delayed or Incomplete Account Deprovisioning | A-02, A-03, A-04, A-05, A-06, A-15 | IT Director; HR Manager | 4 × 4 = **16 High** | 4 × 4 = **16 High** | Medium | Mitigate | 2 × 4 = **8 Moderate** | Open |
| R-03 | Excessive or Conflicting Access Privileges | A-02, A-03, A-04, A-05, A-06, A-13, A-14 | IT Director; System Owners | 4 × 4 = **16 High** | 3 × 4 = **12 High** | Low | Mitigate | 2 × 4 = **8 Moderate** | Open |
| R-04 | Independent-Courier and BYOD Data Exposure | A-05, A-09, A-10, A-13, A-14 | Dispatch Manager; IT Director | 4 × 4 = **16 High** | 4 × 4 = **16 High** | Medium | Mitigate | 2 × 4 = **8 Moderate** | Open |
| R-05 | Unauthorized PHI/ePHI Access or Disclosure | A-01, A-05, A-07, A-13, A-14 | Medical Courier Program Manager | 3 × 5 = **15 High** | 3 × 5 = **15 High** | Low | Mitigate | 2 × 5 = **10 High** | Open |
| R-06 | Sensitive Information in Email and Collaboration Tools | A-01, A-13, A-14, A-16 | Operations Director; IT Director | 4 × 4 = **16 High** | 4 × 4 = **16 High** | Medium | Mitigate | 2 × 4 = **8 Moderate** | Open |
| R-07 | Unpatched or Poorly Segmented Warehouse Systems | A-04, A-11, A-13, A-20 | IT Director; Warehouse Operations Manager | 4 × 5 = **20 Critical** | 3 × 5 = **15 High** | Low | Mitigate | 2 × 5 = **10 High** | Open |
| R-08 | Critical Vendor Breach or Service Outage | A-03, A-05, A-06, A-18, A-19 | Vendor Management; System Owner | 3 × 5 = **15 High** | 3 × 5 = **15 High** | Low | Mitigate / Transfer | 2 × 5 = **10 High** | Open |
| R-09 | Insufficient Logging and Security Monitoring | A-02, A-03, A-04, A-05, A-06, A-17 | IT Director | 4 × 4 = **16 High** | 4 × 4 = **16 High** | Low | Mitigate | 2 × 4 = **8 Moderate** | Open |
| R-10 | Excessive Data Retention and Insecure Disposal | A-01, A-05, A-06, A-07, A-13, A-14, A-15, A-16 | Compliance Manager; Data Owners | 3 × 4 = **12 High** | 3 × 4 = **12 High** | Low | Mitigate | 2 × 4 = **8 Moderate** | Open |
| R-11 | Payment and Financial Data Exposure | A-06, A-13, A-19 | Finance Manager | 3 × 5 = **15 High** | 2 × 5 = **10 High** | Low | Mitigate / Transfer | 1 × 5 = **5 Moderate** | Open |
| R-12 | Inadequate Backup, Recovery, and Continuity | A-01, A-02, A-03, A-04, A-05, A-06, A-07, A-11 | IT Director; Operations Director | 3 × 5 = **15 High** | 3 × 5 = **15 High** | Low | Mitigate | 2 × 5 = **10 High** | Open |
| R-13 | Unauthorized Physical Access to PLG Facilities | A-04, A-11, A-12, A-13, A-20 | Facilities Manager; Warehouse Operations Manager | 3 × 4 = **12 High** | 2 × 4 = **8 Moderate** | Low | Mitigate | 1 × 4 = **4 Low** | Open |
| R-14 | Controls That Create Unsafe or Unworkable Driver Behavior | A-05, A-09, A-10, A-13, A-14 | Dispatch Manager; Safety Manager | 3 × 5 = **15 High** | 3 × 5 = **15 High** | Medium | Mitigate | 1 × 5 = **5 Moderate** | Open |

## Risk Statements and Treatments

### R-01 — Phishing and Account Compromise

**Risk statement:** Because PLG faces increased phishing attempts and may not consistently enforce strong authentication and conditional access, a threat actor could compromise a workforce account and access email, logistics, dispatch, billing, customer, or medical-delivery information, resulting in fraud, data exposure, disruption, and loss of trust.

**Treatment:** Enforce appropriate MFA and conditional access; disable legacy authentication; monitor risky sign-ins; provide role-specific simulations; establish account-containment and token-revocation procedures.

### R-02 — Delayed or Incomplete Account Deprovisioning

**Risk statement:** Because PLG may not use an integrated joiner-mover-leaver process, terminated employees, transferred personnel, or former couriers could retain unnecessary access, resulting in unauthorized activity or information exposure.

**Treatment:** Establish HR-triggered workflows, termination deadlines, separate courier identities, account reconciliation, and reviews for dormant, shared, duplicate, and orphaned accounts.

### R-03 — Excessive or Conflicting Access Privileges

**Risk statement:** Because PLG has not standardized role-based access across its hybrid environment, users may accumulate excessive or conflicting permissions, enabling unauthorized changes, data access, fraud, or concealment of errors.

**Treatment:** Create a role catalog and permission matrix; enforce least privilege and segregation of duties; require data-owner approval; conduct periodic access reviews; time-limit exceptions.

### R-04 — Independent-Courier and BYOD Data Exposure

**Risk statement:** Because courier and personal devices operate outside or partially outside PLG's management boundary, sensitive route, recipient, location, proof-of-delivery, or medical-delivery information could be stored, displayed, shared, or retained insecurely.

**Treatment:** Separate courier identities; limit access by assignment and duration; apply application protection, encryption, session timeout, and remote revocation; minimize local storage; establish BYOD requirements.

### R-05 — Unauthorized PHI/ePHI Access or Disclosure

**Risk statement:** Because PLG has not validated where PHI/ePHI enters, moves through, or remains in its workflows, personnel, contractors, vendors, or unauthorized recipients could access or disclose protected information.

**Treatment:** Validate PHI/ePHI scope; minimize collection and display; restrict access by role and assignment; encrypt applicable data; establish recipient-verification, escalation, retention, and disposal requirements; obtain qualified privacy review.

### R-06 — Sensitive Information in Email and Collaboration Tools

**Risk statement:** Because orders and exceptions may be handled through email and collaboration tools, employees may create uncontrolled copies of sensitive information, increasing misdelivery, oversharing, excessive retention, and unauthorized access.

**Treatment:** Define approved channels; redirect information to systems of record; configure sharing restrictions, retention labels, and DLP; review forwarding and guest access; provide workflow-specific training.

### R-07 — Unpatched or Poorly Segmented Warehouse Systems

**Risk statement:** Because warehouse systems may have inconsistent patching, unsupported components, weak segmentation, or excessive local privilege, a threat actor or malware event could compromise fulfillment operations and connected services.

**Treatment:** Validate software and vulnerability inventories; establish risk-based patching; segment warehouse systems; restrict administrative access; test backups, restoration, and manual workarounds.

### R-08 — Critical Vendor Breach or Service Outage

**Risk statement:** Because PLG depends on external logistics, dispatch, billing, identity, and payment services, a vendor breach, outage, support-access failure, or control weakness could expose information or interrupt operations beyond PLG's direct control.

**Treatment:** Tier vendors; perform due diligence; strengthen security and notification clauses; review assurance reports; track exceptions; document contingency, data-export, and exit plans.

### R-09 — Insufficient Logging and Security Monitoring

**Risk statement:** Because PLG may not centrally collect, retain, correlate, and review security-relevant logs, malicious or inappropriate activity could remain undetected and increase the consequences of an incident.

**Treatment:** Define logging requirements; centralize priority events; assign alert ownership and escalation; protect log integrity; test high-value detection use cases.

### R-10 — Excessive Data Retention and Insecure Disposal

**Risk statement:** Because PLG has not validated consistent retention and disposal rules across email, operational systems, mobile applications, billing, and archives, sensitive records may remain accessible longer than necessary.

**Treatment:** Create a retention schedule; define systems of record; remove unnecessary copies; configure deletion; validate mobile, backup, archive, vendor, and terminated-account handling; document legal holds and disposal.

### R-11 — Payment and Financial Data Exposure

**Risk statement:** Because PLG's payment-data flow has not been validated, financial or cardholder information could be unnecessarily stored, transmitted, intercepted, or accessed, resulting in fraud, financial loss, contractual consequences, and potential PCI DSS exposure.

**Treatment:** Map payment flows; minimize retained data; use tokenized or hosted processing where feasible; restrict billing access; enforce segregation of duties; monitor changes and validate processor assurance.

### R-12 — Inadequate Backup, Recovery, and Continuity

**Risk statement:** Because recovery objectives, backup coverage, restoration testing, vendor dependencies, and manual workarounds may not be consistently defined, an attack, failure, outage, or data-loss event could cause prolonged disruption.

**Treatment:** Complete a business impact analysis; define RTOs and RPOs; map PLG and vendor responsibilities; protect backups; test restoration; document manual operations; conduct tabletop exercises.

### R-13 — Unauthorized Physical Access to PLG Facilities

**Risk statement:** Because badge administration, visitor management, restricted-area access, and physical-access reviews may be inconsistent, an unauthorized person could enter PLG facilities or sensitive areas and cause theft, tampering, exposure, or disruption.

**Treatment:** Define physical-access roles; integrate badge lifecycle processes; review active badges and after-hours activity; secure sensitive areas; test lost-badge, tailgating, visitor, and termination procedures.

### R-14 — Controls That Create Unsafe or Unworkable Driver Behavior

**Risk statement:** Because controls may be designed without accounting for mobile, time-sensitive, and safety-critical work, drivers or couriers could bypass safeguards, share credentials, delay updates, or interact with devices while driving.

**Treatment:** Observe workflows; limit interaction to safe points; use appropriate reauthentication; minimize mobile steps and displayed data; establish exceptions and escalation; monitor workarounds and frontline feedback.

## Current Residual-Risk Summary

| Rating | Number | Risk IDs |
|---|---:|---|
| Critical | 1 | R-01 |
| High | 12 | R-02, R-03, R-04, R-05, R-06, R-07, R-08, R-09, R-10, R-11, R-12, R-14 |
| Moderate | 1 | R-13 |
| Low | 0 | None |

## Target Residual-Risk Summary

| Rating | Number | Risk IDs |
|---|---:|---|
| Critical | 0 | None |
| High | 5 | R-01, R-05, R-07, R-08, R-12 |
| Moderate | 8 | R-02, R-03, R-04, R-06, R-09, R-10, R-11, R-14 |
| Low | 1 | R-13 |

Some target risks remain High because controls can reduce likelihood without eliminating the potentially severe impact of account compromise, sensitive-data exposure, critical-system disruption, or vendor failure.

## Treatment Priorities

### Priority 1 — Immediate to 30 Days

- Strengthen authentication for privileged and high-risk accounts.
- Begin phishing and account-compromise response improvements.
- Confirm PHI/ePHI and payment-data scope.
- Identify former, dormant, shared, and orphaned accounts.
- Validate critical WMS vulnerabilities, support status, backups, and network exposure.

### Priority 2 — 31 to 90 Days

- Implement RBAC and standardized joiner-mover-leaver procedures.
- Strengthen independent-courier and BYOD controls.
- Reduce sensitive information in email and collaboration tools.
- Establish priority logging and monitoring use cases.
- Implement high-priority vendor, medical-delivery, payment, and physical safeguards.

### Priority 3 — 91 to 180 Days

- Complete vendor-tiering and continuity planning.
- Implement retention, archive, and disposal requirements.
- Expand control testing, restoration exercises, and tabletop exercises.
- Measure control adoption, exceptions, workflow friction, and residual risk.

## Required Management Decisions

1. Confirm the owner for every risk.
2. Approve or revise each response and timeline.
3. Allocate resources for Critical and High risks.
4. Define risk-acceptance authority and escalation thresholds.
5. Require documented approval for delayed treatment or accepted residual risk.
6. Prioritize evidence collection for risks with Low confidence.

## Review Cadence

- Critical risks: at least monthly until reduced below Critical
- High risks: at least quarterly and during active remediation
- Moderate risks: at least semiannually
- Low risks: at least annually
- All risks: after significant incidents, system or vendor changes, material business changes, or invalidated assumptions

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. Risk scores, current-control descriptions, and treatment timelines demonstrate a structured GRC approach and are not findings from a real organization.
