# IAM and Security Procedures

## Purpose

These procedures define how Peachtree Logistics Group requests, approves, provisions, modifies, reviews, suspends, and removes logical and physical access. They also establish repeatable responses for compromised accounts, lost devices, temporary access, vendor access, emergency access, and security exceptions.

The procedures operationalize:

- `docs/06-risk-register.md`
- `docs/07-security-control-matrix.md`
- `docs/08-role-based-access-control-model.md`

These procedures represent a proposed target state and do not claim current implementation.

## Scope

These procedures apply to:

- Employees, managers, contractors, independent couriers, vendors, administrators, and service accounts
- Microsoft 365
- Identity and Access Management Service
- Logistics and Freight Platform
- Warehouse Management System
- Dispatch and Delivery Platform
- Billing and Accounting System
- Records Archive
- PLG-issued laptops and mobile devices
- Approved personal devices accessing PLG information
- Badge, visitor, office, warehouse, records, network, and restricted-area access

## Roles and Responsibilities

| Role | Responsibilities |
|---|---|
| Requesting Manager / Sponsor | Identifies business need, requests the approved role, confirms scope, and reviews continued need |
| Human Resources | Provides authoritative employee start, transfer, leave, and separation information |
| Vendor Management / Procurement | Provides authoritative vendor, contractor, contract, and termination information |
| Dispatch Manager | Sponsors and reviews driver and independent-courier access |
| System or Data Owner | Approves access according to business need, data classification, and segregation-of-duties requirements |
| IT / IAM Administrator | Provisions, changes, suspends, and removes technical access after approval |
| Facilities Manager | Provisions, reviews, and removes physical access |
| Security Operations / Incident Lead | Investigates suspicious access and coordinates containment |
| GRC Analyst | Reviews evidence, monitors exceptions, tests procedures, and reports deficiencies |
| User | Protects credentials, follows policy, reports suspected compromise, and uses access only for authorized purposes |

## Service-Level Requirements

| Event | Required Completion |
|---|---|
| Standard new-user request | Submitted at least three business days before the approved start date |
| Standard role change | Completed by the effective date; obsolete access removed within one business day |
| Standard voluntary separation | Access disabled no later than the effective separation time |
| Involuntary or high-risk separation | Access disabled at or immediately before notification, as coordinated with HR and leadership |
| Independent-courier assignment | Access active only for the approved assignment or engagement period |
| Vendor support access | Enabled only for the approved support window and disabled when work concludes |
| Suspected compromised account | Immediate suspension or containment after validation of the report |
| Lost or stolen device | Reported immediately; session and device containment initiated as soon as practical |
| Emergency-access review | Completed by the next business day |
| Critical access-review finding | Remediated or formally escalated within five business days |
| Standard access-review finding | Remediated within 30 calendar days unless an approved exception exists |

## General Requirements

1. Every user must have a unique identity.
2. Users may not approve or provision their own access.
3. Access must be based on an approved RBAC role and least privilege.
4. Confidential or Restricted access requires system or data-owner approval.
5. Privileged, financial, medical-delivery, vendor, and physical access may require additional approval.
6. Shared accounts are prohibited unless a documented technical exception is approved.
7. Temporary access must include a start date and expiration date.
8. Approvals, changes, exceptions, and removals must be retained as evidence.
9. Access must not be granted solely because a user previously held similar permissions.
10. Production access may not be used for training, convenience, or unsanctioned testing.

## Procedure 1: Request and Approve Access

### Trigger

A worker, manager, courier sponsor, vendor sponsor, or system owner identifies a legitimate need for new or changed access.

### Procedure

1. The Requesting Manager or Sponsor submits an access request.
2. The request identifies:
   - User name and unique workforce, courier, contractor, or vendor identifier
   - Employment or engagement type
   - Requested RBAC role
   - Systems and physical locations requested
   - Business justification
   - Department, facility, client, and assignment scope
   - Information classification involved
   - Requested start and expiration dates
3. The manager confirms that the selected role matches the user's duties.
4. The System or Data Owner reviews access involving Confidential or Restricted information.
5. Finance approves sensitive billing or payment permissions.
6. The Medical Courier Program Manager or designated privacy authority approves access to applicable PHI/ePHI workflows.
7. IT checks for incompatible roles, excessive access, existing accounts, and segregation-of-duties conflicts.
8. The authorized approver approves, rejects, or returns the request for correction.
9. IT or Facilities provisions only the approved access.
10. A person other than the provisioner verifies high-risk or privileged access.
11. The user and manager are notified when access is ready.

### Evidence

- Access request
- Business justification
- Required approvals
- Segregation-of-duties review
- Provisioning record
- Verification record
- Start and expiration dates

## Procedure 2: Provision a New User

### Trigger

HR, Vendor Management, Dispatch, or another authorized sponsor confirms an approved start or engagement.

### Procedure

1. Confirm the person exists in the appropriate authoritative source.
2. Confirm the approved role, start date, manager, location, and employment or engagement type.
3. Create a unique identity using the approved naming convention.
4. Assign only the approved RBAC role and group memberships.
5. Require MFA and approved authentication methods.
6. Issue a standard account separately from any privileged account.
7. Configure device, application, and physical access according to role.
8. Set an expiration date for temporary, courier, contractor, and vendor access.
9. Require completion of applicable training and policy acknowledgment.
10. Test access without exposing unnecessary production information.
11. Record the provisioner, completion time, and verification.
12. Provide the user with secure activation instructions.

### Evidence

- Authoritative-source record
- Approved role and access request
- Identity and group record
- MFA enrollment
- Device and badge assignment
- Training and acknowledgment
- Completion and verification timestamps

## Procedure 3: Modify Access After a Role or Assignment Change

### Trigger

A worker changes department, job, manager, facility, client, route, assignment, contract, or responsibility.

### Procedure

1. HR, the manager, Dispatch, or Vendor Management submits the change.
2. The new manager identifies the appropriate target role.
3. System and Data Owners approve newly required sensitive access.
4. IT compares existing access with the target role.
5. Remove obsolete access before or at the same time new access is added.
6. Identify segregation-of-duties conflicts.
7. If temporary overlap is required:
   - Document the reason
   - Obtain approval
   - Apply additional monitoring
   - Set an expiration date
8. Update logical access, device profiles, distribution groups, records access, and physical access.
9. Verify that the old access has been removed.
10. Notify the manager and user.

### Evidence

- Change request
- Old and new role comparison
- Approvals
- Access-removal record
- New-access record
- Temporary-overlap exception where applicable

## Procedure 4: Disable Access at Separation

### Trigger

An employee, contractor, courier, or vendor relationship ends.

### Procedure

1. HR, Vendor Management, Dispatch, or the authorized sponsor communicates:
   - Identity
   - Separation type
   - Effective date and time
   - Risk level
   - Required coordination
2. For involuntary or high-risk separations, coordinate disablement at or immediately before notification.
3. Disable primary, privileged, mobile, SaaS, on-premises, VPN, vendor, and physical-access accounts.
4. Revoke active sessions, refresh tokens, application passwords, certificates, and recovery methods where supported.
5. Remove roles, groups, delegation, shared-mailbox access, forwarding, and application integrations assigned to the individual.
6. Recover PLG devices, badges, keys, tokens, records, and other assets.
7. Transfer ownership of files, mailboxes, records, workflows, and scheduled tasks.
8. Rotate shared secrets known to the departing person.
9. Preserve information subject to approved retention or legal-hold requirements.
10. Confirm removal across systems not integrated with IAM.
11. The manager verifies that access and assets have been addressed.
12. Record any failure, delay, or exception and escalate high-risk gaps immediately.

### Evidence

- Separation notice
- Disablement and revocation timestamps
- System checklist
- Asset-return record
- Ownership-transfer record
- Badge and physical-access removal
- Manager verification
- Exceptions and escalation records

## Procedure 5: Manage Independent-Courier Access

### Trigger

An independent courier is approved for an assignment or engagement.

### Procedure

1. Dispatch verifies the courier's approved engagement and contractual requirements.
2. Create or activate a unique external identity.
3. Do not create an employee account or provide internal directory access.
4. Assign only the active delivery, route, recipient, timing, and handling information required.
5. Limit historical search, bulk export, unrelated customer access, download, and local storage.
6. Apply appropriate strong authentication and device/application safeguards.
7. Set automatic assignment or engagement expiration.
8. Log authentication, assignment access, status changes, proof of delivery, and administrative changes.
9. Require immediate reporting of lost devices, suspected compromise, misdirected information, or unsafe application behavior.
10. Disable access when the assignment or engagement ends.
11. Reconcile courier identities against active assignments at least monthly.

### Evidence

- Approved courier and contract record
- Unique external identity
- Assignment-to-access mapping
- Authentication and access logs
- Expiration and disablement record
- Monthly reconciliation

## Procedure 6: Grant and Monitor Privileged Access

### Trigger

An administrator or approved support person requires elevated access.

### Procedure

1. Require a separate privileged account.
2. Document the systems, functions, business justification, and duration.
3. Obtain System Owner and IT Director approval.
4. Require MFA and an approved secure administrative method.
5. Use time-limited elevation where supported.
6. Prohibit routine email, web browsing, and office work from the privileged account.
7. Log administrative authentication and actions.
8. Review privileged activity independently.
9. Remove temporary elevation after the task or approved window.
10. Review the full privileged-account population quarterly.

### Evidence

- Privileged-access request and approvals
- Administrator inventory
- MFA coverage
- Elevation records
- Activity logs
- Independent review
- Removal or expiration record

## Procedure 7: Manage Vendor Support Access

### Trigger

A third-party provider requires access for approved support, maintenance, or implementation.

### Procedure

1. Confirm the vendor contract, sponsor, support need, and security requirements.
2. Create a named vendor identity; shared vendor accounts require an approved exception.
3. Define the system, permissions, access method, support window, and expiration.
4. Obtain System Owner and IT approval.
5. Require MFA where supported.
6. Restrict access to approved systems and tasks.
7. Monitor or record the session where proportionate and feasible.
8. Prevent unnecessary access to customer, employee, financial, or medical-delivery information.
9. Disable access when the support window closes.
10. Review vendor activity and document unexpected actions.

### Evidence

- Contract and security terms
- Sponsor and approvals
- Named vendor identity
- Access window
- Session or activity logs
- Closure and disablement record

## Procedure 8: Review Access

### Trigger

A scheduled review begins or an event requires targeted recertification.

### Procedure

1. IT produces complete user, role, group, privileged, service, vendor, courier, and physical-access listings.
2. The reviewer receives understandable role and permission descriptions.
3. Managers verify workforce status and business need.
4. System and Data Owners verify role appropriateness and sensitive access.
5. Reviewers identify:
   - Terminated or inactive users
   - Dormant, duplicate, shared, and orphaned accounts
   - Excessive privileges
   - Segregation-of-duties conflicts
   - Expired temporary access
   - Unowned service accounts
   - Inappropriate courier or vendor access
6. Reviewers approve, remove, modify, or escalate each exception.
7. IT completes remediation within the required timeframe.
8. The reviewer verifies completion.
9. GRC tracks overdue reviews and unresolved findings.

### Frequency

- Privileged, emergency, critical-system, courier, vendor, and Restricted-data access: quarterly or more frequently where specified
- Standard lower-risk access: at least semiannually
- Targeted review: after incidents, reorganizations, system changes, or material control failures

### Evidence

- Review population
- Reviewer assignment
- Decisions and dates
- Remediation tickets
- Completion verification
- Exceptions
- Review metrics

## Procedure 9: Manage Service Accounts

### Trigger

A system integration, automated job, application, or approved technical process requires a non-human identity.

### Procedure

1. Document the business and technical purpose.
2. Assign a business owner and technical custodian.
3. Confirm that a service account is necessary.
4. Grant only required systems, functions, and data.
5. Prevent interactive login where feasible.
6. Protect credentials using an approved secret-management method.
7. Rotate credentials according to risk and after suspected exposure.
8. Log authentication and material activity.
9. Do not permit shared human use.
10. Review ownership, use, privilege, and activity quarterly.
11. Disable the account when the associated system or process is retired.

### Evidence

- Service-account inventory
- Owner and custodian
- Purpose and dependency
- Permission record
- Credential-management evidence
- Activity logs
- Quarterly review

## Procedure 10: Use Emergency or Break-Glass Access

### Trigger

Normal access would unreasonably delay response to a critical operational or security event.

### Procedure

1. Confirm that normal access cannot meet the urgent need.
2. Obtain designated approval when circumstances permit.
3. Use a unique emergency identity.
4. Record the requester, reason, affected system, start time, and intended action.
5. Limit access to the minimum required privilege and duration.
6. Monitor and log all use.
7. Remove elevation or secure the emergency account immediately after use.
8. Rotate affected credentials where required.
9. Review activity by the next business day.
10. Document lessons, unauthorized actions, and corrective measures.

### Evidence

- Emergency-access record
- Approval or documented emergency justification
- Activity logs
- End time and removal
- Credential rotation
- After-action review

## Procedure 11: Respond to a Suspected Compromised Account

### Trigger

PLG receives a suspicious-login alert, phishing report, impossible-travel alert, repeated authentication failure, user report, or other indication of account compromise.

### Procedure

1. Record the report and time received.
2. Validate the identity and affected account without requesting the user's password.
3. Disable or suspend the account when compromise is credible.
4. Revoke active sessions, tokens, application passwords, and suspicious recovery methods.
5. Reset credentials through an approved identity-verification process.
6. Review MFA registrations, forwarding rules, delegated access, group changes, privilege changes, and recent activity.
7. Determine what systems and information were accessed.
8. Preserve relevant logs and evidence.
9. Escalate potential customer, financial, PHI/ePHI, contractual, or legal impact.
10. Restore access only after containment requirements are satisfied.
11. Monitor the account after restoration.
12. Document the incident and corrective actions.

### Evidence

- Alert or report
- Containment timestamps
- Session and token revocation
- Authentication and activity logs
- Impact analysis
- Escalation record
- Restoration approval
- Incident record

## Procedure 12: Respond to a Lost, Stolen, or Replaced Device

### Trigger

A PLG-issued or approved personal device with PLG access is lost, stolen, replaced, or suspected compromised.

### Procedure

1. The user reports the event immediately to IT, Security, and the manager.
2. Record the device, user, time, location, applications, and information potentially involved.
3. Revoke PLG sessions and application access.
4. Lock, retire, or remotely wipe managed PLG information where supported and authorized.
5. Reset or revoke credentials, tokens, certificates, and recovery methods as necessary.
6. Review recent device and account activity.
7. Determine whether customer, recipient, payment, or medical-delivery information may have been exposed.
8. Escalate according to incident, privacy, contractual, and legal procedures.
9. Reissue access only after the replacement device meets security requirements.
10. Document containment and closure.

### Evidence

- Device incident report
- Session revocation
- MDM or application-protection action
- Account review
- Exposure analysis
- Replacement-device compliance
- Closure approval

## Procedure 13: Handle Access and Security Exceptions

### Trigger

A required control cannot be implemented as designed, or a business process requires temporary deviation.

### Procedure

1. The requester documents:
   - Requirement that cannot be met
   - Business justification
   - Affected user, role, system, data, and workflow
   - Related risks
   - Requested duration
2. The requester proposes compensating controls.
3. The Control Owner assesses feasibility and monitoring.
4. The Risk Owner reviews the remaining exposure.
5. The authorized approver accepts, modifies, or rejects the exception.
6. GRC records the exception, owner, approval, start date, expiration, and review frequency.
7. IT implements only the approved deviation.
8. The owner monitors the compensating controls.
9. The exception expires automatically unless formally renewed.
10. PLG removes the exception when the business or technical need ends.

### Evidence

- Exception request
- Risk analysis
- Compensating controls
- Approval
- Start and expiration dates
- Monitoring evidence
- Closure or renewal

## Procedure 14: Preserve Procedure Evidence

Access and security evidence must:

- Be attributable to the user, requester, approver, provisioner, reviewer, and system.
- Include relevant timestamps.
- Be protected from unauthorized alteration or deletion.
- Be retained according to approved business, contractual, legal, privacy, and security requirements.
- Avoid retaining sensitive information longer than necessary.
- Be accessible to authorized reviewers, investigators, auditors, and control owners.

## Escalation Requirements

Immediately escalate:

- Suspected compromise of privileged, executive, finance, IAM, or medical-delivery accounts
- Access retained after an involuntary or high-risk separation
- Unauthorized access to applicable PHI/ePHI or payment information
- Evidence of credential sharing or unapproved shared accounts
- Vendor activity outside the approved support window
- Unexplained privilege elevation or administrative changes
- Failure to disable access within required timeframes
- Lost devices containing or accessing Restricted information
- Access controls that encourage unsafe driver behavior
- Repeated or deliberate circumvention of controls

## Procedure Metrics

PLG should measure:

- Percentage of accounts covered by MFA
- Percentage of access requests with complete approval evidence
- Percentage of terminated-user accounts disabled on time
- Number of dormant, orphaned, shared, and duplicate accounts
- Percentage of quarterly reviews completed on time
- Average time to remove inappropriate access
- Number and age of access exceptions
- Percentage of courier accounts tied to active assignments
- Percentage of vendor accounts with an expiration date
- Percentage of service accounts with an assigned owner
- Time to contain suspected compromised accounts
- Time to revoke access after a lost-device report
- Number of reported workflow or safety conflicts caused by access controls

Detailed KPI and KRI definitions will be maintained in `docs/13-kpis-and-kris.md`.

## Risk and Control Traceability

These procedures primarily support:

- Risks R-01, R-02, R-03, R-04, R-05, R-06, R-08, R-09, R-11, R-13, and R-14
- Controls CTL-01 through CTL-10, CTL-14, CTL-16, CTL-19 through CTL-24

## Review and Maintenance

- IT owns the technical IAM procedures.
- HR owns authoritative employee lifecycle notifications.
- Vendor Management owns vendor and contractor lifecycle notifications.
- Dispatch owns independent-courier sponsorship and assignment status.
- Facilities owns physical-access procedures.
- GRC reviews procedure design, evidence quality, exceptions, and testing results.
- Procedures must be reviewed at least annually and after significant incidents, audit findings, system changes, organizational changes, or control failures.

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. These procedures demonstrate a proposed GRC and IAM operating model and are not implemented procedures from a real organization.
