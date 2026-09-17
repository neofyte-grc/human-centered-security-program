# Incident Response Scenarios and Playbooks

## Purpose

This document defines practical incident-response scenarios for Peachtree Logistics Group (PLG). The scenarios help PLG recognize, contain, investigate, recover from, and learn from security incidents without unnecessarily interrupting warehouse, dispatch, last-mile delivery, medical-courier, freight-brokerage, or billing operations.

The playbooks supplement—not replace—a formal incident response policy. Each response must be adjusted to the facts of the incident and applicable legal, contractual, insurance, privacy, and regulatory obligations.

This document supports:

- `docs/06-risk-register.md`
- `docs/07-security-control-matrix.md`
- `docs/08-role-based-access-control-model.md`
- `docs/09-iam-and-security-procedures.md`
- `docs/10-security-awareness-plan.md`

## Objectives

PLG's incident-response process will:

1. Protect people and maintain safe logistics operations.
2. Contain threats quickly while preserving evidence.
3. Protect customer, employee, payment, delivery, and medical-delivery information.
4. Establish clear decision authority and escalation paths.
5. Maintain essential operations through approved workarounds.
6. Meet applicable notification and reporting obligations.
7. Restore systems and access safely.
8. Use lessons learned to reduce future risk.

## Response Principles

- **Life and safety first:** Do not require drivers to troubleshoot or report while actively driving.
- **Report early:** Personnel should report suspected incidents even when details are incomplete.
- **Preserve evidence:** Do not delete messages, wipe devices, alter logs, or investigate independently unless directed.
- **Use least privilege:** Restrict compromised or unnecessary access without disabling more operations than required.
- **Communicate carefully:** Share incident information only with authorized responders and affected decision-makers.
- **Maintain service:** Use documented manual processes or alternative systems when they can operate safely and securely.
- **Avoid blame:** Focus first on containment, recovery, and facts. Address individual accountability separately and fairly.
- **Document decisions:** Record what happened, who authorized actions, and why decisions were made.

## Incident Response Lifecycle

| Phase | Primary Activities | Expected Output |
|---|---|---|
| Preparation | Assign roles, maintain contacts, configure logging, train personnel, test backups, and prepare workarounds | Current plans, tools, contacts, and trained responders |
| Detection and Analysis | Receive reports, validate indicators, determine affected assets and data, assign severity, and preserve evidence | Incident record, scope, severity, and response assignment |
| Containment | Isolate accounts, devices, applications, connections, or workflows while protecting essential services | Threat spread limited and business impact controlled |
| Eradication | Remove malicious access, persistence, unsafe configurations, and compromised credentials | Identified cause and threat removed |
| Recovery | Restore systems, validate security, monitor closely, and return operations to normal | Authorized, tested restoration of service |
| Post-Incident Review | Document root cause, impact, timeline, response effectiveness, and corrective actions | After-action report and tracked improvements |

## Incident Severity Levels

| Severity | Description | Examples | Initial Escalation Target |
|---|---|---|---|
| SEV-1 Critical | Confirmed or highly probable incident causing major operational disruption, widespread compromise, significant Restricted-data exposure, or immediate safety risk | Ransomware across operations; widespread account takeover; confirmed large PHI/ePHI or payment-data exposure | Immediately upon confirmation or credible indication |
| SEV-2 High | Confirmed incident affecting an important system, privileged account, sensitive information, or multiple users, but with limited current spread | Compromised administrator account; material vendor incident; lost unlocked device with Restricted data | Within 30 minutes |
| SEV-3 Moderate | Contained or suspected event with limited impact and no evidence of broad compromise | Single-user phishing compromise; malware isolated to one endpoint; misdirected confidential email | Within 4 business hours |
| SEV-4 Low | Suspicious event, policy violation, or attempted attack with no confirmed compromise | Blocked phishing attempt; unsuccessful login activity; minor procedural error | By the end of the business day |

Severity may increase or decrease as evidence develops. When uncertain, responders should begin at the higher reasonable level.

## Core Incident Response Team

| Role | Primary Responsibility |
|---|---|
| Incident Commander | Coordinates the response, assigns actions, approves operational priorities, and maintains the incident timeline |
| IT / Security Lead | Leads technical investigation, containment, eradication, recovery, and evidence preservation |
| Identity and Access Administrator | Revokes sessions, resets credentials, restricts accounts, reviews access, and preserves identity logs |
| GRC / Compliance Lead | Documents decisions, maps obligations, coordinates risk assessment, and tracks corrective actions |
| Operations Lead | Assesses warehouse, dispatch, delivery, and customer-service impact; activates workarounds |
| Medical Courier Program Manager | Advises on medical-delivery workflows, chain of custody, and potential PHI/ePHI impact |
| HR Lead | Coordinates workforce matters, internal communications, and personnel-related investigations |
| Legal / Privacy Counsel | Determines legal privilege, notification requirements, contractual obligations, and regulator or law-enforcement coordination |
| Communications Lead | Coordinates approved employee, client, public, and media communications |
| Vendor Management Lead | Coordinates affected vendors, contracts, escalation contacts, and evidence requests |
| Executive Sponsor | Approves major business, financial, risk-acceptance, and crisis-communication decisions |

One person may perform multiple roles because PLG has limited dedicated security personnel. Role assignments and backups must be documented in advance.

## General Response Checklist

### Reporter Actions

1. Move to a safe location before reporting if driving or operating equipment.
2. Stop the suspicious activity when safe, but do not destroy evidence.
3. Contact the approved PLG incident-reporting channel.
4. Provide the time, system or device, observed behavior, actions already taken, and current location of the affected asset.
5. Do not discuss the incident externally or post it on social media.
6. Remain available for follow-up instructions.

### Initial Responder Actions

1. Open an incident record and record the detection time.
2. Confirm reporter contact information and immediate safety concerns.
3. Assign an initial severity and Incident Commander.
4. Preserve relevant logs, messages, screenshots, device details, and access records.
5. Identify affected identities, assets, systems, data, locations, vendors, and business services.
6. Select containment actions proportionate to the risk.
7. Notify required internal stakeholders.
8. Determine whether legal, privacy, insurance, client, vendor, law-enforcement, or regulatory consultation is required.
9. Maintain a decision and action log throughout the response.

## Scenario 1: Microsoft 365 Account Compromise

### Trigger

An employee reports unexpected MFA prompts, unusual sent messages, missing email, an unfamiliar login, or a suspicious inbox rule. Monitoring may also identify impossible travel, risky sign-in activity, mass downloads, or unusual external sharing.

### Potential Impact

- Exposure of email, Teams messages, SharePoint files, customer information, contracts, or employee records
- Business email compromise or fraudulent payment requests
- Theft of active sessions or authentication tokens
- Malicious forwarding rules and external sharing
- Use of the account to compromise other employees, customers, or vendors

### Immediate Actions

1. Validate the report through a trusted contact method.
2. Disable or restrict the affected account when justified.
3. Revoke active sessions, refresh tokens, app passwords, and suspicious OAuth grants.
4. Reset the password and require secure MFA re-registration when compromise is probable.
5. Preserve Microsoft 365, identity, email, audit, sharing, and endpoint logs.
6. Review sign-ins, inbox rules, sent items, deleted items, external forwarding, file access, and application consent.
7. Search for related phishing messages and affected recipients.
8. Block confirmed malicious indicators without deleting necessary evidence.

### Investigation Questions

- How did the attacker obtain access?
- Was MFA bypassed, approved, redirected, or socially engineered?
- Which messages, files, sites, applications, and data were accessed?
- Were payment, medical-delivery, customer, employee, or privileged records involved?
- Did the account send messages or create persistence?
- Were other accounts targeted or compromised?

### Recovery Criteria

- Malicious sessions, credentials, applications, forwarding rules, and persistence have been removed.
- The user has securely re-established authentication.
- Affected endpoints have been examined and cleared.
- Related accounts and recipients have been assessed.
- Enhanced monitoring is active for the defined observation period.
- Required communications and notifications have been evaluated.

### Risk Traceability

- Primary risks: R-01, R-04, R-10
- Primary controls: MFA, conditional access, logging, phishing awareness, session revocation, and access review

## Scenario 2: Lost or Stolen Driver Mobile Device

### Trigger

A PLG-employed driver or independent courier reports that a device used for delivery work is missing, stolen, replaced, or left in an uncontrolled location.

### Potential Impact

- Exposure of routes, addresses, recipient details, signatures, photos, delivery notes, location information, or medical-delivery flags
- Unauthorized access through an active session
- Exposure through lock-screen notifications, local files, screenshots, or application caches
- Continued access by a former or unauthorized courier

### Immediate Actions

1. Confirm that the driver or courier is safely parked before requesting interaction.
2. Record the device owner, phone number, platform, management status, last known location, and time last seen.
3. Revoke delivery-platform and other active sessions.
4. Disable the device or external identity as appropriate.
5. Initiate remote lock or wipe for managed devices according to policy and evidence needs.
6. Review recent application activity, route access, downloads, and authentication events.
7. Determine whether local data, notifications, PHI/ePHI, or proof-of-delivery information may have been exposed.
8. Reassign active deliveries through dispatch without exposing unnecessary recipient information.
9. Provide a replacement-device and identity-verification process.

### Investigation Questions

- Was the device PLG-managed, approved BYOD, or independently managed?
- Was encryption, screen lock, MFA, and current software enabled?
- Which assignments and data were accessible or stored locally?
- Was the application session still active?
- Was the device recovered, and can its integrity be trusted?
- Does the event affect a medical-delivery client or another contractual obligation?

### Recovery Criteria

- All relevant sessions and credentials have been revoked or re-established securely.
- The missing device can no longer access PLG information.
- Active deliveries have been reassigned or resumed safely.
- A replacement device meets security requirements before access is restored.
- Exposure and notification determinations are documented.

### Risk Traceability

- Primary risks: R-05, R-06, R-11
- Primary controls: Mobile-device management, application session controls, encryption, remote protection, assignment-limited access, and incident reporting

## Scenario 3: Medical-Delivery Information Exposure

### Trigger

Medical-delivery information is sent to the wrong recipient, displayed in an exposed notification, shared through an unapproved channel, accessed without authorization, or found on a lost device. The information may include PHI/ePHI depending on its content and context.

### Potential Impact

- Privacy harm to an individual
- Client, contractual, or regulatory reporting obligations
- Loss of healthcare-client trust
- Exposure of delivery addresses, medical-service relationships, recipient identity, or chain-of-custody details

### Immediate Actions

1. Stop further disclosure without deleting evidence.
2. Recall, restrict, or remove access to the information where technically possible.
3. Preserve the original message, file, audit record, and recipient details.
4. Notify the Incident Commander, GRC / Compliance Lead, and Medical Courier Program Manager.
5. Consult qualified legal or privacy counsel to determine whether the information constitutes PHI/ePHI and whether HIPAA or another obligation applies.
6. Identify exactly what information was exposed, to whom, for how long, and whether it was viewed, downloaded, or redistributed.
7. Contact an unintended recipient only through an approved, counsel-reviewed process.
8. Protect ongoing deliveries and chain-of-custody requirements.

### Investigation Questions

- What specific information was involved?
- Was the information encrypted or otherwise protected?
- Who received or accessed it, and were they authorized?
- Can PLG confirm deletion, return, or access revocation?
- Which client contract, business associate arrangement, privacy rule, or state law may apply?
- Did a workflow or system design encourage unnecessary disclosure?

### Recovery Criteria

- Access has been removed or contained where possible.
- The scope, recipients, data elements, and duration are documented.
- Legal, contractual, client, and regulatory notification decisions are documented.
- The affected workflow has been corrected or temporarily controlled.
- Follow-up monitoring and corrective training are assigned.

### Risk Traceability

- Primary risks: R-06, R-11, R-13
- Primary controls: Minimum-necessary access, approved channels, recipient verification, encryption, retention controls, and role-based training

## Scenario 4: Payment Fraud or Business Email Compromise

### Trigger

Finance receives an urgent request to change bank details, redirect a payment, issue a refund, alter payroll, or pay an unfamiliar invoice. The request may appear to come from an executive, customer, employee, or vendor.

### Potential Impact

- Fraudulent transfer or financial loss
- Exposure of payment or account information
- Compromised executive, finance, vendor, or customer account
- Manipulated invoices or payment instructions

### Immediate Actions

1. Pause the transaction or change request.
2. Verify the request through a known contact using a separate trusted channel.
3. Notify Finance leadership and the Incident Commander.
4. Preserve the message, attachment, headers, call details, payment records, and approval history.
5. Restrict affected accounts and revoke sessions when compromise is suspected.
6. Contact the financial institution immediately if funds were transferred.
7. Review related mailboxes, transactions, vendor records, and approval activity.
8. Determine whether clients, vendors, insurers, law enforcement, or other parties must be contacted.

### Investigation Questions

- Was a PLG, vendor, executive, or customer account compromised?
- Which verification and approval controls were completed or bypassed?
- Were bank details or vendor-master records changed?
- Were other fraudulent requests sent?
- Can funds be recalled, frozen, or recovered?

### Recovery Criteria

- Fraudulent instructions and compromised access have been removed.
- Financial accounts and affected identities are secured.
- All related transactions have been reviewed.
- Recovery efforts and external contacts are documented.
- Approval and callback controls are tested before normal processing resumes.

### Risk Traceability

- Primary risks: R-01, R-04, R-10, R-14
- Primary controls: MFA, segregation of duties, independent verification, payment-change procedures, logging, and fraud awareness

## Scenario 5: Warehouse Management System Malware or Ransomware

### Trigger

Warehouse personnel report inaccessible files, ransom messages, unusual system behavior, widespread slowness, disabled security tools, or inability to use the on-premises Warehouse Management System (WMS).

### Potential Impact

- Warehouse, inventory, fulfillment, and staging disruption
- Lateral movement into other PLG systems
- Loss or encryption of inventory and shipment records
- Safety risks caused by inaccurate or unavailable operational information
- Extended business interruption

### Immediate Actions

1. Prioritize worker and warehouse safety.
2. Notify the Incident Commander, IT Lead, and Warehouse Operations Manager.
3. Isolate affected endpoints, servers, or network segments using approved methods.
4. Do not power off systems unless directed by the technical response lead or required for safety.
5. Preserve alerts, logs, ransom notes, volatile evidence where feasible, and backup status.
6. Disable compromised accounts and block confirmed malicious access paths.
7. Activate approved manual inventory, staging, and fulfillment procedures.
8. Protect backups from alteration and validate that clean recovery points exist.
9. Coordinate with cyber-insurance, legal counsel, vendors, or forensic specialists when required.

### Investigation Questions

- What was the initial access vector?
- Which endpoints, servers, accounts, shares, and backups are affected?
- Did the threat move into cloud services or other network zones?
- Was data exfiltrated before encryption?
- Which warehouse functions can continue safely through manual processes?
- Are recovery media and configurations known to be clean?

### Recovery Criteria

- The initial access method and persistence have been addressed.
- Restoration uses validated clean backups and secured credentials.
- Rebuilt systems are patched, hardened, segmented, and tested.
- Inventory and shipment records are reconciled before full operations resume.
- Enhanced monitoring shows no continuing malicious activity.
- Operations leadership approves return to normal processing.

### Risk Traceability

- Primary risks: R-02, R-03, R-09, R-12
- Primary controls: Patching, segmentation, endpoint protection, protected backups, logging, vulnerability management, and continuity procedures

## Scenario 6: Logistics Vendor or SaaS Platform Incident

### Trigger

A logistics technology vendor reports a breach or outage, PLG detects suspicious vendor-originated activity, or a critical cloud platform becomes unavailable.

### Potential Impact

- Exposure of order, routing, customer, account, or delivery information
- Loss of dispatch, brokerage, tracking, or proof-of-delivery capabilities
- Unauthorized vendor support access
- Dependency on incomplete or delayed vendor information

### Immediate Actions

1. Open a PLG incident record even when the vendor controls the technical investigation.
2. Contact the vendor through the approved escalation channel.
3. Request the incident time, affected services, PLG data involved, indicators of compromise, containment status, and expected updates.
4. Restrict vendor integrations, support accounts, tokens, or data flows when risk justifies the operational impact.
5. Preserve PLG-side logs and evidence.
6. Activate approved operational workarounds for affected logistics functions.
7. Identify affected customers, shipments, users, and information.
8. Review contractual notification, service-level, cyber-insurance, privacy, and evidence-preservation requirements.

### Investigation Questions

- Which PLG tenants, accounts, integrations, data, and time periods are affected?
- Did the vendor access or export PLG information?
- Are PLG credentials, tokens, or API keys compromised?
- Can PLG independently confirm the vendor's scope and containment?
- What manual or alternative service can maintain essential operations?
- Does the incident change the vendor's residual risk or continued suitability?

### Recovery Criteria

- The vendor provides sufficient evidence that the service is safe to reconnect or resume.
- PLG rotates affected credentials, keys, and tokens.
- Data integrity and synchronization are validated.
- Backlogged transactions and deliveries are reconciled.
- Contractual, client, privacy, and regulatory decisions are documented.
- Vendor corrective actions and PLG follow-up reviews are tracked.

### Risk Traceability

- Primary risks: R-07, R-08, R-12, R-13
- Primary controls: Vendor due diligence, contractual requirements, restricted support access, integration security, monitoring, continuity planning, and exit procedures

## Scenario 7: Orphaned or Excessive Access

### Trigger

PLG discovers that a former employee, transferred worker, vendor, courier, or service account retains access that is no longer required. An access review may also identify excessive permissions or conflicting roles.

### Potential Impact

- Unauthorized access to PLG systems and data
- Fraud, data theft, or operational manipulation
- Inability to attribute activity accurately
- Violation of least-privilege or segregation-of-duties requirements

### Immediate Actions

1. Validate the person's status and current business need through HR, the manager, or Vendor Management.
2. Suspend unnecessary or unauthorized access.
3. Revoke sessions, credentials, tokens, badges, VPN access, and application permissions as applicable.
4. Preserve identity, access, application, and physical-access logs.
5. Review activity from the last known authorized date through containment.
6. Identify other accounts created, approved, or influenced by the affected identity.
7. Determine whether data was accessed, changed, downloaded, or shared.

### Investigation Questions

- Why did the joiner-mover-leaver process fail?
- Which systems and locations remained accessible?
- Was the account used after authorization ended?
- Were manager, HR, IT, or vendor notifications delayed?
- Do similar users or accounts have the same control gap?

### Recovery Criteria

- Unauthorized access is removed across all connected systems and facilities.
- Activity is reviewed and impact is documented.
- Similar identities and roles are checked.
- Provisioning, transfer, recertification, or offboarding controls are corrected.
- System and Data Owners confirm appropriate restored access, if any.

### Risk Traceability

- Primary risks: R-02, R-03, R-07, R-08
- Primary controls: Automated lifecycle workflows, RBAC, timely deprovisioning, access recertification, named accounts, and vendor offboarding

## Business Continuity Workarounds

| Affected Capability | Temporary Workaround | Required Safeguards |
|---|---|---|
| Customer order intake | Approved call script and controlled intake form | Verify requester; collect minimum necessary data; enter into system of record when restored |
| Dispatch platform | Preapproved manual dispatch sheet or alternate communication method | Limit recipient data; authenticate driver or courier; track assignment and return records |
| Driver application | Dispatcher-assisted delivery process | Do not use personal messaging for PHI/ePHI or payment data; document confirmation securely |
| Warehouse Management System | Controlled paper or offline inventory process | Sequential records; restricted storage; dual review; reconciliation after restoration |
| Microsoft 365 | Approved backup communication method | Restrict sensitive data; verify identities; preserve business records |
| Billing system | Hold noncritical changes and use controlled transaction log | Dual approval; callback verification; reconcile before posting |

Workarounds must be approved by Operations and the Incident Commander. They must not continue longer than necessary and must be reconciled after normal systems return.

## Evidence Preservation

Responders should preserve, as applicable:

- Identity-provider and MFA logs
- Microsoft 365 audit, email, sharing, and application-consent records
- Endpoint, mobile-device, firewall, VPN, and network logs
- SaaS application and administrator logs
- WMS server, database, and backup records
- Driver and courier application access records
- Payment approvals and transaction records
- Physical-access and visitor records
- Relevant messages, files, screenshots, photographs, and call notes
- Vendor notices and support communications
- A chronological response and decision log

Evidence must be access-restricted, integrity-protected, retained according to applicable requirements, and transferred using documented chain-of-custody procedures when needed.

## Communication Rules

- Only authorized personnel may communicate externally about an incident.
- Employees should not speculate, admit liability, or provide unapproved details.
- Client communications must be accurate, timely, and coordinated with Legal / Privacy and Communications.
- Media inquiries must be directed to the designated spokesperson.
- Incident updates should distinguish confirmed facts from assumptions.
- Sensitive incident details must be shared through an approved secure channel.
- Operational teams should receive enough information to work safely without unnecessary exposure of investigative details.

## Notification Decision Checklist

Legal or qualified privacy counsel should help determine whether notification is required based on:

- The people, clients, jurisdictions, and contracts involved
- The type, sensitivity, and amount of information affected
- Whether information was accessed, acquired, altered, or unavailable
- Whether the information was encrypted or otherwise protected
- The identity and obligations of PLG, its clients, and its vendors
- Applicable privacy, breach-notification, payment-card, healthcare, insurance, and law-enforcement requirements
- Contractual notification deadlines

This portfolio scenario does not make a legal determination that HIPAA, PCI DSS, or a specific breach-notification law applies.

## Tabletop Exercise Format

Each tabletop exercise should include:

1. **Scenario briefing:** A realistic event with limited initial information.
2. **Injects:** New facts introduced over time, such as client calls, new affected accounts, system outages, or media inquiries.
3. **Decision discussion:** Participants identify authority, priorities, containment options, and tradeoffs.
4. **Operational validation:** Teams confirm whether contacts, tools, logs, backups, and workarounds are actually available.
5. **After-action review:** Facilitators document strengths, gaps, owners, and deadlines.

Exercises should evaluate decision-making and coordination rather than surprise or embarrass participants.

## Exercise Schedule

| Exercise | Participants | Frequency |
|---|---|---|
| Microsoft 365 account compromise | IT, IAM, GRC, HR, Communications, executive representative | Semiannual |
| Lost driver device and active medical delivery | Dispatch, IT, Medical Courier Manager, GRC, driver representative | Semiannual |
| Payment fraud | Finance, executive leadership, IT, GRC, Vendor Management | Annual |
| WMS ransomware and warehouse continuity | IT, Warehouse Operations, GRC, executive leadership, vendor support | Annual |
| SaaS vendor breach and outage | IT, Operations, Vendor Management, GRC, Legal / Privacy | Annual |
| Terminated-user access failure | HR, manager, IT / IAM, Facilities, GRC | Annual |

## Response Metrics

### Key Performance Indicators

| KPI | Initial Target |
|---|---:|
| High-severity incidents assigned an Incident Commander within target | At least 95% |
| Relevant compromised sessions revoked within the defined response target | At least 95% |
| Incident records containing a complete action and decision timeline | 100% |
| Corrective actions assigned an owner and due date | 100% |
| Annual tabletop exercises completed | 100% |
| Critical recovery procedures tested successfully | At least annually |

### Key Risk Indicators

| KRI | Escalation Indicator |
|---|---|
| Delayed reporting of suspected incidents | Increasing trend or any material delay affecting containment |
| Incidents without sufficient logs | Any material investigation blocked by missing evidence |
| Repeat incidents with the same root cause | Any recurrence after corrective-action closure |
| Unsupported operational workaround | Any use involving Restricted data or material business decisions |
| Overdue high-priority corrective action | Any item beyond the approved deadline |
| Unreconciled records after system recovery | Any material inventory, delivery, or financial discrepancy |
| Vendor failing to meet incident-notification terms | Any material contractual failure |

Targets should be refined after PLG establishes a response baseline.

## Post-Incident Review

For SEV-1 and SEV-2 incidents—and selected lower-severity events—PLG should complete an after-action review that documents:

- Executive summary
- Incident timeline
- Affected identities, assets, systems, data, clients, and services
- Root cause and contributing conditions
- Detection source and missed warning signs
- Containment, eradication, and recovery actions
- Operational, financial, legal, privacy, safety, and reputational impact
- Communications and notification decisions
- What worked well
- What created delay, confusion, or unnecessary friction
- Corrective actions, owners, priorities, and due dates
- Residual risk and required leadership decisions

The review should examine technology, process, staffing, training, vendor, and control-design factors—not only individual behavior.

## Governance and Maintenance

The GRC Analyst should coordinate review of this document at least annually and after:

- A significant incident or near miss
- A material change to PLG systems, services, vendors, or workflows
- A major organizational or response-team change
- A tabletop exercise identifying a material gap
- A change in applicable contractual, privacy, or security requirements

Contact lists, escalation methods, insurance details, and vendor emergency contacts should be maintained separately in a restricted operational appendix rather than published in a public portfolio repository.

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. These scenarios demonstrate risk-based incident-response planning and do not represent legal advice, a complete regulatory determination, or the response plan of a real organization.
