# Evidence and Control Testing Plan

## Purpose

This plan defines how Peachtree Logistics Group (PLG) will collect evidence and evaluate whether selected security controls are appropriately designed, implemented, and operating effectively.

The plan is designed for PLG's mixed cloud and on-premises environment and prioritizes controls related to identity and access management, Microsoft 365, logistics platforms, warehouse systems, mobile devices, medical-delivery information, payment processes, physical security, workforce practices, and third-party access.

This document supports:

- `docs/04-asset-and-system-inventory.md`
- `docs/05-risk-assessment-methodology.md`
- `docs/06-risk-register.md`
- `docs/07-security-control-matrix.md`
- `docs/08-role-based-access-control-model.md`
- `docs/09-iam-and-security-procedures.md`
- `docs/10-security-awareness-plan.md`
- `docs/11-incident-response-scenarios.md`

## Objectives

The testing program will:

1. Determine whether key controls address their intended risks.
2. Confirm that documented procedures have been implemented.
3. Evaluate whether controls operate consistently over time.
4. Identify gaps in control ownership, evidence, execution, or monitoring.
5. Distinguish isolated exceptions from systemic control failures.
6. Produce reproducible workpapers and defensible conclusions.
7. Prioritize remediation based on risk and operational impact.
8. Measure whether security improvements reduce PLG's residual risk.

## Scope

### In Scope

- Microsoft 365 identity, email, Teams, and SharePoint controls
- Identity and access management services
- Cloud logistics and freight-brokerage applications
- On-premises Warehouse Management System
- Dispatch and delivery platform
- Billing and accounting system
- Records archive
- Employee laptops and mobile devices
- PLG-employed driver devices
- Approved personal devices used for PLG work
- Independent-courier access
- User provisioning, role changes, access reviews, and offboarding
- Privileged and service accounts
- Medical-delivery information handling
- Payment-change and approval controls
- Security awareness and incident reporting
- Physical access to PLG offices and warehouses
- Vendor onboarding, access, monitoring, and offboarding

### Out of Scope

- Active exploitation or penetration testing
- Destructive testing of production systems
- Direct inspection of vendor-owned internal environments
- Vehicle mechanical systems and telematics hardware
- Physical building construction and engineering
- Legal conclusions regarding HIPAA, PCI DSS, or breach-notification applicability

## Assessment Limitations

Testing is based on interviews, observation, documentation, configuration review, log review, and sampling. A passing sample does not guarantee that every transaction or account complied. Vendor assertions are evaluated through evidence available to PLG and do not constitute an independent audit of the vendor.

## Roles and Responsibilities

| Role | Responsibility |
|---|---|
| GRC Analyst / Test Lead | Plans testing, requests evidence, selects samples, performs tests, documents results, and drafts findings |
| Control Owner | Explains control design, supplies evidence, validates populations, and responds to exceptions |
| System Owner | Provides system context, configuration evidence, reports, and remediation support |
| Data Owner | Confirms information sensitivity, access need, and acceptable use |
| IT / IAM Administrator | Produces identity, configuration, device, logging, and technical evidence |
| HR Manager | Provides workforce lifecycle evidence and validates employment events |
| Department Managers | Validate roles, approvals, operational practices, and sampled transactions |
| Vendor Management | Provides contracts, due-diligence records, access lists, and vendor-monitoring evidence |
| Medical Courier Program Manager | Validates medical-delivery workflows and minimum-necessary handling |
| Finance Manager | Provides payment-control evidence and validates segregation of duties |
| Executive Sponsor | Resolves escalated access issues, resource conflicts, and risk-acceptance decisions |

Testers should not test controls they personally perform without independent review of the conclusion.

## Testing Concepts

### Design Effectiveness

A control is designed effectively when it:

- Has a clearly defined risk and objective
- Has an assigned owner
- Defines who performs it, how, and when
- Covers the appropriate systems, identities, information, and locations
- Produces reviewable evidence
- Includes escalation or correction when exceptions occur
- Can operate without creating unacceptable safety or operational disruption

### Implementation Status

A control is implemented when the designed procedure, configuration, or safeguard exists in the relevant environment and is available for use.

### Operating Effectiveness

A control operates effectively when evidence shows it was performed consistently, by authorized personnel, at the required frequency, across the defined population, and with timely follow-up of exceptions.

### Sustainability

A control is sustainable when PLG can continue operating it with available staffing, skills, technology, budget, and workflow constraints.

## Test Result Ratings

| Rating | Definition |
|---|---|
| Effective | Control is appropriately designed, implemented, and operating as intended; no material exceptions identified |
| Effective with Minor Exceptions | Control generally operates as intended, but limited exceptions do not materially undermine the objective |
| Partially Effective | Control exists but design, coverage, consistency, evidence, or follow-up weaknesses reduce assurance |
| Ineffective | Control is absent, materially misdesigned, not implemented, or fails to address the intended risk |
| Not Tested | Testing could not be completed because the control was out of scope, not yet due, unavailable, or lacked an adequate population |
| Not Applicable | The control objective does not apply to the evaluated system, role, process, or period |

## Evidence Standards

Evidence should be sufficient, relevant, reliable, complete, timely, and reproducible.

### Evidence Quality Criteria

| Criterion | Evaluation Question |
|---|---|
| Sufficiency | Is there enough evidence to support the conclusion? |
| Relevance | Does the evidence directly address the control objective and test period? |
| Reliability | Was the evidence generated by a trustworthy source with limited opportunity for alteration? |
| Completeness | Does the evidence represent the full population or clearly defined sample? |
| Timeliness | Does the evidence cover the applicable assessment period? |
| Reproducibility | Could another qualified reviewer repeat the test and reach a similar conclusion? |

### Evidence Reliability Hierarchy

Evidence is generally stronger in the following order:

1. Tester-obtained system exports or direct read-only observation
2. System-generated reports with documented parameters and timestamps
3. Approved records showing performance and review
4. Screenshots with visible context, date, system, and configuration path
5. Written procedures, tickets, emails, or meeting records
6. Interview statements without corroboration

Interviews are valuable for understanding control design but should not be the sole basis for concluding that a recurring control operates effectively.

## Evidence Handling Requirements

- Request only the evidence necessary to perform the test.
- Redact or minimize PHI/ePHI, payment data, credentials, secrets, and unrelated personal information.
- Never collect passwords, MFA codes, private keys, or complete payment-card data.
- Store evidence in a restricted assessment location.
- Assign each item a unique evidence identifier.
- Record the source, owner, collection date, covered period, and related test.
- Preserve original exports when possible.
- Document filters, parameters, time zones, and transformations.
- Use secure transfer methods.
- Restrict evidence access to authorized participants.
- Retain and dispose of evidence according to approved requirements.
- Do not place operational evidence or real sensitive data in the public portfolio repository.

## Evidence Naming Convention

Use the following format:

`EV-[TestID]-[Sequence]-[YYYYMMDD]-[ShortDescription]`

Examples:

- `EV-CT01-01-20260917-M365-MFA-Export`
- `EV-CT04-03-20260917-Terminated-User-Ticket`
- `EV-CT12-02-20260917-Training-Completion-Report`

## Evidence Register

| Evidence ID | Test ID | Description | Source / Owner | Period Covered | Date Collected | Storage Location | Sensitivity | Reviewer |
|---|---|---|---|---|---|---|---|---|
| EV-CT01-01 | CT-01 | Example MFA registration export | IAM Administrator | Assessment period | YYYY-MM-DD | Restricted evidence folder | Confidential | GRC Analyst |

The example row should be replaced with actual assessment records. Sensitive operational locations and evidence should remain outside the public repository.

## Evidence Request Process

1. Define the control objective and required population.
2. Identify the authoritative source and evidence owner.
3. Issue a request containing the required fields, period, format, and due date.
4. Confirm whether sensitive fields should be redacted.
5. Validate the report parameters and completeness when evidence is received.
6. Record the evidence in the evidence register.
7. Follow up on missing, unclear, or conflicting information.
8. Protect and retain the evidence according to policy.

## Population Validation

Before selecting samples, the tester should determine whether the population is complete and accurate.

Validation techniques include:

- Reconcile system user lists to authoritative HR or vendor records.
- Compare beginning and ending populations with additions and removals.
- Review report filters, date ranges, status fields, and excluded records.
- Compare system-generated totals to control-owner totals.
- Check for duplicate, blank, disabled, service, shared, or unlicensed accounts.
- Trace selected source records into the population.
- Trace selected population records back to the source system.

If population reliability cannot be established, the test limitation must be documented and the control may require a separate finding.

## Sampling Methodology

Sampling should reflect risk, control frequency, population size, control maturity, prior findings, and expected reliance.

### Baseline Sample Guidance

| Control Frequency | Suggested Baseline Sample |
|---|---:|
| Annual | 1 occurrence |
| Semiannual | 1–2 occurrences |
| Quarterly | 2 occurrences |
| Monthly | 3 occurrences |
| Weekly | 5 occurrences |
| Daily or transaction-based | 10–25 items, based on risk and population |
| Continuous / automated | Inspect configuration plus exceptions across the assessment period |

These are risk-based portfolio guidelines rather than statistically representative sample sizes.

### Targeted Sampling

Samples should intentionally include higher-risk items such as:

- Privileged users
- Departed and transferred employees
- Independent couriers
- Vendors with remote access
- Medical-courier roles
- Finance and payment approvers
- Users with multiple roles
- Temporary or emergency access
- Exceptions and override transactions
- Accounts without recent activity
- Shared or service accounts
- Personally owned devices

### Sample Expansion

The tester should expand a sample when:

- An exception appears systemic
- Multiple exceptions share a cause
- The population is unreliable
- A high-risk account or transaction fails
- Control evidence conflicts with interviews or configurations
- Prior findings remain unresolved

## Test Schedule

| Phase | Activities | Target Timing |
|---|---|---|
| Planning | Confirm scope, controls, owners, period, populations, and evidence requests | Week 1 |
| Evidence Collection | Receive inventories, exports, configurations, tickets, approvals, and policies | Weeks 1–2 |
| Design Assessment | Review control objectives, procedures, ownership, coverage, and evidence design | Week 2 |
| Operating Effectiveness Testing | Validate populations, select samples, perform tests, and document exceptions | Weeks 2–3 |
| Validation | Discuss exceptions with owners and obtain relevant supplemental evidence | Week 3 |
| Reporting | Rate results, draft findings, assess residual risk, and recommend remediation | Week 4 |
| Management Response | Assign owners, target dates, and remediation commitments | Week 4 |

## Control Testing Catalog

### CT-01: Multifactor Authentication Coverage

**Objective:** Confirm that MFA is enabled for required workforce, administrator, vendor, and remote-access accounts.

**Evidence:**

- Identity-provider user and MFA registration export
- Conditional-access or equivalent authentication policies
- Approved exception register
- Sample authentication logs

**Test procedure:**

1. Obtain the complete in-scope identity population.
2. Reconcile the population to HR, vendor, courier, and privileged-user records.
3. Inspect policies to confirm required users and applications are covered.
4. Identify accounts without compliant MFA or excluded from policy.
5. Sample privileged, finance, medical-courier, vendor, and driver accounts.
6. Verify that exceptions are approved, time-limited, and monitored.
7. Document coverage percentage and unexplained gaps.

**Pass criteria:** All required accounts are covered by an approved MFA method or a documented compensating control and approved exception.

### CT-02: Conditional Access and Authentication Controls

**Objective:** Confirm that access policies reduce risky authentication without preventing safe, authorized work.

**Evidence:**

- Conditional-access configuration
- Named-location, device, risk, and session settings
- Policy change records
- Sign-in and policy-result logs
- Break-glass account records

**Test procedure:**

1. Inspect policy scope, exclusions, enforcement state, and protected applications.
2. Confirm privileged and sensitive applications receive stronger protection.
3. Verify that emergency-access accounts are limited, monitored, and tested.
4. Sample successful and blocked sign-ins to verify expected policy results.
5. Review driver or courier workflows for unsafe authentication prompts while driving.

**Pass criteria:** Policies cover the intended population, exceptions are justified, emergency access is controlled, and no material workflow or safety conflict is identified.

### CT-03: New User Provisioning

**Objective:** Confirm that new access is based on approved roles and authorized business need.

**Evidence:**

- New-hire list
- Access requests and approvals
- Role assignments
- Training completion records
- Account creation logs

**Test procedure:**

1. Obtain the population of accounts created during the test period.
2. Select a risk-based sample across departments and worker types.
3. Verify employment or contract status, manager approval, assigned RBAC role, and required training.
4. Compare granted permissions to the approved request and role baseline.
5. Confirm privileged, financial, medical-delivery, and vendor access received required additional approval.

**Pass criteria:** Sampled access is authorized, role appropriate, timely, traceable, and not broader than approved.

### CT-04: Role Changes and Transfers

**Objective:** Confirm that access is adjusted promptly when responsibilities change.

**Evidence:**

- HR transfer report
- Manager notifications
- Access modification tickets
- Before-and-after role assignments
- Segregation-of-duties review

**Test procedure:**

1. Obtain the population of transfers and material role changes.
2. Select a sample that includes sensitive and cross-department changes.
3. Verify that new access was approved and obsolete access removed.
4. Confirm conflicting permissions were identified and resolved.
5. Compare completion dates to the effective transfer dates.

**Pass criteria:** Access changes are complete, timely, approved, and aligned to the new role.

### CT-05: Termination and Offboarding

**Objective:** Confirm that logical and physical access is removed promptly when employment, assignments, or contracts end.

**Evidence:**

- Termination and contract-end population
- Account disablement logs
- Session and token revocation records
- Badge deactivation records
- Device and asset-return records
- Vendor and courier access records

**Test procedure:**

1. Reconcile termination records to accounts across in-scope systems.
2. Sample voluntary, involuntary, vendor, temporary, driver, and courier departures.
3. Compare effective separation time to account and badge disablement.
4. Confirm sessions, tokens, remote access, application access, and shared secrets were addressed.
5. Review post-termination activity.
6. Verify asset return or remote protection when assets were not returned.

**Pass criteria:** Access is removed within the required target, assets are addressed, and no unexplained post-termination use exists.

### CT-06: Periodic Access Reviews

**Objective:** Confirm that System and Data Owners periodically validate user, privileged, vendor, and service-account access.

**Evidence:**

- Access-review population
- Reviewer assignments
- Completed certifications
- Decisions and comments
- Removal tickets
- Escalation records

**Test procedure:**

1. Inspect the review scope and verify that all required systems and account types are included.
2. Confirm reviewers are knowledgeable and independent enough to evaluate access.
3. Sample retained, removed, modified, and unresolved decisions.
4. Verify timely completion of resulting changes.
5. Identify rubber-stamping, incomplete reviews, or unexplained bulk approvals.

**Pass criteria:** Reviews are complete, meaningful, performed on schedule, and followed by timely remediation.

### CT-07: Privileged and Service Account Management

**Objective:** Confirm that elevated and nonhuman accounts are limited, protected, monitored, and attributable.

**Evidence:**

- Privileged and service-account inventories
- Account-owner records
- Approval and access-review records
- MFA and password or secret-management settings
- Administrative activity logs

**Test procedure:**

1. Reconcile privileged accounts to authorized administrators.
2. Confirm administrators use separate standard and privileged accounts.
3. Verify MFA and secure administrative access.
4. Review dormant, shared, default, and emergency accounts.
5. Sample service accounts for owner, purpose, permissions, credential management, and interactive-login restrictions.
6. Review privileged activity monitoring and escalation.

**Pass criteria:** Accounts are necessary, assigned, least-privileged, protected, reviewed, and monitored.

### CT-08: Mobile Device and Driver Application Security

**Objective:** Confirm that PLG and approved personal devices protect PLG data while supporting safe delivery workflows.

**Evidence:**

- Managed-device inventory
- Mobile security policy or configuration
- Encryption, screen-lock, update, and compliance reports
- Delivery-platform session settings
- Lost-device incidents and response records
- BYOD acknowledgments

**Test procedure:**

1. Reconcile active driver and courier identities to authorized devices.
2. Sample PLG-issued and approved personal devices.
3. Verify encryption, screen lock, current software, application controls, and remote-protection capability as applicable.
4. Review local storage, screenshots, downloads, caches, and notification exposure controls.
5. Confirm lost-device reporting and session-revocation processes.
6. Observe whether authentication and reporting can occur at safe workflow points.

**Pass criteria:** Sampled devices meet defined requirements, unauthorized devices are blocked or restricted, and controls do not require unsafe interaction while driving.

### CT-09: Medical-Delivery Information Handling

**Objective:** Confirm that access, disclosure, storage, and retention of applicable medical-delivery information follow minimum-necessary practices.

**Evidence:**

- Role and access lists
- Medical-delivery workflow documentation
- Sample delivery records with sensitive details redacted
- Sharing and access logs
- Retention settings
- Training records
- Incident and exception records

**Test procedure:**

1. Identify roles and systems that handle medical-delivery information.
2. Sample medical-delivery transactions across intake, dispatch, delivery, confirmation, and retention.
3. Verify that only necessary information was available at each stage.
4. Confirm approved communication channels and recipient verification.
5. Review access after assignment completion and applicable retention settings.
6. Confirm relevant personnel completed role-based training.

**Pass criteria:** Access and disclosure are limited to authorized purposes, transactions use approved channels, and unnecessary persistence is not identified.

### CT-10: Payment Change and Approval Controls

**Objective:** Confirm that payment, bank-detail, refund, and vendor-master changes receive independent verification and appropriate approval.

**Evidence:**

- Population of payment and vendor-detail changes
- Approval records
- Callback or independent-verification records
- System role assignments
- Exception and override reports

**Test procedure:**

1. Validate the completeness of the change population.
2. Sample routine, high-value, urgent, rejected, and overridden changes.
3. Verify requester and approver separation.
4. Confirm independent verification through a known contact method.
5. Review system access for conflicting initiation and approval permissions.
6. Inspect exceptions for documented authorization and follow-up.

**Pass criteria:** Sampled changes are independently verified, appropriately approved, segregated, and traceable.

### CT-11: Security Logging and Monitoring

**Objective:** Confirm that PLG collects, protects, reviews, and retains logs necessary to detect and investigate material events.

**Evidence:**

- Logging architecture and source inventory
- Microsoft 365, IAM, endpoint, network, application, WMS, and mobile-platform settings
- Alert rules and review records
- Retention configuration
- Sample alerts and incident tickets

**Test procedure:**

1. Compare required log sources to connected and active sources.
2. Inspect retention, access restrictions, time synchronization, and integrity protections.
3. Sample high-risk events such as privileged changes, failed sign-ins, external sharing, account disablement, and vendor access.
4. Trace selected alerts to review, escalation, or closure.
5. Identify material visibility gaps.

**Pass criteria:** Required sources produce usable logs, high-risk events are monitored, and alerts receive documented review.

### CT-12: Security Awareness and Role-Based Training

**Objective:** Confirm that personnel complete relevant training and demonstrate expected security behavior.

**Evidence:**

- Workforce and contractor population
- Training assignments and completion report
- Role-to-training matrix
- Knowledge checks and exercise results
- Remedial training records
- Approved exceptions

**Test procedure:**

1. Reconcile the training population to active employees, contractors, couriers, privileged users, and relevant vendors.
2. Verify foundational and role-specific assignment rules.
3. Sample finance, dispatch, medical-courier, warehouse, IT, driver, and manager records.
4. Confirm required training preceded sensitive access where required.
5. Review overdue items, exceptions, simulations, and remedial actions.
6. Evaluate behavioral metrics rather than completion alone.

**Pass criteria:** Required audiences receive timely, relevant training and material gaps receive follow-up.

### CT-13: Incident Response Readiness

**Objective:** Confirm that PLG can identify, escalate, contain, document, and recover from priority incident scenarios.

**Evidence:**

- Incident response plan and playbooks
- Contact and escalation lists
- Incident tickets
- Tabletop records
- After-action reports
- Corrective-action tracker

**Test procedure:**

1. Inspect roles, severity criteria, reporting methods, and escalation paths.
2. Sample incidents or exercises covering account compromise, lost devices, sensitive-data exposure, ransomware, payment fraud, or vendor disruption.
3. Verify timestamps, decisions, evidence preservation, communications, recovery, and post-incident review.
4. Confirm corrective actions are assigned and tracked.

**Pass criteria:** PLG demonstrates coordinated response, documented decisions, protected operations, and follow-through on lessons learned.

### CT-14: Vulnerability, Patching, and Endpoint Protection

**Objective:** Confirm that PLG identifies and remediates vulnerabilities based on risk, especially for the on-premises WMS and endpoints.

**Evidence:**

- Asset and vulnerability inventories
- Patch and endpoint-protection reports
- Remediation tickets
- Approved exceptions
- Unsupported-system plans

**Test procedure:**

1. Reconcile scanned or managed assets to the inventory.
2. Review coverage and update status for servers, employee endpoints, and managed mobile devices.
3. Sample critical, high, overdue, internet-facing, and WMS findings.
4. Verify remediation within PLG targets or documented exception approval.
5. Review compensating controls for unsupported systems.

**Pass criteria:** Material assets are covered, urgent weaknesses receive timely treatment, and exceptions are documented and monitored.

### CT-15: Backup and Recovery

**Objective:** Confirm that critical data and systems can be restored from protected, tested backups.

**Evidence:**

- Backup scope and configuration
- Job success and failure records
- Access restrictions
- Restore-test results
- Recovery objectives
- Exception tickets

**Test procedure:**

1. Compare critical systems and data to backup coverage.
2. Inspect backup isolation, encryption, access, monitoring, and retention.
3. Sample successful and failed jobs.
4. Review evidence of restoration testing.
5. Compare actual test results to recovery objectives.

**Pass criteria:** Critical information is backed up, failures are resolved, backups are protected, and restoration is tested successfully.

### CT-16: Vendor Risk and Third-Party Access

**Objective:** Confirm that PLG evaluates vendors, defines security obligations, restricts access, monitors material relationships, and performs secure offboarding.

**Evidence:**

- Vendor inventory and risk tiers
- Due-diligence records
- Contracts and security addenda
- Vendor access lists
- Periodic reviews
- Incident notices
- Offboarding records

**Test procedure:**

1. Validate the completeness of the in-scope vendor population.
2. Sample critical SaaS, logistics, payment, medical-delivery, and support vendors.
3. Verify risk tiering, due diligence, contract requirements, and accountable owner.
4. Review vendor identities for named accounts, MFA, least privilege, expiration, and monitoring.
5. Confirm material incidents and performance issues are tracked.
6. Sample terminated vendors for access removal and data-return or disposal requirements.

**Pass criteria:** Vendors receive risk-appropriate review and contractual treatment, and their access is controlled throughout the relationship.

### CT-17: Physical Access and Visitor Management

**Objective:** Confirm that access to offices, warehouses, network areas, records, and sensitive storage is authorized and monitored.

**Evidence:**

- Badge-holder list
- Physical access approvals
- Entry logs
- Visitor records
- Badge deactivation records
- Sensitive-area access list

**Test procedure:**

1. Reconcile badge holders to active workforce and vendor populations.
2. Sample new, transferred, terminated, temporary, and vendor badge holders.
3. Verify authorization and timely deactivation.
4. Review visitor sign-in, escort, and badge-return practices.
5. Observe selected physical practices without disrupting operations.
6. Review access to network rooms and sensitive storage.

**Pass criteria:** Physical access is authorized, current, traceable, and proportionate to business need.

### CT-18: Records Retention and Secure Disposal

**Objective:** Confirm that PLG retains records only as required and disposes of them securely.

**Evidence:**

- Retention schedule
- System retention configurations
- Legal-hold procedures
- Disposal logs or vendor certificates
- Archive access list
- Sample retained records

**Test procedure:**

1. Map major record types to approved retention requirements.
2. Inspect retention settings for Microsoft 365, logistics, delivery, billing, and archive systems.
3. Sample expired records and confirm timely disposition where no hold applies.
4. Review archive access and disposal-provider controls.
5. Identify indefinite retention without documented need.

**Pass criteria:** Retention aligns with approved requirements, archive access is restricted, and disposal is authorized and verifiable.

## Control Test Workpaper Template

### Test Identification

| Field | Entry |
|---|---|
| Test ID | CT-XX |
| Control ID(s) | CTL-XX |
| Control Name |  |
| Related Risk(s) | R-XX |
| System / Process |  |
| Control Owner |  |
| Test Period |  |
| Tester |  |
| Reviewer |  |

### Test Details

**Control objective:**

Describe the risk-reduction outcome the control is intended to achieve.

**Control description:**

Describe who performs the control, how it operates, its frequency, population, evidence, and escalation path.

**Design assessment:**

Document whether the control is appropriately designed and why.

**Population:**

Document the population source, size, period, validation steps, and known limitations.

**Sample:**

Document the sampling method, size, items selected, and reason for targeted selections.

**Evidence reviewed:**

- EV-CTXX-01
- EV-CTXX-02

**Procedures performed:**

1. Procedure one
2. Procedure two
3. Procedure three

**Exceptions:**

Document each exception, affected item, expected condition, observed condition, evidence, and control-owner explanation.

**Conclusion:**

- Design effectiveness: Effective / Ineffective / Not Tested
- Implementation: Implemented / Partially Implemented / Not Implemented
- Operating effectiveness: Effective / Effective with Minor Exceptions / Partially Effective / Ineffective / Not Tested
- Sustainability: Sustainable / Improvement Needed / Unsustainable

**Reviewer sign-off:**

Document reviewer, review date, comments, and resolution of review notes.

## Exception Evaluation

Each exception should be evaluated based on:

- Sensitivity of affected information
- Privilege of the affected identity
- Criticality of the affected system or service
- Number and percentage of affected items
- Duration of exposure
- Whether the issue is isolated or systemic
- Whether the control detected and corrected its own failure
- Prior exceptions or repeat findings
- Operational, safety, legal, privacy, financial, and contractual impact
- Effectiveness of compensating controls

An exception is not automatically a finding. The tester must evaluate whether it materially affects the control objective.

## Finding Severity

| Severity | Description | Example |
|---|---|---|
| Critical | Immediate, widespread, or severe exposure with a high probability of major impact | Active privileged-account compromise or unprotected widespread Restricted-data access |
| High | Material control failure affecting sensitive data, critical systems, or essential operations | Former administrator retains active access; critical system lacks recoverable backups |
| Moderate | Meaningful weakness with limited scope or compensating controls | Inconsistent quarterly access review or delayed removal for a low-privilege account |
| Low | Limited issue that does not materially undermine the control objective | Minor documentation inconsistency or isolated late approval |
| Observation | Improvement opportunity without a confirmed control failure | Simplify evidence retention or improve dashboard clarity |

## Finding Template

### Finding [ID]: [Title]

**Severity:** Critical / High / Moderate / Low / Observation

**Condition:**

What the tester observed.

**Criteria:**

The policy, procedure, control requirement, contract, framework expectation, or approved practice that should have been met.

**Cause:**

Why the condition occurred, including process, technology, staffing, training, ownership, vendor, or design factors.

**Risk / Effect:**

How the issue could affect confidentiality, integrity, availability, privacy, safety, finances, compliance, or operations.

**Evidence:**

Reference the supporting evidence and affected sample items without exposing sensitive details.

**Recommendation:**

Provide a practical, risk-based corrective action that fits PLG's environment.

**Management Response:**

Document whether management agrees, the chosen remediation, accountable owner, resources, and target date.

**Residual Risk:**

Document the expected remaining risk after remediation and whether formal acceptance is required.

## Remediation Validation

A finding should not be closed based only on a management statement. Closure evidence should demonstrate that:

1. The corrective action addresses the root cause.
2. The updated control is implemented.
3. The affected population has been corrected.
4. The control operated successfully for a reasonable period or transaction sample.
5. Policies, procedures, training, or ownership were updated when necessary.
6. No material unintended operational or safety impact was introduced.

Findings requiring extended observation may be marked **Remediated—Monitoring in Progress** until operating effectiveness can be validated.

## Quality Assurance

Before finalizing a test, the reviewer should confirm that:

- The control objective and risks are clear.
- Evidence supports the stated period and population.
- Population completeness was evaluated.
- Sampling is documented and risk based.
- Procedures can be reproduced.
- Exceptions are supported by evidence.
- The conclusion matches the results.
- Conflicting evidence is resolved or disclosed.
- Sensitive data is minimized and protected.
- Findings identify root cause and practical remediation.
- Control owners had an opportunity to validate factual accuracy.
- Reviewer comments are resolved and documented.

## Reporting

The final assessment report should include:

- Executive summary
- Scope and limitations
- Testing methodology
- Controls tested
- Design and operating-effectiveness results
- Findings by severity and risk domain
- Repeat findings
- Root-cause themes
- Remediation owners and target dates
- Residual-risk implications
- KPI and KRI baseline
- Management decisions and accepted risks

Public portfolio reporting should use fictional, sanitized, or aggregated evidence only.

## Testing Metrics

### Key Performance Indicators

| KPI | Initial Target |
|---|---:|
| Planned controls tested | 100% |
| Evidence requests fulfilled by agreed due date | At least 90% |
| Tests receiving independent review | 100% |
| Findings with assigned owner and target date | 100% |
| High-risk remediation validated by evidence before closure | 100% |
| Repeatable test workpapers with complete evidence references | 100% |

### Key Risk Indicators

| KRI | Escalation Indicator |
|---|---|
| Control cannot produce evidence | Any key control or increasing trend |
| Population cannot be reconciled | Any identity, privileged-access, vendor, or sensitive-data population |
| Repeat finding | Any High finding or recurring root cause |
| Overdue remediation | Any Critical or High item beyond approved date |
| Exception rate | Above defined tolerance or increasing trend |
| Owner disputes factual evidence | Unresolved dispute delaying conclusion |
| Control depends on one person | Any critical control without a trained backup |
| Testing causes unsafe or material operational interruption | Any occurrence |

## Risk and Control Traceability

Testing results should be linked through the following chain:

`Asset or Process → Risk → Control → Test Procedure → Evidence → Result → Finding → Remediation → Residual Risk`

The GRC Analyst should update the risk register and control matrix when testing identifies:

- A previously unknown risk
- A control that does not address the intended risk
- A material implementation gap
- A change in likelihood or impact
- An ineffective compensating control
- A completed remediation that reduces residual risk

## Review and Maintenance

This plan should be reviewed at least annually and after:

- A material system, vendor, service, or workflow change
- A significant incident or control failure
- A change to the risk register or control matrix
- A new contractual, privacy, or security requirement
- Repeated evidence-quality or population-reliability issues
- Testing that creates unexpected operational or safety friction

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. This plan demonstrates a risk-based approach to evidence collection and security control testing. It is not an audit opinion, legal advice, certification, or attestation of a real organization.
