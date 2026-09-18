# Human Factors Security Analysis

## Purpose

This document analyzes how people, work conditions, technology, procedures, and organizational expectations influence security behavior at Peachtree Logistics Group (PLG). It identifies where well-intentioned employees, drivers, independent couriers, managers, administrators, and third parties may be pushed toward errors or insecure workarounds by the way work is designed.

The purpose is not to label people as the weakest link. The purpose is to design security controls that employees can understand and follow while completing time-sensitive logistics work safely and reliably.

This document supports PLG's guiding principle:

> **Cybersecurity Made Human: secure behavior should be the practical path, not the difficult exception.**

## Supporting Documents

- `docs/01-project-charter.md`
- `docs/02-stakeholder-analysis.md`
- `docs/03-data-flow-diagrams.md`
- `docs/06-risk-register.md`
- `docs/07-security-control-matrix.md`
- `docs/08-role-based-access-control-model.md`
- `docs/09-iam-and-security-procedures.md`
- `docs/10-security-awareness-plan.md`
- `docs/11-incident-response-scenarios.md`
- `docs/12-evidence-and-control-testing-plan.md`
- `docs/13-kpis-and-kris.md`

## Analysis Objectives

The human factors analysis will:

1. Identify conditions that make security mistakes or workarounds more likely.
2. Distinguish individual mistakes from control-design and system-level failures.
3. Evaluate whether controls fit real office, warehouse, dispatch, delivery, medical-courier, and finance workflows.
4. Protect drivers and warehouse personnel from unsafe security expectations.
5. Reduce unnecessary cognitive load, ambiguity, interruptions, and duplicate work.
6. Improve reporting by creating clear and psychologically safe escalation paths.
7. Recommend controls that combine technology, process, training, and management support.
8. Define measures for security effectiveness and operational usability.

## Scope

### Workforce Groups

- Executive leadership
- IT and IAM administrators
- Customer service and operations personnel
- Warehouse personnel and managers
- Dispatchers
- PLG-employed drivers
- Independent couriers
- Medical-courier personnel
- Billing and finance personnel
- HR and Facilities personnel
- Vendor Management and Procurement
- Third-party support users

### Work Environments

- Corporate offices
- Warehouses and fulfillment areas
- Dispatch operations
- Vehicles and field locations
- Customer and recipient locations
- Remote and hybrid work locations
- Cloud and on-premises technology environments

### Security-Relevant Activities

- Authentication and MFA
- Customer order intake
- Access provisioning and approval
- Dispatch and route assignment
- Mobile delivery workflows
- Medical-delivery information handling
- Payment and vendor-detail changes
- Physical access and visitor management
- Incident recognition and reporting
- Vendor support and remote access
- Data sharing, retention, and disposal

## Methodology

This analysis uses a workflow-centered approach rather than assuming that security failures result only from carelessness or insufficient training.

The approach evaluates:

1. **Task:** What must the person accomplish?
2. **Environment:** Where and under what conditions is the work performed?
3. **Technology:** What systems, devices, and interfaces support the task?
4. **Information:** What must the person notice, remember, enter, verify, or protect?
5. **Pressure:** What time, workload, service, safety, or management pressures affect decisions?
6. **Coordination:** Which teams, vendors, clients, and recipients must interact?
7. **Control:** What security requirement is expected, and does it fit the workflow?
8. **Recovery:** Can the person report and correct an error without fear or unnecessary delay?

## Human Factors Categories

| Category | Description | PLG Example |
|---|---|---|
| Cognitive Load | The amount of information a person must process or remember | A dispatcher simultaneously monitors routes, driver messages, delivery windows, and exceptions |
| Time Pressure | Deadlines that encourage speed over verification | A medical delivery must be reassigned quickly while preserving minimum-necessary information |
| Interruption | A task is disrupted by alerts, calls, messages, or competing demands | A warehouse worker is interrupted during inventory confirmation and leaves a session open |
| Fatigue | Reduced attention caused by long shifts, irregular hours, or repeated tasks | A driver receives a convincing smishing message near the end of a route |
| Ambiguity | Instructions, ownership, or expected actions are unclear | A manager does not know who must remove a transferred employee's old permissions |
| Interface Design | A system makes the safe action difficult, hidden, or confusing | An MFA prompt provides too little context to distinguish an expected login from an attack |
| Workflow Friction | A control adds steps that conflict with operational needs | Repeated authentication interrupts dispatch during peak assignment periods |
| Social Pressure | Authority, urgency, or customer expectations influence behavior | A finance employee receives an urgent payment request appearing to come from an executive |
| Normalization of Deviance | Repeated exceptions become accepted as normal | Shared warehouse credentials continue because individual login is considered too slow |
| Psychological Safety | People feel safe reporting mistakes, uncertainty, or control problems | A courier reports a lost device immediately without fear of automatic punishment |
| Role Clarity | Responsibilities and decision authority are understood | A System Owner knows who approves, reviews, and removes vendor access |
| Skill and Knowledge | Personnel understand how to complete the task securely | A driver knows how to verify a recipient without exposing unnecessary shipment details |

## Workforce and Workflow Analysis

### Executive Leadership

#### Work Characteristics

- High email and meeting volume
- Broad access to sensitive information
- Frequent mobile and remote work
- Authority to request urgent operational or financial action
- Limited time for detailed security procedures

#### Human Factors Risks

- Executive impersonation and business email compromise
- Approval shortcuts caused by urgency or authority
- MFA fatigue during travel or high-volume work
- Sensitive information shared through convenient but unapproved channels
- Staff reluctance to challenge unusual executive requests

#### Recommended Design Responses

- Require independent verification for financial and high-risk requests regardless of seniority.
- Use assistants or delegated roles without sharing credentials.
- Provide concise executive-specific threat briefings.
- Configure strong MFA and risk-based access controls.
- Publicly reinforce that employees are expected to verify unusual executive requests.

### IT and IAM Administrators

#### Work Characteristics

- Elevated access across multiple systems
- Frequent interruptions and urgent support requests
- Small-team resource constraints
- Responsibility for cloud, on-premises, endpoint, identity, and vendor systems
- Pressure to restore service quickly

#### Human Factors Risks

- Use of privileged accounts for ordinary work
- Configuration errors caused by interruptions or incomplete change review
- Alert fatigue
- Excessive reliance on one knowledgeable administrator
- Delayed patching or access reviews during operational emergencies
- Informal vendor support access created to speed troubleshooting

#### Recommended Design Responses

- Separate standard and privileged accounts.
- Require change tickets and peer review for high-impact changes.
- Prioritize alerts based on risk and suppress known low-value noise.
- Cross-train administrators and maintain current runbooks.
- Use named, MFA-protected, time-limited vendor accounts.
- Schedule protected time for patching, access review, documentation, and recovery testing.

### Customer Service and Operations Personnel

#### Work Characteristics

- High-volume communications with clients
- Orders arriving through email, telephone, portal, or logistics platform
- Frequent schedule and address changes
- Pressure to respond quickly and maintain customer satisfaction

#### Human Factors Risks

- Trusting spoofed client requests
- Misdirecting customer or medical-delivery information
- Copying information into email or chat for convenience
- Collecting more sensitive information than necessary
- Bypassing verification when a caller appears urgent or frustrated

#### Recommended Design Responses

- Establish simple verification rules for delivery-address, contact, and account changes.
- Use structured intake forms with minimum necessary fields.
- Display data-classification and sharing guidance within the workflow.
- Provide an escalation path that does not penalize reasonable delay for verification.
- Reduce re-entry by integrating approved systems where practical.

### Warehouse Personnel and Managers

#### Work Characteristics

- Shared physical work areas
- Shift-based operations
- Repetitive and time-sensitive fulfillment tasks
- Gloves, noise, movement, equipment, and limited workstation availability
- Shared responsibility for inventory, staging, and visitor awareness

#### Human Factors Risks

- Shared credentials used to avoid login delays
- Unlocked sessions on shared workstations
- Tailgating during busy periods
- Passwords written near workstations
- Security alerts overlooked because they resemble ordinary operational errors
- Procedures that are difficult to read or follow in the work environment

#### Recommended Design Responses

- Provide fast individual authentication using appropriate secure methods.
- Configure short but operationally tested session controls.
- Position screens and devices to reduce exposure.
- Use concise visual job aids at the point of work.
- Make visitor badges and restricted areas easy to recognize.
- Deliver shift-based security briefings rather than relying only on email.
- Test controls with actual warehouse personnel before deployment.

### Dispatchers

#### Work Characteristics

- Continuous coordination across customers, drivers, couriers, warehouses, and recipients
- Rapid changes and exception handling
- Multiple screens, calls, messages, and platform alerts
- Responsibility for time-sensitive and medical deliveries

#### Human Factors Risks

- Sending excessive recipient information to resolve an urgent issue
- Assigning work to the wrong driver or courier identity
- Using personal messaging when the approved platform is slow or unavailable
- Missing suspicious activity among high alert volumes
- Pressuring drivers to interact with devices while moving

#### Recommended Design Responses

- Limit driver and courier views to current assignments and necessary information.
- Clearly distinguish PLG employees from independent couriers in the system.
- Provide a rapid identity-verification method for dispatch changes.
- Create approved outage and exception workflows.
- Require dispatchers to wait until drivers are safely stopped before requesting device interaction.
- Prioritize urgent security alerts separately from routine operational notifications.

### PLG-Employed Drivers

#### Work Characteristics

- Mobile work across uncontrolled environments
- Route, delivery-window, traffic, parking, customer, and safety pressures
- Use of mobile devices for navigation, delivery confirmation, signatures, and exception reporting
- Intermittent connectivity and limited ability to stop work immediately

#### Human Factors Risks

- Reading or responding to security prompts while driving
- Accepting an unexpected MFA prompt to clear the screen quickly
- Exposure of recipient or medical-delivery information through lock-screen notifications
- Delayed reporting of a lost device because the driver fears discipline or route disruption
- Using screenshots, personal messaging, or local photos to work around connectivity problems
- Device sharing during urgent delivery reassignment

#### Recommended Design Responses

- Design all authentication, training, and incident-reporting actions for parked use.
- Use long enough trusted sessions with risk-based reauthentication.
- Suppress sensitive content from lock-screen notifications.
- Minimize local data and automatically remove completed-assignment information.
- Provide one-tap reporting and dispatcher-assisted escalation.
- Create a supportive lost-device process focused on rapid containment.
- Test mobile controls under realistic lighting, connectivity, weather, and time-pressure conditions.

### Independent Couriers

#### Work Characteristics

- External relationship with limited PLG supervision
- Mixed device ownership and technical capability
- Temporary or assignment-based access
- Potential work for multiple organizations

#### Human Factors Risks

- Confusion between personal, other-client, and PLG information
- Unmanaged local storage or screenshots
- Continued access after assignment completion
- Inconsistent security training
- Informal sharing of devices or credentials
- Delayed incident reporting because PLG reporting channels are unfamiliar

#### Recommended Design Responses

- Use separate, named identities rather than shared or employee accounts.
- Limit access by assignment, time, and information need.
- Require a short pre-access security module and acknowledgment.
- Provide a mobile-friendly reporting channel.
- State device and data-deletion requirements in agreements.
- Automatically expire inactive or completed-assignment access.
- Avoid placing PLG internal procedures or unrelated data in the courier interface.

### Medical-Courier Personnel

#### Work Characteristics

- Time-sensitive delivery and chain-of-custody requirements
- Potential handling of PHI/ePHI or information that reveals a medical relationship
- Recipient verification and delivery exception management
- High consequence of disclosure or delivery to an unauthorized recipient

#### Human Factors Risks

- Oversharing information to resolve a delivery exception
- Confusing identity verification with collection of unnecessary information
- PHI/ePHI displayed in alerts or messages
- Pressure to complete a delivery despite uncertain recipient authority
- Retaining photos, signatures, or notes longer than necessary

#### Recommended Design Responses

- Show only minimum-necessary information at each workflow stage.
- Provide clear stop-and-escalate rules when recipient authority is uncertain.
- Use standardized chain-of-custody prompts.
- Avoid displaying sensitive medical details in notifications.
- Automatically restrict access after completion.
- Train through realistic delivery scenarios rather than legal terminology alone.
- Reinforce that meeting a delivery window does not override privacy or recipient-verification requirements.

### Billing and Finance Personnel

#### Work Characteristics

- High volume of invoices, payments, refunds, and vendor records
- Regular interaction with executives, clients, banks, and vendors
- Month-end and deadline pressure
- Authority to initiate or approve financial activity

#### Human Factors Risks

- Business email compromise exploiting urgency and authority
- Skipping independent verification near payment deadlines
- Segregation-of-duties conflicts in a small team
- Fatigue during high-volume reconciliation
- Trusting familiar formatting or message history instead of verifying the request

#### Recommended Design Responses

- Require callback verification using independently maintained contact information.
- Prevent one person from initiating and approving sensitive changes.
- Display warnings for bank-detail, refund, payroll, and vendor-master changes.
- Require a cooling-off or secondary review period for unusual changes where practical.
- Provide clear emergency-payment procedures that preserve verification requirements.
- Encourage employees to challenge requests regardless of apparent executive authority.

### HR and Facilities Personnel

#### Work Characteristics

- Responsibility for workforce, badge, visitor, and facility lifecycle events
- Handling of sensitive personnel information
- Need for close coordination with managers and IT
- Time-sensitive terminations and transfers

#### Human Factors Risks

- Ambiguity over who initiates or confirms access changes
- Delays when termination information is incomplete
- Different effective dates across HR, IT, payroll, and physical access
- Informal visitor exceptions during busy periods
- Excessive access to personnel records

#### Recommended Design Responses

- Use a single joiner-mover-leaver workflow with clear ownership and timestamps.
- Define emergency termination procedures.
- Require completion confirmation across logical access, badges, assets, and shared resources.
- Use standardized visitor and escort rules.
- Limit personnel-record access by role.

### Vendor Management and Third-Party Support

#### Work Characteristics

- Dependence on vendor-provided security information
- Contract deadlines and operational reliance
- Temporary technical support needs
- Limited visibility into vendor environments

#### Human Factors Risks

- Treating vendor questionnaires as a checkbox exercise
- Granting broad support access during outages
- Failing to remove access when support ends
- Assuming a known vendor contact is legitimate
- Accepting weak contract language to avoid procurement delay

#### Recommended Design Responses

- Tier vendors by operational and data risk.
- Focus due diligence on evidence relevant to PLG's use of the service.
- Require named, MFA-protected, time-limited support access.
- Maintain verified escalation contacts.
- Preapprove emergency vendor-access procedures.
- Track contract exceptions and residual risk visibly.

## Critical Workflow Analysis

### Customer Order Intake

| Human Factors Condition | Security Risk | Design Response |
|---|---|---|
| Orders arrive through multiple channels | Information is copied or stored inconsistently | Direct personnel to a primary intake workflow and defined system of record |
| Client urgency | Verification steps are skipped | Use quick verification prompts and manager escalation |
| Free-form email content | Excessive sensitive information is collected | Use structured fields and minimum-necessary guidance |
| Repetitive data entry | Entry errors or insecure copy-and-paste behavior | Integrate systems or provide validated templates |

### Review and Scheduling

| Human Factors Condition | Security Risk | Design Response |
|---|---|---|
| High order volume | Incorrect shipment or customer record selected | Use clear identifiers and confirmation before high-impact changes |
| Shared responsibilities | Ownership is unclear | Assign accountable roles for approval and exception handling |
| Multiple systems | Data becomes inconsistent | Define the authoritative record and reconciliation procedure |

### Dispatch and Assignment

| Human Factors Condition | Security Risk | Design Response |
|---|---|---|
| Rapid reassignment | Wrong driver or courier receives information | Confirm identity and show assignment-specific information |
| High message volume | Security alerts are missed | Separate security and operational alert priorities |
| Driver is moving | Unsafe device interaction | Delay prompts and require parked acknowledgment |
| Platform outage | Staff use personal messaging | Maintain an approved, minimum-data continuity method |

### Pickup and Transportation

| Human Factors Condition | Security Risk | Design Response |
|---|---|---|
| Intermittent connectivity | Screenshots or local notes are created | Provide secure offline functionality with controlled deletion |
| Public environments | Shoulder surfing or device theft | Use privacy-conscious displays, screen locks, and minimal notifications |
| Tight delivery windows | Verification is rushed | Use short, consistent verification steps and escalation support |

### Delivery Confirmation

| Human Factors Condition | Security Risk | Design Response |
|---|---|---|
| Recipient pressure | Delivery made to an unauthorized person | Provide clear refusal and escalation authority |
| Signature and photo capture | Excessive or unnecessary data is retained | Limit capture, access, and retention |
| Similar names or locations | Wrong recipient selected | Show distinguishing but minimum-necessary confirmation details |

### Billing and Retention

| Human Factors Condition | Security Risk | Design Response |
|---|---|---|
| Month-end workload | Verification and reconciliation are skipped | Protect review time and use workflow-enforced approvals |
| Historical data appears useful | Records are retained indefinitely | Automate approved retention and disposal rules |
| Executive urgency | Fraudulent payments bypass review | Require verification regardless of authority or urgency |

## Primary Human Factors Findings

### HF-01: Security Controls May Conflict With Driver Safety

**Observation:** Mobile authentication, incident reporting, delivery updates, and security prompts may occur while a driver is moving or under route pressure.

**Risk:** Drivers may interact unsafely, dismiss security prompts, share devices, or delay reporting.

**Root causes:** Mobile-first operations, limited safe stopping opportunities, rigid session settings, and response expectations that do not distinguish moving from parked work.

**Recommendation:** Design mobile controls around parked workflow points, suppress nonessential prompts while moving, use risk-based sessions, and provide dispatcher-assisted reporting.

**Priority:** High

### HF-02: Shared and Fast-Paced Work Encourages Credential Workarounds

**Observation:** Warehouse and dispatch teams may view individual authentication as slower than shared access during busy periods.

**Risk:** Reduced accountability, unauthorized access, inaccurate audit trails, and delayed offboarding.

**Root causes:** Limited workstations, slow login, poorly matched timeout settings, shift transitions, and production targets.

**Recommendation:** Provide fast individual authentication, sufficient devices, tested timeout settings, and supervisor reinforcement that production targets do not justify shared credentials.

**Priority:** High

### HF-03: Urgency and Authority Increase Social-Engineering Risk

**Observation:** Finance, operations, and customer-service personnel regularly receive urgent requests from executives, clients, recipients, and vendors.

**Risk:** Fraudulent payments, unauthorized routing changes, data disclosure, and account compromise.

**Root causes:** Service culture, fear of delaying leadership, inconsistent verification, and attacker use of realistic business context.

**Recommendation:** Establish verification rules that apply regardless of seniority, use separate trusted channels, and publicly authorize employees to pause unusual requests.

**Priority:** High

### HF-04: Multiple Communication Channels Increase Data Exposure

**Observation:** Orders, route changes, delivery exceptions, and support requests may move among email, Teams, telephone, logistics platforms, and personal mobile tools.

**Risk:** Misdirected information, uncontrolled copies, incomplete records, and use of unapproved channels.

**Root causes:** Platform limitations, outages, habit, client preference, and unclear systems of record.

**Recommendation:** Define primary channels, create approved continuity methods, minimize duplicate entry, and provide in-workflow guidance for sensitive information.

**Priority:** High

### HF-05: Reporting May Be Delayed by Fear or Uncertainty

**Observation:** Personnel may hesitate to report mistaken clicks, lost devices, misdirected messages, or security workarounds.

**Risk:** Threats remain active longer and potential data exposure grows.

**Root causes:** Fear of discipline, uncertainty about what qualifies as an incident, difficult reporting channels, and lack of feedback after reports.

**Recommendation:** Use a supportive reporting policy, simple mobile and email reporting, clear examples, receipt confirmation, and coaching that distinguishes mistakes from reckless or intentional misconduct.

**Priority:** High

### HF-06: Role Ambiguity Weakens Access Lifecycle Controls

**Observation:** HR, managers, IT, System Owners, and Vendor Management share responsibility for provisioning, transfers, reviews, and offboarding.

**Risk:** Excessive, conflicting, or orphaned access remains active.

**Root causes:** Informal notifications, inconsistent effective dates, unclear ownership, and separate logical and physical processes.

**Recommendation:** Implement one documented joiner-mover-leaver workflow with accountable roles, timestamps, escalation targets, and completion confirmation.

**Priority:** High

### HF-07: Independent Couriers Operate Across a Distinct Trust Boundary

**Observation:** Independent couriers perform delivery tasks but may use personally managed devices and work for multiple organizations.

**Risk:** PLG data may persist outside PLG control or remain accessible after an assignment.

**Root causes:** External employment relationship, inconsistent device controls, temporary access, and limited direct supervision.

**Recommendation:** Use separate courier identities, assignment-scoped data, automatic expiration, minimum device standards, concise training, and contractual reporting and deletion requirements.

**Priority:** High

### HF-08: Training Alone Cannot Correct Poor Control Design

**Observation:** Repeated mistakes may be treated as an awareness problem even when a system is confusing, slow, or incompatible with operational work.

**Risk:** Personnel receive repeated training while the root cause remains, reducing trust in the security program.

**Root causes:** Overreliance on annual training, limited frontline testing, and metrics focused on completion instead of behavior and usability.

**Recommendation:** Investigate repeated errors as potential design signals, test controls with users, and pair training with technical or workflow changes.

**Priority:** Moderate

### HF-09: Alert Volume Can Hide High-Risk Events

**Observation:** Dispatchers, IT personnel, managers, and mobile workers receive many operational and security notifications.

**Risk:** Important alerts are ignored, misunderstood, or dismissed through habituation.

**Root causes:** Poor prioritization, duplicate notifications, unclear wording, and excessive low-value alerts.

**Recommendation:** Tier alerts, eliminate duplicates, provide clear required actions, and monitor acknowledgment and outcome rather than delivery alone.

**Priority:** Moderate

### HF-10: Small-Team Constraints Create Concentration Risk

**Observation:** PLG has limited dedicated security personnel and may rely on a small number of administrators or managers.

**Risk:** Controls fail during absence, knowledge is undocumented, reviews lack independence, and urgent tasks displace preventive work.

**Root causes:** Staffing and budget limitations, broad roles, and informal knowledge transfer.

**Recommendation:** Cross-train personnel, document critical procedures, designate backups, automate repeatable tasks, and prioritize controls based on risk.

**Priority:** Moderate

## Human-Centered Control Design Standards

PLG should evaluate new and modified controls against the following standards.

### Clear

- Use plain language.
- State the expected action and reason.
- Avoid vague warnings such as “something went wrong.”
- Distinguish routine operational alerts from security events.

### Minimal

- Ask for only the information and actions necessary.
- Avoid duplicate entry and repeated approval.
- Reduce the number of decisions required under time pressure.

### Contextual

- Present guidance at the point of action.
- Tailor controls to the user's role, device, location, and task.
- Explain why an action is blocked and how to continue safely.

### Forgiving

- Allow personnel to report and recover from mistakes quickly.
- Provide safe cancellation, correction, and escalation options.
- Avoid irreversible actions without confirmation.

### Secure by Default

- Default to minimum access, approved channels, and limited retention.
- Do not depend on users remembering to select the secure option every time.

### Operationally Realistic

- Test controls during peak periods and real working conditions.
- Account for gloves, noise, motion, lighting, connectivity, shift work, and small screens.
- Provide continuity methods for outages and urgent exceptions.

### Measurable

- Record whether the control is used, bypassed, delayed, or misunderstood.
- Measure security outcome and operational impact.

## Error and Behavior Classification

PLG should distinguish among different causes before selecting corrective action.

| Classification | Description | Appropriate Response |
|---|---|---|
| Slip | Person intends the correct action but performs the wrong one | Improve interface, confirmation, layout, or interruption management |
| Lapse | Person forgets a step or loses place in a process | Use reminders, checklists, automation, and workflow state preservation |
| Knowledge Gap | Person does not know the correct action | Provide targeted instruction, demonstration, and accessible job aids |
| Ambiguous Procedure | Guidance permits multiple interpretations | Clarify ownership, decision rules, examples, and escalation |
| Workaround | Person intentionally bypasses a control to complete work | Investigate workflow friction, incentives, and control feasibility |
| Reckless Behavior | Person knowingly disregards a reasonable control and material risk | Apply coaching, access restriction, or formal accountability as appropriate |
| Malicious Behavior | Person intentionally causes harm or unauthorized access | Initiate incident response, preserve evidence, restrict access, and involve appropriate authorities |

Not every adverse action is a training problem. PLG should avoid using retraining as the default response when technology, workload, policy, or management incentives created the condition.

## Frontline Validation Plan

Before implementing a material control, PLG should conduct a limited pilot with representative users.

### Participant Groups

- Office employee
- Warehouse employee
- Dispatcher
- PLG-employed driver
- Independent courier representative
- Medical-courier user
- Finance user
- Manager or approver
- IT or IAM administrator

### Validation Questions

1. Can the user explain the security objective in their own words?
2. Can the user complete the task without unapproved assistance?
3. Does the control add time or steps that affect service delivery?
4. Does it create a safety concern?
5. Is the required action clear on the first attempt?
6. What happens during poor connectivity, device failure, or system outage?
7. Can the user correct a mistake?
8. Can the user report a problem quickly?
9. Does the control expose unnecessary information?
10. Is the control accessible to personnel with different abilities and levels of technical experience?

### Pilot Acceptance Criteria

- No unresolved safety conflict
- No requirement to interact while driving
- Security objective achieved in representative scenarios
- Instructions understood without extensive explanation
- Operational impact within approved tolerance
- Errors and exceptions produce clear recovery guidance
- Reporting and escalation function as designed
- Feedback and observed behavior are documented

## Recommendations Roadmap

### Immediate: 0–30 Days

- Publish a supportive incident-reporting statement.
- Confirm that drivers are never expected to interact with security prompts while moving.
- Identify and disable shared or orphaned accounts where safe to do so.
- Establish independent verification for payment and high-risk change requests.
- Define approved outage communication methods.
- Add a simple method for reporting control friction and safety concerns.

### Near Term: 31–60 Days

- Pilot RBAC roles with representative users.
- Test authentication and timeout settings in warehouses and field operations.
- Separate employee and independent-courier identities and access paths.
- Implement assignment-limited courier access.
- Review alerts for duplication, unclear wording, and low-value noise.
- Deliver role-based scenarios for dispatch, mobile, medical-delivery, and finance workflows.

### Medium Term: 61–90 Days

- Integrate joiner-mover-leaver notifications and completion tracking.
- Automate minimum-necessary access and post-assignment expiration where practical.
- Establish usability and friction metrics.
- Conduct a lost-device and medical-delivery tabletop exercise.
- Review recurring exceptions for control-design causes.
- Report human factors findings and remediation decisions to leadership.

## Human Factors Metrics

### Key Performance Indicators

| KPI | Initial Target |
|---|---:|
| Material controls piloted with representative users before broad deployment | 100% |
| High-risk workflows with an approved continuity procedure | 100% |
| Substantiated control-friction reports acknowledged within target | At least 95% |
| Required role-based training completed before sensitive access | 100% |
| Correct actions during role-specific exercises | At least 85% |
| Corrective actions addressing system or workflow causes, when identified | 100% |

### Key Risk Indicators

| KRI | Escalation Indicator |
|---|---|
| Credible control-related safety conflict | Any occurrence |
| Driver asked to interact with a device while moving | Any occurrence |
| Shared credential use | Any privileged or repeated operational occurrence |
| Repeated workaround involving sensitive information | Any recurring pattern |
| Delayed reporting caused by fear or unclear procedures | Any material incident or increasing trend |
| Multiple users making the same error | Indicates possible design or procedure failure |
| Authentication-related operational disruption | Repeated delivery, warehouse, or dispatch impact |
| Unresolved control-friction finding | Any High item or overdue remediation |

These metrics supplement KRI-15 and related measures in `docs/13-kpis-and-kris.md`.

## Governance

| Role | Responsibility |
|---|---|
| COO / Executive Sponsor | Reinforces that security, safety, and reliable operations are shared priorities |
| GRC Analyst | Coordinates human factors analysis, tracks findings, and challenges blame-only explanations |
| IT Director | Ensures technical controls are secure, usable, supportable, and monitored |
| HR Manager | Supports training, reporting culture, accessibility, and fair accountability |
| Operations Managers | Validate that controls fit actual workflows and service requirements |
| Dispatch and Safety Managers | Protect safe mobile work and validate field procedures |
| Medical Courier Program Manager | Validates minimum-necessary and recipient-verification workflows |
| Finance Manager | Validates payment controls under routine and urgent conditions |
| Employees, Drivers, and Couriers | Participate in testing, report problems, and explain real workflow conditions |

## Assessment Limitations

This analysis is based on the fictional PLG environment, defined workflows, stakeholder roles, risks, and proposed controls. A real assessment would require direct observation, interviews, surveys, help-desk and incident data, system testing, accessibility review, and representative user pilots.

Human behavior varies by individual and context. The analysis should not be used to stereotype workforce groups or predict individual misconduct.

## Review and Maintenance

The GRC Analyst should coordinate review of this document at least annually and after:

- A material security incident or near miss
- A reported safety conflict
- Repeated user error or workaround
- A new or significantly changed system
- A change to mobile, warehouse, dispatch, finance, or medical-delivery workflows
- A material change in staffing, workload, vendor relationships, or service requirements
- Evidence that a security metric is encouraging underreporting or undesirable behavior

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. This document demonstrates a human-centered security analysis and does not represent an ergonomic, clinical, legal, regulatory, or employment assessment of a real organization.
