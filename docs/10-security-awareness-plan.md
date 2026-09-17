# Security Awareness and Training Plan

## Purpose

This plan establishes a role-based security awareness and training program for Peachtree Logistics Group. The program is designed to help employees, managers, drivers, independent couriers, administrators, and third parties make secure decisions during real PLG workflows.

The program supports PLG's human-centered security objective: controls must be understandable, practical, measurable, and compatible with time-sensitive logistics work.

This plan supports:

- `docs/06-risk-register.md`
- `docs/07-security-control-matrix.md`
- `docs/08-role-based-access-control-model.md`
- `docs/09-iam-and-security-procedures.md`

## Program Theme

> **Secure the Route: Protect the Data. Protect the Delivery.**

The theme connects cybersecurity to PLG's operational mission. Security is presented as part of reliable delivery—not as a separate compliance exercise.

## Program Objectives

The program will:

1. Help personnel recognize and report phishing, credential theft, suspicious access, data exposure, and device incidents.
2. Reinforce MFA, password, access, and account-lifecycle requirements.
3. Teach personnel how to handle Internal, Confidential, and Restricted information.
4. Reduce sensitive information shared through unapproved email, chat, file-sharing, and mobile channels.
5. Teach drivers and couriers to use PLG applications securely at safe workflow points.
6. Reinforce minimum-necessary handling of medical-delivery information and applicable PHI/ePHI.
7. Help finance personnel recognize payment fraud and unauthorized changes.
8. Improve vendor, contractor, and independent-courier security behavior.
9. Create a reporting culture that rewards early reporting and does not punish good-faith mistakes.
10. Measure whether training changes behavior and reduces risk.

## Guiding Principles

### Role Relevant

Training must reflect the decisions each audience actually makes. Warehouse personnel, drivers, administrators, finance staff, and executives should not receive identical content.

### Short and Practical

Use concise modules, realistic examples, demonstrations, job aids, and scenario-based practice. Avoid unnecessary technical jargon.

### Available at the Point of Need

Provide instructions where work occurs—for example, mobile reporting guidance for drivers, recipient-verification prompts during delivery, and phishing-reporting tools within email.

### Safe by Design

Drivers must not be expected to read training, authenticate, report incidents, or interact with applications while actively driving. Training must reinforce safe workflow points.

### Supportive Reporting Culture

Personnel should report suspicious messages, mistaken clicks, lost devices, misdirected information, and control conflicts immediately. Good-faith reporting should be encouraged rather than hidden through fear of automatic punishment.

### Accessible

Materials should use plain language, readable formatting, captions, transcripts, accessible digital formats, and alternative delivery methods where needed.

### Measurable

Completion alone is not evidence of reduced risk. PLG should measure reporting, behavior, control adoption, repeat failures, exceptions, and operational friction.

## Audience Groups

| Audience | Key Responsibilities | Primary Training Needs |
|---|---|---|
| All Employees | Protect credentials, information, devices, and facilities; report suspicious activity | Phishing, MFA, data handling, reporting, physical security, acceptable use |
| Executive Leadership | Set expectations, approve resources, own risk decisions, and lead by example | Targeted attacks, executive impersonation, risk oversight, incident decisions |
| IT and IAM Administrators | Manage identities, systems, logs, endpoints, backups, and privileged access | Secure administration, privileged accounts, logging, incident containment, change control |
| Customer Service and Operations | Receive orders, communicate with clients, schedule work, and manage exceptions | Secure intake, identity verification, email safety, approved channels, data minimization |
| Warehouse Personnel and Managers | Manage inventory, fulfillment, staging, and facility workflows | WMS access, shared-workstation security, badges, visitors, devices, incident reporting |
| Dispatchers | Assign routes, monitor drivers, resolve exceptions, and handle recipient information | Minimum-necessary sharing, courier access, safe driver communication, urgent escalation |
| PLG-Employed Drivers | Complete deliveries using PLG-managed devices and applications | Mobile security, safe workflow points, recipient verification, lost devices, reporting |
| Independent Couriers | Complete approved assignments using external identities and approved devices | Assignment-limited access, device requirements, data deletion, incident reporting |
| Medical Courier Personnel | Coordinate and perform medical-delivery services | Applicable PHI/ePHI, minimum necessary, chain of custody, verification, incident escalation |
| Billing and Finance | Invoice clients, process payments, reconcile records, and manage financial changes | Payment fraud, impersonation, segregation of duties, callback verification, sensitive data |
| HR and Facilities | Manage workforce and physical-access lifecycles | Joiner-mover-leaver events, badges, visitors, personnel data, urgent termination coordination |
| Vendor Management / Procurement | Select, contract with, monitor, and terminate vendors | Due diligence, contract requirements, support access, incident notification, exit planning |
| Third-Party Support Users | Perform approved technical work | Named accounts, MFA, time-limited access, monitoring, data restrictions, reporting |

## Core Curriculum

### Module 1: Security Responsibilities and Reporting

**Audience:** All personnel

**Learning objectives:**

- Explain why security supports reliable logistics operations.
- Identify common security events and reporting channels.
- Report suspected incidents quickly, even when facts are incomplete.
- Understand protection against retaliation for good-faith reporting.

**Topics:**

- Individual security responsibilities
- What constitutes suspicious activity
- How and when to report
- Immediate reporting for mistaken clicks, lost devices, unauthorized access, and misdirected information
- What information to include in a report

### Module 2: Phishing, Smishing, and Impersonation

**Audience:** All personnel, with enhanced modules for executives, finance, dispatch, and customer service

**Learning objectives:**

- Recognize suspicious email, text, voice, QR-code, login, and collaboration messages.
- Inspect urgency, sender identity, links, attachments, requests, and context.
- Use the approved reporting method rather than forwarding suspicious content.
- Verify unusual requests through a separate trusted channel.

**Scenarios:**

- Fake Microsoft 365 password-expiration message
- Executive request for urgent payment or gift cards
- Client request to change a delivery address
- Driver text containing a malicious route link
- Vendor support request for administrator access
- Fake toll, payroll, benefits, or package message

### Module 3: Credentials, MFA, and Access

**Audience:** All personnel; enhanced content for managers and administrators

**Learning objectives:**

- Protect passwords, MFA prompts, recovery codes, tokens, and badges.
- Reject unexpected MFA prompts and report them.
- Never share accounts or approve another person's access.
- Understand why access changes when roles or assignments change.

**Topics:**

- Password and authenticator protection
- MFA fatigue and push-bombing
- Shared-account risks
- Least privilege
- Temporary and assignment-based access
- Joiner-mover-leaver responsibilities

### Module 4: Data Classification and Approved Sharing

**Audience:** All personnel

**Learning objectives:**

- Distinguish Public, Internal, Confidential, and Restricted information.
- Select an approved storage and communication channel.
- Avoid unnecessary copies, downloads, forwarding, and external sharing.
- Report misdirected or overshared information.

**Topics:**

- Customer, recipient, shipment, employee, financial, and vendor information
- Email and Microsoft 365 sharing
- Systems of record
- Clean-desk and secure-printing practices
- Retention and secure disposal

### Module 5: Mobile Device, BYOD, and Field Security

**Audience:** Drivers, independent couriers, dispatchers, managers, and mobile workers

**Learning objectives:**

- Secure PLG-issued and approved personal devices.
- Use applications only at safe workflow points.
- Protect route, location, recipient, and proof-of-delivery information.
- Report lost, stolen, replaced, or compromised devices immediately.

**Topics:**

- Screen lock, encryption, updates, and approved applications
- Notification privacy
- Public Wi-Fi and charging risks
- Local photos, screenshots, downloads, caches, and message history
- Session revocation and remote protection
- No application interaction while actively driving

### Module 6: Medical-Delivery Information

**Audience:** Medical Courier Program Manager, applicable customer service and operations staff, dispatchers, drivers, couriers, compliance, and IT

**Learning objectives:**

- Recognize when medical-delivery information may include PHI/ePHI.
- Apply minimum-necessary access and disclosure.
- Verify authorized recipients.
- Protect chain-of-custody and proof-of-delivery information.
- Escalate suspected privacy incidents immediately.

**Topics:**

- Applicable PHI/ePHI versus general shipment information
- Role- and assignment-limited access
- Approved communication channels
- Recipient verification
- Misdirected information
- Lost devices and exposed notifications
- Retention and disposal

Training does not independently determine HIPAA applicability. Qualified legal or privacy review is required.

### Module 7: Payment and Financial Fraud

**Audience:** Finance, billing, executives, customer service, vendor management, and relevant managers

**Learning objectives:**

- Recognize business email compromise and payment-redirection fraud.
- Verify bank, refund, invoice, payroll, and payment-instruction changes.
- Apply segregation of duties and callback verification.
- Escalate suspicious transactions before processing.

**Scenarios:**

- Executive impersonation requesting urgent payment
- Vendor bank-account change
- Client overpayment and refund request
- Fraudulent invoice attachment
- MFA request during a payment change

### Module 8: Warehouse and Physical Security

**Audience:** Warehouse personnel, managers, facilities, IT, drivers, and applicable vendors

**Learning objectives:**

- Protect badges, keys, workstations, network areas, devices, records, and staged shipments.
- Challenge or report unauthorized entry according to safety procedures.
- Prevent tailgating and visitor-policy bypass.
- Secure shared workstations and report unusual system behavior.

### Module 9: Vendor and Third-Party Security

**Audience:** Vendor Management, System Owners, IT, Finance, Legal or Compliance, and vendor sponsors

**Learning objectives:**

- Apply vendor tiering and due diligence.
- Define security and incident-notification obligations.
- Restrict and monitor vendor access.
- Remove access and recover information when work or contracts end.

### Module 10: Secure Administration

**Audience:** IT, IAM administrators, system administrators, security personnel, and approved support users

**Learning objectives:**

- Use separate standard and privileged accounts.
- Apply MFA and secure administration methods.
- Protect secrets, service accounts, logs, and backups.
- Recognize and escalate suspicious administrative activity.
- Preserve evidence during incident response.

### Module 11: Manager and Approver Responsibilities

**Audience:** All managers, System Owners, Data Owners, and approvers

**Learning objectives:**

- Select appropriate RBAC roles.
- Validate business need and segregation of duties.
- Initiate timely role and termination changes.
- Complete access reviews accurately.
- Identify workarounds and control friction.
- Escalate exceptions rather than informally bypassing controls.

## Role-Based Training Matrix

| Audience | Required Modules | Delivery Method | Frequency | Owner |
|---|---|---|---|---|
| All Employees | 1, 2, 3, 4, 8 | Instructor-led or online orientation; microlearning; exercises | At hire; annually; periodic refreshers | HR and GRC |
| Executive Leadership | 1, 2, 3, 7, 11 | Executive briefing and tabletop exercise | Annually; targeted updates | GRC and Incident Lead |
| IT / IAM Administrators | 1, 2, 3, 4, 9, 10, 11 | Technical workshop, lab, and tabletop | At role assignment; annually; after major change | IT Director |
| Customer Service / Operations | 1, 2, 3, 4, 6 as applicable | Scenario workshop and job aids | At hire; annually; quarterly microlearning | Operations Manager |
| Warehouse Personnel | 1, 2, 3, 4, 8 | Shift briefing, demonstration, and job aids | At hire; annually; periodic toolbox talks | Warehouse Manager |
| Dispatchers | 1, 2, 3, 4, 5, 6, 11 | Workflow simulation and job aids | At hire; annually; quarterly refreshers | Dispatch Manager |
| PLG-Employed Drivers | 1, 2, 3, 4, 5, 6 as applicable | Mobile-friendly module and parked demonstration | Before access; annually; periodic refreshers | Dispatch / Safety |
| Independent Couriers | 1, 2, 3, 4, 5, 6 as applicable | Short pre-access module and acknowledgment | Before first assignment; annual renewal | Dispatch Manager |
| Medical Courier Personnel | 1, 3, 4, 5, 6 | Scenario training and practical verification | Before access; annually; after material change | Medical Courier Manager |
| Billing / Finance | 1, 2, 3, 4, 7, 11 | Fraud scenarios, verification exercise, and job aids | At hire; annually; quarterly refreshers | Finance Manager |
| HR / Facilities | 1, 2, 3, 4, 8, 11 | Process workshop and checklist practice | At hire; annually | HR and Facilities |
| Vendor Management | 1, 2, 3, 4, 7, 9, 11 | Vendor-risk workshop and contract scenarios | At role assignment; annually | Procurement and GRC |
| Third-Party Support Users | 1, 3, 4, 9, 10 as applicable | Pre-access briefing and acknowledgment | Before access; contract renewal | Vendor Sponsor and IT |

## Training Lifecycle

### Before Access

- Complete required foundational and role-specific training.
- Acknowledge relevant policies and procedures.
- Complete additional training before receiving privileged, financial, medical-delivery, courier, vendor, or Restricted-data access.

### Annual Training

- Refresh core responsibilities and current threat patterns.
- Include role-specific scenarios rather than repeating only generic content.
- Require a knowledge check or practical exercise.

### Event-Driven Training

Provide targeted training after:

- A significant incident or near miss
- Repeated simulation failures
- A control or audit finding
- A material role, system, workflow, vendor, or policy change
- Evidence of unsafe workarounds
- Changes in applicable contractual, privacy, or security obligations

### Microlearning

Use short communications throughout the year, such as:

- One-minute reporting demonstrations
- Shift-start security reminders
- Dispatch job aids
- Mobile-device reminders
- Manager approval tips
- Finance verification prompts
- Lessons learned from sanitized incidents

## Simulation and Exercise Plan

| Exercise | Audience | Frequency | Success Measure |
|---|---|---|---|
| Phishing simulation | Employees with email access | Quarterly | Reporting increases while repeat interaction decreases |
| Smishing / malicious route-link discussion | Drivers, couriers, dispatchers | Semiannual | Personnel select the approved reporting and verification process |
| Lost-device drill | Drivers, managers, IT, Security | Annual | Report, session revocation, assessment, and escalation occur within targets |
| Unauthorized-recipient scenario | Drivers, couriers, medical program staff | Annual | Personnel refuse improper disclosure and follow escalation procedures |
| Payment-change verification exercise | Finance, billing, executives, vendor management | Semiannual | Independent verification and segregation-of-duties steps are completed |
| Tailgating and visitor scenario | Warehouse and office personnel | Annual | Personnel follow safe challenge or reporting procedures |
| Compromised-account tabletop | IT, Security, HR, Legal/Compliance, operations | Annual | Containment, evidence, impact analysis, and communications are coordinated |
| Vendor-outage tabletop | IT, operations, vendor management, leadership | Annual | Manual workarounds, escalation, recovery, and client communications are tested |

Simulations should educate and measure behavior. They should not use humiliation, public ranking, deceptive collection of personal credentials, or punishment as the default response.

## Reporting and Reinforcement

PLG should provide:

- A clearly labeled phishing-reporting function in email where supported
- A security contact and backup reporting method
- A mobile-friendly method for drivers and couriers
- A manager escalation path
- Emergency instructions for suspected PHI/ePHI, payment, privileged-account, or device incidents
- Confirmation that reports were received
- Feedback and lessons learned when appropriate

Personnel should never send passwords, MFA codes, full payment details, or unnecessary sensitive information within a report.

## Training Metrics

### Key Performance Indicators

| KPI | Initial Target |
|---|---:|
| Foundational training completed by deadline | At least 95% |
| Required role-specific training completed before access | 100% |
| Managers completing access-review training | At least 95% |
| Independent couriers completing required training before first assignment | 100% |
| Phishing reports acknowledged within the defined service target | At least 95% |
| Correct actions during role-specific exercises | At least 85% |

### Key Risk Indicators

| KRI | Escalation Indicator |
|---|---|
| Repeat phishing simulation interaction | Increasing trend or repeated failure by the same population |
| Actual credentials submitted during simulation or incident | Any occurrence requiring immediate review |
| Unreported lost or stolen device | Any delayed report involving PLG access |
| Courier access granted before training | Any occurrence |
| Repeated sensitive-information sharing through unapproved channels | Increasing trend or recurring department |
| Driver reports of unsafe authentication or application prompts | Any credible safety conflict; repeated reports require design review |
| Overdue role-specific training for privileged or Restricted-data users | Any overdue user retaining access |
| Medical-delivery or payment-handling errors | Any material event or repeated near miss |

Targets should be reviewed after baseline data is available. Metrics must not be manipulated by discouraging reports or excluding difficult populations.

## Corrective and Remedial Training

Remedial training should:

1. Be based on the actual behavior or control gap.
2. Occur promptly after a mistake, event, or repeated knowledge gap.
3. Use coaching and practical demonstration.
4. Distinguish an honest mistake from deliberate or reckless misconduct.
5. Address control design when several people make the same error.
6. Be documented without collecting unnecessary sensitive details.

Repeated failure may require manager involvement, access restriction, process redesign, or formal corrective action according to HR policy.

## Program Evidence

PLG should retain:

- Approved training plan and curriculum
- Audience and role mappings
- Training assignments
- Completion and acknowledgment records
- Knowledge-check results
- Simulation design and aggregate results
- Exercise attendance and after-action reports
- Remedial-training records
- Job aids and communications
- Accessibility accommodations
- Feedback and program-improvement decisions
- Evidence that required training preceded privileged, courier, vendor, financial, or Restricted-data access

## Governance

| Role | Responsibility |
|---|---|
| COO / Executive Sponsor | Reinforces expectations and approves resources |
| GRC Analyst | Coordinates the program, maps content to risks, and reports effectiveness |
| HR Manager | Assigns foundational training and maintains workforce completion records |
| IT Director | Approves technical and administrator content |
| Department Managers | Validate role-specific content and ensure participation |
| Dispatch and Safety Managers | Validate driver and courier usability and safety |
| Medical Courier Program Manager | Validates medical-delivery scenarios and minimum-necessary practices |
| Finance Manager | Validates payment-fraud and financial-verification content |
| Vendor Management | Ensures third-party training and acknowledgment requirements |
| Employees and Contractors | Complete training, apply procedures, provide feedback, and report suspicious activity |

## 90-Day Rollout

### Days 0–30: Foundation

- Approve the program charter, theme, audiences, and reporting channels.
- Assign foundational training.
- Deliver phishing and credential-protection training.
- Train privileged users and high-risk finance, medical-delivery, dispatch, and courier populations.
- Establish baseline completion and reporting metrics.

### Days 31–60: Role-Based Expansion

- Deliver workflow-specific modules.
- Publish driver, dispatcher, warehouse, finance, and manager job aids.
- Launch the first phishing exercise.
- Conduct a lost-device and account-compromise drill.
- Gather frontline feedback and identify control friction.

### Days 61–90: Measurement and Improvement

- Review completion, simulation, reporting, exception, and incident data.
- Provide targeted coaching.
- Correct confusing content and unsafe or impractical procedures.
- Report results and recommended improvements to leadership.
- Approve the next quarterly awareness cycle.

## Risk and Control Traceability

This plan primarily supports:

- Risks R-01, R-04, R-05, R-06, R-10, R-11, R-13, and R-14
- Controls CTL-07 through CTL-10, CTL-16, CTL-19 through CTL-22, and CTL-24

## Review and Maintenance

The program must be reviewed at least annually and after:

- Significant incidents or near misses
- Material changes to systems, workflows, vendors, or services
- Repeated simulation or control failures
- Changes to applicable client, contractual, privacy, or security requirements
- Frontline reports that a control is unsafe, unclear, or impractical

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. This plan demonstrates a proposed human-centered security awareness program and does not represent training delivered by a real organization.
