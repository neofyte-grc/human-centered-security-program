# Role-Based Access Control Model

## Purpose

This role-based access control (RBAC) model defines how Peachtree Logistics Group grants, modifies, reviews, and removes access according to job responsibilities and business need. Its purpose is to reduce excessive privileges, inconsistent access, orphaned accounts, credential sharing, and inappropriate exposure of customer, employee, financial, shipment, and medical-delivery information.

This model supports the risks and controls documented in:

- `docs/06-risk-register.md`
- `docs/07-security-control-matrix.md`

The model is a proposed target state. It does not claim that the roles or permissions are currently implemented.

## RBAC Principles

1. **Least privilege:** Users receive only the access required to perform approved duties.
2. **Need to know:** Access to Confidential or Restricted information is limited by role, assignment, client, and legitimate business purpose.
3. **Role-based assignment:** Standard access is assigned through approved roles rather than one-off individual permissions whenever practical.
4. **Segregation of duties:** Incompatible activities are divided among different people or independently reviewed.
5. **Unique identity:** Each user receives an individual account. Shared credentials are prohibited unless a documented technical exception is approved.
6. **Identity separation:** Employee, administrator, service, vendor, and independent-courier identities remain distinguishable.
7. **Time-bound access:** Temporary, vendor, emergency, and assignment-specific access expires automatically or is promptly removed.
8. **Default deny:** Access not explicitly approved is denied.
9. **Lifecycle control:** Access is updated when a worker joins, changes roles, changes assignments, or leaves PLG.
10. **Evidence and accountability:** Requests, approvals, provisioning, reviews, exceptions, and removals are documented.
11. **Safe workflow design:** Authentication and authorization requirements must not encourage drivers to interact with devices while actively driving.

## Scope

This model applies to:

- Microsoft 365
- Identity and Access Management Service
- Logistics and Freight Platform
- Warehouse Management System
- Dispatch and Delivery Platform
- Billing and Accounting System
- Records Archive
- PLG-managed laptops and mobile devices
- Approved personal devices accessing PLG applications
- Physical access to offices, warehouses, records, network equipment, and secured shipment areas
- Employees, managers, administrators, contractors, independent couriers, vendors, and service accounts

## Permission-Level Legend

| Code | Permission Level | Definition |
|---|---|---|
| N | None | No access is permitted |
| R | Read | View approved information without creating, changing, approving, or deleting it |
| U | User | Create or update information required for normal assigned duties |
| A | Approver | Review and approve transactions, access, records, or workflow decisions within delegated authority |
| P | Privileged | Perform approved administrative, configuration, security, or system-management activities |
| T | Temporary / Assignment-Based | Access is limited to an approved purpose, assignment, vendor task, or time period |

Permission codes represent maximum standard access. Actual access may be narrower based on location, department, client, assignment, data classification, or system capability.

## Role Catalog

| Role ID | Role | Primary Responsibilities | Data Sensitivity | Standard Restrictions |
|---|---|---|---|---|
| RBAC-01 | Executive Leadership | Approve strategy, resources, risk responses, and major business decisions | Internal, Confidential, summarized Restricted information when required | No routine system administration or transaction processing |
| RBAC-02 | IT Administrator | Administer identity, endpoints, infrastructure, applications, security settings, logging, backup, and recovery | Internal, Confidential, Restricted technical information | Privileged actions require separate admin accounts, MFA, logging, and review |
| RBAC-03 | GRC Analyst | Assess risks and controls, review evidence, track issues, and report results | Internal, Confidential, limited Restricted evidence | Read-only access preferred; no routine production administration or transaction approval |
| RBAC-04 | Human Resources | Manage workforce records, onboarding, transfers, leave, and separation events | Confidential and Restricted personnel information | No operational logistics, dispatch, warehouse, or financial-administration privileges |
| RBAC-05 | Customer Service Representative | Receive customer requests, update approved customer information, and communicate order status | Internal and Confidential customer/order information | No bulk exports, financial administration, privileged access, or unnecessary medical details |
| RBAC-06 | Operations Coordinator | Review orders, validate service requirements, schedule work, and coordinate fulfillment | Internal and Confidential operational information; limited Restricted information | No IAM administration, payment approval, or unrestricted archive access |
| RBAC-07 | Warehouse Personnel | Receive, stage, fulfill, and update inventory and shipment status | Internal and limited Confidential shipment information | Access limited by facility and duties; no billing, IAM, or unnecessary recipient data |
| RBAC-08 | Warehouse Operations Manager | Approve warehouse activities, manage workforce access needs, and review fulfillment exceptions | Internal and Confidential operational information | No IAM provisioning or payment administration |
| RBAC-09 | Dispatcher | Assign drivers, manage routes, monitor delivery status, and resolve delivery exceptions | Confidential route, recipient, and delivery information; applicable limited Restricted data | No billing administration, broad archive access, or identity administration |
| RBAC-10 | PLG-Employed Driver | Receive assigned routes, update safe status points, and capture authorized proof of delivery | Assignment-specific Confidential information; minimum necessary Restricted data | No access to other drivers' assignments, bulk records, customer portfolios, or system administration |
| RBAC-11 | Independent Courier | Complete specifically assigned pickup and delivery work | Temporary, assignment-specific Confidential information; minimum necessary Restricted data | External identity; no employee account, directory access, bulk search, unrelated deliveries, or access after assignment/engagement |
| RBAC-12 | Medical Courier Program Manager | Oversee medical-delivery operations, workflow requirements, access approvals, exceptions, and applicable privacy safeguards | Confidential and applicable Restricted PHI/ePHI | No IAM provisioning or unrestricted technical administration |
| RBAC-13 | Billing Specialist | Create invoices, process approved billing records, and reconcile authorized transactions | Confidential financial/customer information; applicable Restricted payment data | Cannot approve own access, modify IAM, or independently change and approve sensitive payment instructions |
| RBAC-14 | Finance Manager | Approve financial workflows, review reconciliation, and authorize billing access | Confidential and applicable Restricted financial information | No routine IAM provisioning or system-security administration |
| RBAC-15 | Compliance / Records Manager | Manage retention, legal holds, records access, disposal requirements, and compliance evidence | Internal, Confidential, and applicable Restricted records | No routine operational transaction processing or technical administration |
| RBAC-16 | Vendor Management / Procurement | Perform vendor due diligence, manage contracts, track assurance evidence, and coordinate termination | Internal and Confidential vendor/contract information | No vendor technical access provisioning without system-owner and IT approval |
| RBAC-17 | Third-Party Support User | Perform approved support or maintenance activities | Minimum system information required for the approved task | Temporary access, named account, MFA, monitored session where feasible, no standing access unless justified |
| RBAC-18 | Physical Security / Facilities | Manage badges, visitors, facility access, and physical-access evidence | Internal and Confidential facility/access information | No business-system administration; cannot approve own physical-access request |
| RBAC-19 | Service Account | Execute an approved automated system function | Limited to required systems and data | Non-interactive where feasible; named owner; protected credential; no shared human use; periodic review |

## System-Access Matrix

| Role | Microsoft 365 | Logistics / Freight Platform | Warehouse Management System | Dispatch / Delivery Platform | Billing / Accounting | Records Archive | IAM | Physical Access |
|---|---|---|---|---|---|---|---|---|
| Executive Leadership | R | R | R | R | R | R | N | A based on business need |
| IT Administrator | P | P technical | P technical | P technical | P technical | P technical | P | U for technical areas |
| GRC Analyst | R | R evidence | R evidence | R evidence | R evidence | R evidence | R audit/evidence | R logs; escorted access as needed |
| Human Resources | U HR content | N | N | N | N | U personnel records | T lifecycle initiation; R status | A workforce badge lifecycle |
| Customer Service Representative | U | U limited | R limited | R status | R invoice status | N | N | U assigned office |
| Operations Coordinator | U | U | U limited | R/U coordination | R limited | R limited | N | U assigned operations areas |
| Warehouse Personnel | U limited | R assigned orders | U facility-limited | R limited | N | N | N | U assigned warehouse areas |
| Warehouse Operations Manager | U | U | A/U facility-limited | R/U | N | R operational | N | A assigned warehouse areas |
| Dispatcher | U | U | R shipment readiness | A/U dispatch functions | N | R limited | N | U dispatch and operations areas |
| PLG-Employed Driver | U basic collaboration only if required | N or R assigned summary | N | U assignment-limited | N | N | N | T pickup/staging areas as required |
| Independent Courier | N | N | N | T assignment-limited | N | N | N internal; external authentication only | T escorted or designated pickup areas |
| Medical Courier Program Manager | U | U medical program | R limited | A/U medical workflow | R limited | R medical records | N | A applicable secured areas |
| Billing Specialist | U | R completed orders | N | R proof of delivery | U | U billing records | N | U assigned office |
| Finance Manager | U | R | N | R | A/U | R financial records | N | U assigned office |
| Compliance / Records Manager | U | R | R | R | R | A/U | R evidence only | T records areas |
| Vendor Management / Procurement | U | N | N | N | R vendor payments only | U contracts | N | U assigned office |
| Third-Party Support User | T | T | T | T | T | T only if specifically required | N or T approved support identity | T escorted or remote only |
| Physical Security / Facilities | U limited | N | N | N | N | U physical-access records | N | P physical-access system |
| Service Account | N unless required | T approved integration | T approved integration | T approved integration | T approved integration | T approved process | T workload identity | N |

## Data-Access Rules

### Public Information

- May be accessed and shared according to approved communications practices.
- Public classification does not authorize changes to official content.

### Internal Information

- Available to employees and explicitly authorized contractors with a legitimate business need.
- Must not be posted publicly without authorization.

### Confidential Information

- Requires role-based access and an approved business purpose.
- Bulk export, external sharing, forwarding, and download should be restricted where feasible.
- Access should be logged and reviewed for high-value systems.

### Restricted Information

- Requires explicit authorization, minimum-necessary access, strong authentication, encryption, and enhanced logging.
- Access must be limited by role, assignment, client, transaction, or approved case where feasible.
- Independent couriers receive only the Restricted information necessary to complete an active assignment.
- Legal, privacy, contractual, or compliance review is required where PHI/ePHI or payment-card obligations may apply.

## Segregation-of-Duties Rules

| Activity | Incompatible or Separately Reviewed Activities |
|---|---|
| Requesting access | Approving and provisioning the same access |
| Approving access | Independently provisioning and certifying the same access |
| IAM administration | Independent review of IAM administrator activity |
| Creating or changing vendor records | Sole approval of vendor onboarding and payment changes |
| Preparing invoices | Sole approval of billing adjustments, refunds, or sensitive payment changes |
| Changing payment instructions | Independently approving and reconciling the same change |
| System administration | Independent security-log review and control-effectiveness testing |
| Operating backups | Independent validation of restoration results where feasible |
| Performing warehouse transactions | Sole approval of inventory adjustments or exception resolution |
| Dispatch assignment | Unauthorized alteration of completed proof-of-delivery records |
| Risk ownership | Independent GRC assessment and challenge |
| Physical-access request | Approving and issuing one's own badge or restricted-area access |

When staffing limitations prevent full separation, PLG must document a compensating control such as secondary review, enhanced logging, transaction reconciliation, time-limited access, or management approval.

## Employee and Independent-Courier Separation

Independent couriers are external users and must not be treated as employees for access purposes.

### Required Courier Controls

- Use a unique external identity rather than an employee account.
- Limit access to active assignments and minimum necessary data.
- Prevent directory browsing and access to internal Microsoft 365 resources unless specifically approved.
- Prohibit access to unrelated customers, routes, recipients, deliveries, or historical records.
- Expire or disable access at assignment or engagement completion.
- Apply MFA or an appropriate strong authentication method supported by the delivery platform.
- Restrict unnecessary download, local storage, screenshot, forwarding, printing, and copy/paste where technically feasible.
- Log authentication, assignment access, proof-of-delivery activity, exceptions, and administrative changes.
- Require contractual security, privacy, incident-reporting, device, and data-deletion obligations.

## Mobile and Driver Access Requirements

- Drivers must interact with applications only at safe workflow points, including dispatch, pickup, parked status updates, and delivery confirmation.
- Authentication design must not encourage interaction while actively driving.
- Mobile screens should display only the information needed for the current task.
- Session duration should balance risk with safe, usable workflows.
- Lost, stolen, replaced, or noncompliant devices must support prompt session revocation and access removal.
- Sensitive information should not remain in local notifications, downloads, photos, caches, or message history longer than necessary.
- Approved personal-device access must meet documented BYOD and application-protection requirements.

## Privileged-Access Requirements

1. Administrators must use separate standard-user and privileged accounts.
2. Privileged access requires MFA and approved secure administration methods.
3. Standing privilege should be minimized; time-limited elevation should be used where supported.
4. Privileged accounts must not be used for email, web browsing, or routine office work.
5. Administrative activity must be logged and independently reviewed.
6. Emergency or break-glass accounts must be tightly controlled, monitored, tested, and reviewed after use.
7. Vendor administrative access must be named, approved, time-limited, logged, and disabled when the support task ends.
8. Service accounts require a named owner, documented purpose, minimum permissions, protected credentials, and periodic review.

## Access Request and Approval

Every access request must document:

- User name and workforce or vendor identifier
- Employment, contractor, courier, service-account, or vendor status
- Requested role and systems
- Business justification
- Location, department, client, or assignment scope
- Information classification involved
- Requested start and expiration dates
- Manager approval
- System or data-owner approval where required
- Additional approval for privileged, financial, Restricted, or physical access
- Provisioner and completion date

Users must not approve their own access.

## Joiner-Mover-Leaver Requirements

### Joiner

- HR, Vendor Management, or the authorized sponsor initiates the identity record.
- The manager selects an approved role rather than requesting unrestricted access.
- Required approvals must be completed before provisioning.
- Access begins no earlier than the approved start date.
- Training, policy acknowledgment, and device requirements must be completed according to role.

### Mover

- The manager documents the new role, effective date, and required access.
- Old access must be removed rather than merely adding new permissions.
- Incompatible privileges must be identified before the change is completed.
- Temporary overlap requires approval, justification, monitoring, and an expiration date.

### Leaver

- Involuntary or high-risk termination access must be disabled at or immediately before notification, coordinated with authorized leadership and HR.
- Standard employee access must be disabled no later than the effective separation time.
- Courier access must expire after the final approved assignment or end of engagement.
- Vendor access must be removed when the support need or contract ends.
- Badges, devices, tokens, keys, records, sessions, forwarding rules, shared secrets, and data ownership must be addressed.
- Disablement must be verified across IAM, SaaS, on-premises, mobile, physical, and vendor-managed systems.

## Access-Review Schedule

| Access Type | Review Frequency | Reviewer |
|---|---|---|
| Privileged and emergency access | Quarterly; after every emergency use | IT Director and independent reviewer |
| IAM, Microsoft 365, logistics, dispatch, billing, and archive access | Quarterly for high-risk roles | System and data owners |
| Warehouse Management System access | Quarterly | Warehouse Operations Manager and IT |
| Independent-courier access | Continuous by assignment; monthly account reconciliation | Dispatch Manager |
| Vendor and third-party support access | Quarterly and at contract or task completion | Vendor Management and System Owner |
| Physical and restricted-area access | Quarterly | Facilities Manager and area owner |
| Service accounts and integrations | Quarterly | Technical owner and System Owner |
| Standard low-risk access | At least semiannually | Manager and System Owner |

Reviewers must verify:

- The user still requires access.
- The assigned role remains appropriate.
- Privileges do not exceed approved responsibilities.
- Conflicting permissions are removed or compensated.
- Dormant, duplicate, shared, orphaned, and expired accounts are addressed.
- Exceptions remain justified and have not expired.
- Review decisions and remediation are documented.

## Emergency Access

Emergency access may be used only when normal access would unreasonably delay the response to a critical operational or security event.

Emergency access must:

- Be approved by designated authority or governed by a documented break-glass process.
- Use a unique and attributable account.
- Be time-limited.
- Be logged and monitored.
- Be restricted to the minimum required action.
- Trigger prompt credential rotation or access removal after use.
- Receive an after-action review no later than the next business day.

## Access Exceptions

Exceptions must include:

- The control or role requirement that cannot be met
- Business justification
- Affected user, system, data, and duration
- Related risks
- Compensating controls
- Risk owner and approver
- Start date, expiration date, and review frequency
- Monitoring and removal requirements

Permanent exceptions are not permitted without formal risk acceptance and periodic reapproval.

## Required Evidence

| Control Area | Expected Evidence |
|---|---|
| Role design | Approved role catalog, permission matrix, system-owner sign-off |
| Access requests | Tickets, business justification, approvals, start and expiration dates |
| Provisioning | Account and role records, completion timestamps, provisioner identity |
| Termination | HR notice, disablement timestamps, session revocation, badge/device return |
| Access reviews | User and permission exports, reviewer decisions, removal evidence, exceptions |
| Privileged access | Admin inventory, MFA coverage, activity logs, elevation records, break-glass tests |
| Courier access | Assignment records, external identities, access expiration, device requirements, logs |
| Vendor access | Contract, sponsor, approval, access window, monitored activity, removal evidence |
| Service accounts | Owner, purpose, permissions, credential controls, usage logs, review record |
| Physical access | Badge inventory, visitor logs, restricted-area approvals, termination samples |

## Risk and Control Traceability

| Related Risk | RBAC Response |
|---|---|
| R-01 Phishing and Account Compromise | MFA, conditional access, separate privileged accounts, session revocation, and authentication logging |
| R-02 Delayed or Incomplete Deprovisioning | Joiner-mover-leaver workflow, termination deadlines, reconciliation, and assignment expiration |
| R-03 Excessive or Conflicting Privileges | Role catalog, least privilege, segregation of duties, access reviews, and exceptions |
| R-04 Courier and BYOD Exposure | External identities, assignment-based access, mobile safeguards, and prompt revocation |
| R-05 Unauthorized PHI/ePHI Access | Minimum-necessary roles, explicit approval, Restricted-data safeguards, and enhanced evidence |
| R-06 Sensitive Information in Collaboration Tools | Role-limited sharing, guest-access control, and Restricted-data authorization |
| R-07 Warehouse-System Exposure | Limited WMS roles, controlled administration, and periodic access review |
| R-08 Vendor Breach or Outage | Named, approved, time-limited, monitored vendor access |
| R-09 Insufficient Monitoring | Authentication, authorization, privileged-activity, and administrative logs |
| R-11 Payment and Financial Exposure | Finance roles, segregation of duties, least privilege, and change monitoring |
| R-13 Unauthorized Physical Access | Role-based badge access, lifecycle integration, and quarterly review |
| R-14 Unsafe or Unworkable Driver Controls | Safe workflow points, usable authentication, minimized display, and frontline testing |

## Framework Alignment

This model is primarily aligned with:

- NIST CSF 2.0: PR.AA, PR.AT, PR.DS, DE.CM, GV.RR
- NIST SP 800-53 Rev. 5: AC-2, AC-3, AC-5, AC-6, AC-17, AC-19, AC-20, IA-2, IA-4, IA-5, PS-4, PS-5, AU-2, AU-6, PE-2, and PE-3

Mappings indicate relevant relationships and do not establish certification or compliance.

## Approval and Maintenance

- The IT Director maintains the technical access model.
- Business and data owners approve role content for their systems and information.
- HR, Vendor Management, Facilities, and Dispatch maintain authoritative workforce, vendor, physical-access, and courier lifecycle inputs.
- The GRC Analyst reviews the model for risk, evidence, exception, and control alignment.
- The model must be reviewed at least annually and after material system, workflow, vendor, regulatory, contractual, or organizational changes.

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. Roles, permissions, timeframes, and mappings demonstrate a proposed GRC and IAM design and are not implemented settings from a real organization.
