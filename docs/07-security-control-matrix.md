# Security Control Matrix

## Purpose

This matrix translates the risks in the Peachtree Logistics Group risk register into proposed administrative, technical, physical, detective, corrective, and recovery controls. It identifies ownership, operating frequency, expected evidence, implementation priority, and relevant framework references.

The matrix supports control design and traceability. It does not claim that the proposed controls are currently implemented or operating effectively.

## Framework References

Control mappings are informed by:

- [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
- [NIST SP 800-53 Revision 5, Release 5.2.0](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)

Framework references indicate a reasonable relationship between the proposed PLG control and the referenced outcome or control. They do not establish one-to-one equivalency, certification, or compliance.

## Control-Type Legend

| Type | Purpose |
|---|---|
| Preventive | Reduces the likelihood that an unwanted event will occur |
| Detective | Identifies events, failures, or unauthorized activity |
| Corrective | Restores an approved state after a problem is identified |
| Recovery | Restores services, information, or operations after disruption |
| Deterrent | Discourages prohibited or inappropriate behavior |
| Compensating | Provides alternate protection when the preferred control is unavailable |

## Implementation Priority

| Priority | Target Window | Meaning |
|---|---|---|
| P1 | 0–30 days | Immediate action for Critical exposure, urgent scoping, or foundational control gaps |
| P2 | 31–90 days | High-priority implementation after immediate stabilization |
| P3 | 91–180 days | Program expansion, optimization, resilience, or longer-term maturity |

## Security Control Matrix

| Control ID | Control Objective and Requirement | Related Risks | Type | Control Owner | Frequency | Expected Evidence | Priority | NIST CSF 2.0 | NIST SP 800-53 Rev. 5 |
|---|---|---|---|---|---|---|---|---|---|
| CTL-01 | Require MFA for workforce, privileged, remote, cloud, and other high-risk access. Use phishing-resistant methods where practical and prioritize privileged users. | R-01, R-03, R-05, R-11 | Preventive | IT Director | Continuous; quarterly coverage review | MFA configuration, enrollment report, exception list, authentication logs | P1 | PR.AA | IA-2, IA-5 |
| CTL-02 | Apply conditional-access rules based on identity risk, device compliance, location, application sensitivity, and privilege. Disable legacy authentication where supported. | R-01, R-04, R-05, R-06 | Preventive / Detective | IT Director | Continuous; quarterly rule review | Conditional-access policies, sign-in logs, legacy-authentication report, exceptions | P1 | PR.AA, DE.CM | AC-2, AC-17, IA-2, SI-4 |
| CTL-03 | Implement an HR- and manager-triggered joiner-mover-leaver process with defined approval, provisioning, modification, and termination deadlines. | R-02, R-03, R-13 | Preventive / Corrective | HR Manager; IT Director | Per event; monthly reconciliation | Workflow tickets, approval records, HR/account reconciliation, termination timestamps | P1 | PR.AA, GV.RR | AC-2, IA-4, PS-4, PS-5 |
| CTL-04 | Establish role-based access using least privilege, data-owner approval, and segregation-of-duties requirements. | R-03, R-05, R-11 | Preventive | IT Director; System and Data Owners | Per request; annual role review | Role catalog, permission matrix, approvals, segregation analysis, exceptions | P2 | PR.AA | AC-3, AC-5, AC-6 |
| CTL-05 | Perform periodic reviews of users, groups, roles, privileged access, service accounts, shared accounts, and independent-courier access. | R-02, R-03, R-04, R-05, R-11 | Detective / Corrective | System Owners; GRC Analyst | Quarterly for high-risk systems; semiannual otherwise | Access exports, reviewer sign-off, removals, exceptions, completion metrics | P2 | PR.AA, ID.IM | AC-2, AC-6, CA-7 |
| CTL-06 | Separate employee, administrator, service, vendor, and independent-courier identities. Prohibit credential sharing and time-limit temporary access. | R-02, R-03, R-04, R-08, R-09 | Preventive / Detective | IT Director | Continuous; quarterly review | Account naming standard, identity inventory, temporary-access logs, shared-account exceptions | P1 | PR.AA | AC-2, IA-2, IA-4 |
| CTL-07 | Apply mobile application and device safeguards, including encryption, session timeout, remote revocation, minimum device posture, and restrictions on unnecessary local storage. | R-04, R-05, R-14 | Preventive / Corrective | IT Director; Dispatch Manager | Continuous; quarterly compliance review | MDM or application-protection settings, device inventory, compliance reports, revocation tests | P2 | PR.AA, PR.DS, PR.PS | AC-19, AC-20, MP-5, SC-13 |
| CTL-08 | Classify information and minimize collection, display, sharing, and retention according to role, assignment, client, and business need. | R-04, R-05, R-06, R-10, R-11 | Preventive | Compliance Manager; Data Owners | Annual and upon workflow change | Classification standard, data inventory, field-level requirements, approved exceptions | P2 | GV.OC, ID.AM, PR.DS | AC-3, MP-3, PT-2, PT-3 |
| CTL-09 | Configure Microsoft 365 sharing, forwarding, guest access, retention labels, and data-loss-prevention safeguards for Confidential and Restricted information. | R-01, R-05, R-06, R-10 | Preventive / Detective | IT Director; Compliance Manager | Continuous; quarterly review | DLP policies, sharing reports, forwarding rules, guest inventory, retention configuration | P2 | PR.DS, DE.CM | AC-3, AC-4, AU-2, SC-8 |
| CTL-10 | Validate PHI/ePHI handling and implement minimum-necessary access, encryption, recipient verification, escalation, retention, and disposal requirements where applicable. | R-05, R-06, R-10, R-14 | Preventive / Detective / Corrective | Medical Courier Program Manager; Compliance Manager | Per transaction; annual program review | Data-flow validation, access lists, encryption settings, recipient procedures, training, incident records | P1 | GV.OC, PR.AA, PR.DS, RS.MA | AC-3, SC-8, SC-13, IR-6, MP-6 |
| CTL-11 | Maintain an authorized inventory of hardware, software, cloud services, mobile endpoints, integrations, vendors, and business owners. | R-04, R-07, R-08, R-09, R-12 | Preventive / Detective | IT Director; Vendor Management | Monthly reconciliation; annual certification | Asset inventory, software inventory, SaaS list, owner certification, discrepancy log | P1 | ID.AM | CM-8, PM-5 |
| CTL-12 | Establish risk-based vulnerability and patch management for warehouse and other in-scope systems, including deadlines, validation, and documented exceptions. | R-07, R-08, R-12 | Preventive / Corrective | IT Director | Continuous scanning; monthly patch cycle; urgent critical remediation | Scan reports, patch reports, support status, exception approvals, remediation tickets | P1 | ID.RA, PR.PS | RA-5, SI-2 |
| CTL-13 | Segment warehouse, user, guest, vendor, administrative, and sensitive-system traffic according to business need and deny unnecessary connectivity. | R-01, R-07, R-09, R-12 | Preventive | IT Director | Continuous; semiannual rule review | Network diagrams, firewall rules, segmentation tests, approved exceptions | P2 | PR.PS | AC-4, SC-7 |
| CTL-14 | Define minimum security logging, centralized collection, retention, alert ownership, escalation, and detection use cases for high-value systems. | R-01, R-02, R-03, R-04, R-05, R-07, R-09, R-11 | Detective | IT Director; Security Operations Lead | Continuous monitoring; monthly use-case review | Logging standard, source inventory, SIEM records, alert rules, tickets, retention settings | P1 | DE.CM, DE.AE | AU-2, AU-6, AU-11, SI-4 |
| CTL-15 | Tier vendors by data sensitivity and operational criticality; perform due diligence and establish security, access, notification, recovery, subcontractor, audit, and termination requirements. | R-08, R-11, R-12 | Preventive / Detective | Vendor Management; System Owners | Before onboarding; annually for critical vendors | Vendor inventory, tiering, questionnaires, contracts, assurance reports, tracked exceptions | P2 | GV.SC | SA-9, SR-3, SR-5, SR-6 |
| CTL-16 | Minimize PLG's payment-data exposure by using approved processors, restricting billing access, monitoring sensitive changes, and validating PCI DSS applicability. | R-03, R-11 | Preventive / Detective | Finance Manager; IT Director | Per transaction; quarterly access and control review | Payment-flow diagram, processor agreement, access review, reconciliation, change logs | P1 | GV.OC, PR.AA, PR.DS | AC-5, AC-6, AU-2, SC-8 |
| CTL-17 | Establish approved retention periods, systems of record, legal-hold procedures, secure deletion, media sanitization, and disposal evidence. | R-05, R-06, R-10, R-11 | Preventive / Corrective | Compliance Manager; Data Owners | Annual review; automated enforcement where supported | Retention schedule, system settings, deletion logs, legal holds, destruction records | P3 | GV.OC, PR.DS | AU-11, MP-6, SI-12 |
| CTL-18 | Define recovery objectives, maintain protected backups, test restoration, document manual workarounds, and exercise continuity plans for critical services. | R-07, R-08, R-12 | Recovery / Corrective | IT Director; Operations Director | Backups per schedule; restoration tests at least annually; exercises annually | BIA, RTO/RPO approvals, backup logs, restoration results, exercise reports, corrective actions | P1 | ID.BE, PR.DS, RC.RP | CP-2, CP-4, CP-9, CP-10 |
| CTL-19 | Establish incident reporting, triage, containment, investigation, communication, recovery, evidence preservation, and after-action procedures. | R-01, R-04, R-05, R-07, R-08, R-09, R-11, R-12 | Detective / Corrective / Recovery | IT Director; Incident Response Lead | Continuous readiness; annual exercises; after each incident | Incident plan, contact list, tickets, evidence logs, communications, exercise and after-action reports | P1 | RS.MA, RS.AN, RS.CO, RC.RP | IR-4, IR-6, IR-8 |
| CTL-20 | Integrate badge and visitor access with workforce lifecycle processes; restrict sensitive areas and review physical-access activity and exceptions. | R-02, R-13 | Preventive / Detective | Facilities Manager; HR Manager | Per event; quarterly review | Badge inventory, access logs, visitor records, termination samples, exceptions, walkthrough results | P2 | PR.AA, DE.CM | PE-2, PE-3, PE-6 |
| CTL-21 | Deliver role-specific awareness and training covering phishing, reporting, credentials, mobile devices, PHI/ePHI, data handling, vendors, and safe driver workflows. | R-01, R-04, R-05, R-06, R-10, R-14 | Preventive / Deterrent | GRC Analyst; HR Manager; Department Managers | At hire; annually; targeted refreshers | Training content, attendance, acknowledgments, simulations, knowledge checks, corrective training | P2 | PR.AT | AT-2, AT-3 |
| CTL-22 | Validate controls with frontline workers and require application interaction only at safe workflow points such as dispatch, pickup, parked status updates, and delivery confirmation. | R-04, R-14 | Preventive / Compensating | Dispatch Manager; Safety Manager; Application Owner | During design; after material changes; quarterly feedback | Workflow observations, usability tests, driver feedback, exception trends, support tickets | P1 | GV.RR, PR.AT, ID.IM | PL-4, AT-3, CA-7 |
| CTL-23 | Maintain a documented exception and risk-acceptance process with rationale, approver, compensating controls, expiration date, monitoring, and review requirements. | All risks | COO; Risk Owners; GRC Analyst | Per exception; quarterly review | Exception register, approvals, expiration reports, compensating-control evidence | P2 | GV.RM, GV.RR | CA-5, PM-4, RA-7 |
| CTL-24 | Define KPIs, KRIs, control tests, evidence requirements, issue tracking, and management reporting to confirm controls operate and reduce risk. | All risks | GRC Analyst; Control Owners | Monthly or quarterly based on metric | Dashboards, test workpapers, evidence repository, issue log, management reports | P3 | GV.OV, ID.IM | CA-2, CA-5, CA-7 |

## Risk-to-Control Traceability

| Risk ID | Primary Controls |
|---|---|
| R-01 | CTL-01, CTL-02, CTL-05, CTL-06, CTL-09, CTL-14, CTL-19, CTL-21 |
| R-02 | CTL-03, CTL-05, CTL-06, CTL-14, CTL-20 |
| R-03 | CTL-04, CTL-05, CTL-06, CTL-14, CTL-16 |
| R-04 | CTL-02, CTL-05, CTL-06, CTL-07, CTL-08, CTL-14, CTL-19, CTL-21, CTL-22 |
| R-05 | CTL-01, CTL-04, CTL-05, CTL-08, CTL-09, CTL-10, CTL-14, CTL-19, CTL-21 |
| R-06 | CTL-02, CTL-08, CTL-09, CTL-10, CTL-17, CTL-21 |
| R-07 | CTL-05, CTL-11, CTL-12, CTL-13, CTL-14, CTL-18, CTL-19 |
| R-08 | CTL-06, CTL-11, CTL-12, CTL-15, CTL-18, CTL-19 |
| R-09 | CTL-02, CTL-05, CTL-06, CTL-11, CTL-13, CTL-14, CTL-19 |
| R-10 | CTL-08, CTL-09, CTL-10, CTL-17, CTL-21 |
| R-11 | CTL-01, CTL-03, CTL-04, CTL-05, CTL-14, CTL-15, CTL-16, CTL-17, CTL-19 |
| R-12 | CTL-11, CTL-12, CTL-13, CTL-15, CTL-18, CTL-19 |
| R-13 | CTL-03, CTL-20 |
| R-14 | CTL-07, CTL-10, CTL-21, CTL-22 |

## Control Design and Validation Rules

1. A documented policy does not by itself prove that a control operates effectively.
2. Proposed controls must not be reported as current controls until implementation and operating evidence exist.
3. Control owners must be distinct from independent reviewers when feasible.
4. Exceptions must be approved, time-limited, monitored, and supported by compensating safeguards.
5. Controls affecting drivers, couriers, warehouse personnel, and dispatchers must be validated within the actual workflow.
6. PLG should prioritize shared controls that reduce several risks without creating a single point of operational failure.
7. Framework mappings must be reviewed whenever control scope or design materially changes.

## Expected Control States

| State | Definition |
|---|---|
| Proposed | Control has been recommended but not approved or implemented |
| Planned | Control has an approved owner, scope, resources, and target date |
| Implemented | Control is configured or operating, but sufficient effectiveness evidence has not yet been collected |
| Effective | Design and operating evidence demonstrate that the control consistently achieves its objective |
| Needs Improvement | Control exists but has design, coverage, consistency, evidence, or sustainability gaps |
| Not Effective | Control does not adequately address the stated objective or risk |

All controls in this portfolio matrix begin in the **Proposed** state unless later evidence explicitly supports another designation.

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. Framework mappings are illustrative and do not establish certification, regulatory compliance, or implementation by a real organization.
