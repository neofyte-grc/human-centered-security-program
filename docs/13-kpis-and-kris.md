# Security KPIs and KRIs

## Purpose

This document establishes the Key Performance Indicators (KPIs) and Key Risk Indicators (KRIs) Peachtree Logistics Group (PLG) will use to measure security-control performance, identify increasing risk, support management decisions, and demonstrate whether the security program is reducing risk without unnecessarily disrupting logistics operations.

The measurement program is designed for PLG's mixed cloud and on-premises environment, approximately 225-person workforce, warehouse operations, last-mile delivery services, medical-courier activities, freight brokerage, independent couriers, and third-party technology relationships.

This document supports:

- `docs/05-risk-assessment-methodology.md`
- `docs/06-risk-register.md`
- `docs/07-security-control-matrix.md`
- `docs/08-role-based-access-control-model.md`
- `docs/09-iam-and-security-procedures.md`
- `docs/10-security-awareness-plan.md`
- `docs/11-incident-response-scenarios.md`
- `docs/12-evidence-and-control-testing-plan.md`

## Measurement Objectives

The KPI and KRI program will:

1. Measure whether key controls are implemented and operating as intended.
2. Identify trends that may increase the likelihood or impact of security incidents.
3. Connect operational data to the risk register and control matrix.
4. Support timely escalation and remediation decisions.
5. Track whether remediation reduces residual risk.
6. Identify controls that create unsafe, confusing, or impractical workflows.
7. Provide useful information to executives, managers, control owners, and operational teams.
8. Demonstrate continuous improvement through reproducible evidence.

## KPI and KRI Definitions

### Key Performance Indicator

A KPI measures whether a security process or control is performing as intended.

Examples include:

- Percentage of required accounts protected by MFA
- Percentage of terminated-user access removed within target
- Percentage of required training completed on time
- Percentage of access reviews completed by the deadline

### Key Risk Indicator

A KRI measures exposure, adverse conditions, exceptions, or trends that may indicate increasing risk.

Examples include:

- Number of orphaned accounts
- Number of overdue critical vulnerabilities
- Number of lost devices reported after the required timeframe
- Number of vendor accounts without a current business owner

### Relationship Between KPIs and KRIs

A KPI may appear healthy while a related KRI reveals hidden exposure. For example, PLG may report 98% MFA enrollment while the remaining 2% includes privileged administrators. Metrics must therefore be interpreted together, with attention to the affected population and risk.

## Measurement Principles

- **Risk aligned:** Every metric must support a defined risk, control objective, or business decision.
- **Actionable:** A metric must have an owner and a defined response when thresholds are exceeded.
- **Reproducible:** Another qualified reviewer should be able to calculate the same result from the same source data.
- **Timely:** Data must be collected frequently enough to support intervention.
- **Balanced:** Metrics should measure security effectiveness and operational impact.
- **Population aware:** Results must not hide high-risk exceptions within broad averages.
- **Trend focused:** Direction over time is often more useful than a single measurement.
- **Resistant to gaming:** Targets must not encourage personnel to suppress reports, avoid escalation, or exclude difficult populations.
- **Privacy preserving:** Reports should use the minimum necessary personal or sensitive information.
- **Reviewable:** Sources, calculations, assumptions, exclusions, and changes must be documented.

## Metric Status Thresholds

| Status | Meaning | Required Response |
|---|---|---|
| Green | Performance is within target or risk exposure is within tolerance | Continue monitoring and normal control operation |
| Amber | Performance is below target or risk exposure is approaching tolerance | Control owner investigates, documents cause, and creates a corrective action when needed |
| Red | Performance materially misses target or risk exceeds tolerance | Prompt escalation to the accountable manager, GRC Analyst, and appropriate executive or risk owner |
| Gray | Data is unavailable, incomplete, unreliable, or not yet established | Resolve the measurement gap; do not treat missing data as acceptable performance |

Initial thresholds are proposed baselines. PLG should refine them after collecting at least one full reporting cycle and documenting normal operational variation.

## Security KPI Register

### KPI-01: MFA Coverage

| Field | Definition |
|---|---|
| Objective | Measure whether required identities are protected by approved MFA |
| Formula | `(Required accounts with compliant MFA ÷ Total accounts requiring MFA) × 100` |
| Target | 100% for privileged, finance, vendor, remote-access, and medical-delivery roles; at least 98% overall |
| Green | Meets target |
| Amber | 95%–97.9% overall, or one noncompliant high-risk account corrected promptly |
| Red | Below 95% overall, or any unexplained privileged or high-risk account without MFA |
| Source | Identity-provider registration and policy reports; account inventory |
| Frequency | Weekly operational review; monthly reporting |
| Owner | IAM Administrator |
| Related Areas | Account compromise, privileged access, vendor access, Microsoft 365 |

### KPI-02: Timely User Provisioning

| Field | Definition |
|---|---|
| Objective | Measure whether new accounts are approved, role-aligned, and available by the authorized start date |
| Formula | `(Compliant provisioning events completed within target ÷ Total provisioning events) × 100` |
| Target | At least 95% |
| Green | At least 95% |
| Amber | 90%–94.9% |
| Red | Below 90% or any unapproved sensitive access |
| Source | HR records, access requests, approval records, IAM logs |
| Frequency | Monthly |
| Owner | HR Manager and IAM Administrator |
| Related Areas | Joiner process, RBAC, least privilege |

### KPI-03: Timely Role-Change Completion

| Field | Definition |
|---|---|
| Objective | Measure whether obsolete access is removed and new access is approved after transfers or duty changes |
| Formula | `(Role changes completed within target ÷ Total role-change events) × 100` |
| Target | At least 95%; 100% for privileged or conflicting access |
| Green | Meets target |
| Amber | 90%–94.9% or one promptly corrected low-risk delay |
| Red | Below 90% or any unresolved privileged or segregation-of-duties conflict |
| Source | HR transfer report, access tickets, role assignments |
| Frequency | Monthly |
| Owner | Department Managers and IAM Administrator |
| Related Areas | Mover process, excessive access, segregation of duties |

### KPI-04: Timely Offboarding

| Field | Definition |
|---|---|
| Objective | Measure whether logical and physical access is removed within the approved termination target |
| Formula | `(Offboarding events completed within target ÷ Total offboarding events) × 100` |
| Target | 100% for involuntary and high-risk separations; at least 98% overall |
| Green | Meets target |
| Amber | 95%–97.9% overall with no post-separation activity |
| Red | Below 95%, any active access after a high-risk separation, or unexplained post-separation activity |
| Source | HR termination report, IAM logs, application accounts, badge system, asset records |
| Frequency | Weekly operational review; monthly reporting |
| Owner | HR Manager, IAM Administrator, and Facilities |
| Related Areas | Orphaned accounts, unauthorized access, physical security |

### KPI-05: Access Review Completion

| Field | Definition |
|---|---|
| Objective | Measure whether required access certifications are completed accurately and on time |
| Formula | `(Access reviews completed and approved by deadline ÷ Total required access reviews) × 100` |
| Target | 100% |
| Green | 100% |
| Amber | 95%–99.9%, with overdue items completed within the escalation window |
| Red | Below 95% or any overdue high-risk system review |
| Source | Access-certification records, reviewer decisions, remediation tickets |
| Frequency | Quarterly |
| Owner | System Owners and Data Owners |
| Related Areas | Least privilege, privileged access, vendor access |

### KPI-06: Access Review Remediation

| Field | Definition |
|---|---|
| Objective | Measure whether access-removal and modification decisions are implemented promptly |
| Formula | `(Review findings remediated within target ÷ Total review findings due) × 100` |
| Target | At least 95%; 100% for privileged access |
| Green | Meets target |
| Amber | 90%–94.9% |
| Red | Below 90% or any overdue privileged-access removal |
| Source | Certification decisions, IAM and application change logs, tickets |
| Frequency | Monthly and after each review cycle |
| Owner | IAM Administrator and System Owners |
| Related Areas | Excessive access, remediation effectiveness |

### KPI-07: Managed and Compliant Device Coverage

| Field | Definition |
|---|---|
| Objective | Measure whether in-scope endpoints and mobile devices meet required security standards |
| Formula | `(Compliant managed devices ÷ Total devices requiring management) × 100` |
| Target | At least 95%; 100% for privileged and Restricted-data access |
| Green | Meets target |
| Amber | 90%–94.9% with documented remediation |
| Red | Below 90% or any unmanaged device accessing privileged or Restricted data without an approved control |
| Source | Endpoint management, mobile-device management, asset inventory, delivery-platform device records |
| Frequency | Weekly operational review; monthly reporting |
| Owner | IT Operations |
| Related Areas | Driver devices, BYOD, endpoint security, data exposure |

### KPI-08: Critical Vulnerability Remediation

| Field | Definition |
|---|---|
| Objective | Measure whether critical and high-risk vulnerabilities are resolved within PLG's approved targets |
| Formula | `(Applicable vulnerabilities remediated within target ÷ Total applicable vulnerabilities due) × 100` |
| Target | At least 95%; 100% for actively exploited or emergency vulnerabilities unless an approved exception exists |
| Green | Meets target |
| Amber | 90%–94.9% or limited approved exceptions |
| Red | Below 90%, an actively exploited vulnerability overdue, or unsupported critical exposure without compensating controls |
| Source | Vulnerability scanner, patch platform, endpoint-management system, remediation tickets |
| Frequency | Weekly operational review; monthly reporting |
| Owner | IT Director |
| Related Areas | WMS, endpoints, malware, ransomware |

### KPI-09: Security Training Completion

| Field | Definition |
|---|---|
| Objective | Measure timely completion of foundational and role-based security training |
| Formula | `(Personnel completing required training by deadline ÷ Total personnel assigned training) × 100` |
| Target | At least 95% overall; 100% before privileged, courier, vendor, financial, or Restricted-data access |
| Green | Meets target |
| Amber | 90%–94.9% overall with no sensitive access granted early |
| Red | Below 90% or any sensitive access granted before required training |
| Source | Learning-management records, HR population, access records |
| Frequency | Monthly |
| Owner | HR Manager and GRC Analyst |
| Related Areas | Awareness, role readiness, human risk |

### KPI-10: Phishing Reporting Rate

| Field | Definition |
|---|---|
| Objective | Measure whether personnel recognize and report simulated or confirmed phishing attempts |
| Formula | `(Personnel who correctly report the message ÷ Personnel who received the message) × 100` |
| Target | Baseline during first cycle; then sustained quarterly improvement with a proposed target of at least 30% |
| Green | Meets target and trend is stable or improving |
| Amber | Below target or declining for one cycle |
| Red | Material decline across two cycles or low reporting combined with increasing interaction |
| Source | Phishing platform, email-reporting tool, incident records |
| Frequency | Quarterly |
| Owner | GRC Analyst |
| Related Areas | Phishing, account compromise, awareness effectiveness |

The reporting rate should not be interpreted alone. A high reporting rate with a high credential-submission rate still indicates significant risk.

### KPI-11: Incident Response Target Achievement

| Field | Definition |
|---|---|
| Objective | Measure whether material incidents meet defined assignment, containment, communication, and documentation targets |
| Formula | `(Applicable incident milestones achieved within target ÷ Total incident milestones due) × 100` |
| Target | At least 95% |
| Green | At least 95% |
| Amber | 85%–94.9% |
| Red | Below 85% or any missed milestone materially increasing impact |
| Source | Incident records, identity logs, endpoint tools, response timeline |
| Frequency | Monthly and after every SEV-1 or SEV-2 incident |
| Owner | Incident Commander and IT / Security Lead |
| Related Areas | Incident response, containment, evidence preservation |

### KPI-12: Backup and Restore Success

| Field | Definition |
|---|---|
| Objective | Measure whether critical backups complete successfully and can be restored |
| Formula | `(Successful backup or restore activities ÷ Total scheduled activities) × 100` |
| Target | At least 98% successful backup jobs; 100% completion of planned critical restore tests |
| Green | Meets target |
| Amber | Backup success of 95%–97.9% or a delayed noncritical restore test |
| Red | Below 95%, a failed critical restore test, or no valid recovery point for a critical system |
| Source | Backup platform, job logs, restore-test records |
| Frequency | Daily operational monitoring; monthly reporting; restore testing at least annually |
| Owner | IT Operations |
| Related Areas | Ransomware, availability, business continuity |

### KPI-13: Vendor Review Completion

| Field | Definition |
|---|---|
| Objective | Measure whether in-scope vendors receive required initial and periodic security reviews |
| Formula | `(Vendor reviews completed by deadline ÷ Total vendor reviews due) × 100` |
| Target | 100% for critical vendors; at least 95% overall |
| Green | Meets target |
| Amber | 90%–94.9% overall with no overdue critical vendor |
| Red | Below 90% or any critical vendor operating without required review |
| Source | Vendor inventory, review tracker, contracts, due-diligence records |
| Frequency | Monthly status; quarterly reporting |
| Owner | Vendor Management and GRC Analyst |
| Related Areas | Third-party risk, SaaS dependencies, contractual security |

### KPI-14: Control Testing Completion

| Field | Definition |
|---|---|
| Objective | Measure whether planned control tests are completed and independently reviewed |
| Formula | `(Control tests completed and reviewed ÷ Total control tests scheduled) × 100` |
| Target | 100% |
| Green | 100% |
| Amber | 90%–99.9% with approved rescheduling |
| Red | Below 90% or omission of a high-risk control without approval |
| Source | Assessment plan, workpapers, review records |
| Frequency | Monthly during assessment; quarterly thereafter |
| Owner | GRC Analyst |
| Related Areas | Assurance, evidence, governance |

### KPI-15: Remediation Closure Effectiveness

| Field | Definition |
|---|---|
| Objective | Measure whether corrective actions are completed on time and validated before closure |
| Formula | `(Findings remediated, validated, and closed by target date ÷ Total findings due) × 100` |
| Target | At least 90%; 100% for Critical findings |
| Green | Meets target |
| Amber | 80%–89.9% or limited approved extensions |
| Red | Below 80%, any overdue Critical finding, or closure without validation |
| Source | Finding tracker, remediation evidence, retest workpapers |
| Frequency | Monthly |
| Owner | Finding Owners and GRC Analyst |
| Related Areas | Corrective action, residual risk, governance |

## Security KRI Register

### KRI-01: Orphaned or Unowned Accounts

| Field | Definition |
|---|---|
| Risk Signal | Accounts belonging to departed users or accounts without a current accountable owner |
| Calculation | Count of confirmed orphaned or unowned accounts |
| Green | 0 |
| Amber | 1 low-privilege account contained and corrected within target |
| Red | More than 1 account, any privileged orphaned account, or any unexplained post-separation activity |
| Source | HR records, IAM, application inventories, service-account register |
| Frequency | Weekly |
| Owner | IAM Administrator |
| Required Action | Disable or restrict access, investigate activity, identify root cause, and review similar accounts |

### KRI-02: Privileged Accounts Without Required Protection

| Field | Definition |
|---|---|
| Risk Signal | Privileged accounts lacking MFA, named ownership, separate administration, monitoring, or current approval |
| Calculation | Count of noncompliant privileged accounts |
| Green | 0 |
| Amber | 1 contained exception with documented approval and expiration |
| Red | Any unexplained or active noncompliant account |
| Source | Privileged-account inventory, IAM configuration, access reviews |
| Frequency | Weekly |
| Owner | IT Director and IAM Administrator |
| Required Action | Restrict the account, apply required controls, review activity, and escalate unexplained access |

### KRI-03: Overdue Access Removal

| Field | Definition |
|---|---|
| Risk Signal | Access-removal requests not completed within the approved target |
| Calculation | Count and percentage of overdue removals, separated by privilege and system criticality |
| Green | 0 high-risk items and less than 2% low-risk overdue |
| Amber | 2%–5% low-risk overdue with no high-risk item |
| Red | More than 5% overdue or any privileged, terminated-user, vendor, or Restricted-data removal overdue |
| Source | Access reviews, IAM tickets, HR events, vendor records |
| Frequency | Weekly |
| Owner | IAM Administrator and System Owners |
| Required Action | Remove access, investigate delay, and correct the workflow |

### KRI-04: Risky Authentication Events

| Field | Definition |
|---|---|
| Risk Signal | Confirmed or high-confidence risky sign-ins, repeated MFA denials, impossible travel, token misuse, or other suspicious authentication activity |
| Calculation | Count by severity, user type, system, and disposition |
| Green | No unresolved high-risk event; normal baseline variation |
| Amber | Increasing trend or repeated activity involving one user or source |
| Red | Any unresolved high-risk event, confirmed compromise, or multiple related users |
| Source | IAM risk reports, Microsoft 365 logs, incident records |
| Frequency | Daily operational monitoring; monthly trend reporting |
| Owner | IT / Security Lead |
| Required Action | Validate activity, revoke sessions when appropriate, preserve evidence, and initiate incident response |

### KRI-05: Phishing Interaction and Credential Submission

| Field | Definition |
|---|---|
| Risk Signal | Personnel interact with simulated or confirmed phishing, particularly by entering credentials or approving MFA |
| Calculation | Interaction rate and credential-submission rate by campaign and repeat participant population |
| Green | Interaction and submission trend decreases; no actual credential compromise |
| Amber | Interaction rate increases for one cycle or repeat failures are identified |
| Red | Any actual credential submission to a malicious site, MFA approval for an attacker, or worsening trend across two cycles |
| Source | Phishing platform, incident reports, identity logs |
| Frequency | Quarterly and after actual events |
| Owner | GRC Analyst and IT / Security Lead |
| Required Action | Contain actual compromise, provide targeted coaching, and review email and identity controls |

### KRI-06: Unmanaged or Noncompliant Device Access

| Field | Definition |
|---|---|
| Risk Signal | Devices that do not meet security requirements access PLG systems or sensitive information |
| Calculation | Count by device type, user type, information sensitivity, and duration |
| Green | 0 unauthorized devices accessing Restricted data; less than 2% temporary noncompliance overall |
| Amber | 2%–5% noncompliance with active remediation |
| Red | More than 5%, repeated noncompliance, or any unmanaged privileged or Restricted-data access without approval |
| Source | Endpoint management, mobile-device management, IAM, delivery-platform logs |
| Frequency | Weekly |
| Owner | IT Operations |
| Required Action | Restrict access, remediate the device, and review conditional-access coverage |

### KRI-07: Lost or Stolen Device Reporting Delay

| Field | Definition |
|---|---|
| Risk Signal | A lost or stolen device is not reported within PLG's approved reporting target |
| Calculation | Count of delayed reports and average time from discovery to reporting |
| Green | 0 delayed reports |
| Amber | 1 delayed report with no sensitive exposure and prompt containment |
| Red | Any delay involving active access, Restricted data, medical-delivery information, or repeated behavior |
| Source | Incident records, mobile-management logs, dispatch records |
| Frequency | Monthly and after each event |
| Owner | Dispatch Manager and IT / Security Lead |
| Required Action | Revoke sessions, assess exposure, provide coaching, and evaluate reporting friction |

### KRI-08: Overdue Critical or High Vulnerabilities

| Field | Definition |
|---|---|
| Risk Signal | Critical or high-risk vulnerabilities remain open beyond the approved remediation target |
| Calculation | Count and age of overdue findings by asset criticality and exploit status |
| Green | 0 unapproved overdue Critical findings; High backlog within tolerance |
| Amber | Limited overdue High findings with approved plans or an increasing backlog |
| Red | Any actively exploited or unapproved Critical finding overdue, or a material High-risk backlog |
| Source | Vulnerability scanner, patch system, exception register |
| Frequency | Weekly |
| Owner | IT Director |
| Required Action | Prioritize remediation, apply compensating controls, approve a time-limited exception, or restrict the affected asset |

### KRI-09: Medical-Delivery Information Exceptions

| Field | Definition |
|---|---|
| Risk Signal | Medical-delivery information is misdirected, overshared, retained unnecessarily, accessed without authorization, or handled through an unapproved channel |
| Calculation | Count by event type, data sensitivity, affected client, and root cause |
| Green | 0 material events; isolated near misses promptly corrected |
| Amber | Repeated near misses or one limited confirmed exception |
| Red | Any material exposure, repeated control failure, or delayed escalation involving possible PHI/ePHI |
| Source | Incident records, delivery-platform logs, access reviews, client reports |
| Frequency | Monthly and immediately after a material event |
| Owner | Medical Courier Program Manager and GRC Analyst |
| Required Action | Contain disclosure, preserve evidence, consult Legal / Privacy, and correct the workflow |

### KRI-10: Payment-Control Exceptions

| Field | Definition |
|---|---|
| Risk Signal | Payment, refund, payroll, bank-detail, or vendor-master changes bypass required verification or segregation of duties |
| Calculation | Count and value of exceptions, overrides, attempted fraud, and confirmed loss |
| Green | 0 unapproved exceptions |
| Amber | 1 approved emergency exception or repeated attempted fraud without loss |
| Red | Any unapproved bypass, confirmed fraudulent transaction, or incompatible access enabling self-approval |
| Source | Billing system, bank records, approval workflow, incident records |
| Frequency | Monthly and immediately after a material event |
| Owner | Finance Manager |
| Required Action | Pause affected transactions, investigate access, contact financial institutions when necessary, and remediate approval controls |

### KRI-11: Security Incident Reporting Delay

| Field | Definition |
|---|---|
| Risk Signal | Personnel or vendors delay reporting a suspected security incident beyond the required target |
| Calculation | Count and percentage of incidents reported late; median time from discovery to report |
| Green | At least 95% reported within target and no material delayed event |
| Amber | 85%–94.9% within target or isolated low-impact delay |
| Red | Below 85%, any material delay increasing impact, or repeated vendor delay |
| Source | Incident records, interviews, system timestamps, vendor notices |
| Frequency | Monthly and after major incidents |
| Owner | Incident Commander and GRC Analyst |
| Required Action | Identify reporting barriers, correct escalation paths, and update training or contract requirements |

### KRI-12: Repeat Incidents or Findings

| Field | Definition |
|---|---|
| Risk Signal | A security incident or control finding recurs after corrective action was marked complete |
| Calculation | Count of repeated root causes or substantially similar events within the rolling 12-month period |
| Green | 0 material repeat issues |
| Amber | 1 repeated Moderate or Low issue |
| Red | Any repeated Critical or High issue, or multiple events with the same root cause |
| Source | Incident records, findings tracker, after-action reports |
| Frequency | Monthly |
| Owner | GRC Analyst and relevant Control Owner |
| Required Action | Reopen remediation, reassess root cause, expand testing, and escalate residual risk |

### KRI-13: Vendor Security and Access Exceptions

| Field | Definition |
|---|---|
| Risk Signal | Vendors operate without required review, contract protection, named ownership, MFA, access expiration, or timely incident notification |
| Calculation | Count by vendor tier and exception type |
| Green | 0 Critical-vendor exceptions; limited approved lower-tier exceptions |
| Amber | One time-limited Critical-vendor exception or increasing lower-tier exceptions |
| Red | Any unapproved Critical-vendor gap, vendor access without an owner, or material notification failure |
| Source | Vendor inventory, contract records, access lists, review tracker, incident reports |
| Frequency | Monthly |
| Owner | Vendor Management and GRC Analyst |
| Required Action | Restrict access, obtain corrective action, escalate contract enforcement, or reassess the relationship |

### KRI-14: Backup or Restore Failure

| Field | Definition |
|---|---|
| Risk Signal | Critical backup jobs fail repeatedly, protected copies are unavailable, or restoration testing does not meet recovery needs |
| Calculation | Count and duration of unresolved failures; number of failed restore tests |
| Green | No unresolved critical failure; backup success meets target |
| Amber | Isolated failure corrected within target or declining success rate |
| Red | No valid recovery point, repeated critical failure, failed critical restore test, or compromised backup protection |
| Source | Backup logs, alerts, restore-test reports |
| Frequency | Daily operational monitoring; monthly risk reporting |
| Owner | IT Operations |
| Required Action | Restore coverage, investigate cause, protect recovery data, and escalate continuity risk |

### KRI-15: Security Control Friction

| Field | Definition |
|---|---|
| Risk Signal | Personnel report that a control is unsafe, causes material delivery delays, encourages workarounds, or cannot be followed during real operations |
| Calculation | Count and trend of substantiated friction reports, workaround incidents, and affected workflows |
| Green | No material safety conflicts; isolated usability issues resolved promptly |
| Amber | Repeated complaints, increased exceptions, or measurable workflow delay |
| Red | Any credible safety conflict, widespread workaround, or control causing material service disruption |
| Source | Help desk, incident reports, driver and employee feedback, exception requests, operational metrics |
| Frequency | Monthly and immediately for safety concerns |
| Owner | GRC Analyst and relevant Operations Manager |
| Required Action | Apply an interim safe process, perform root-cause analysis, redesign the control, and retest effectiveness |

## Metric Ownership Matrix

| Function | Primary Metrics |
|---|---|
| Executive Leadership | Overall Red metrics, residual-risk trends, overdue Critical and High remediation |
| GRC Analyst | KPI-09, KPI-10, KPI-14, KPI-15; KRI-05, KRI-09, KRI-11, KRI-12, KRI-13, KRI-15 |
| IT Director / IT Operations | KPI-07, KPI-08, KPI-11, KPI-12; KRI-02, KRI-04, KRI-06, KRI-08, KRI-14 |
| IAM Administrator | KPI-01 through KPI-06; KRI-01 through KRI-04 |
| HR Manager | KPI-02, KPI-03, KPI-04, KPI-09 |
| Department and System Owners | KPI-03, KPI-05, KPI-06, KPI-15 |
| Dispatch Manager | KPI-07, KPI-09; KRI-07, KRI-15 |
| Medical Courier Program Manager | KPI-09; KRI-09, KRI-15 |
| Finance Manager | KPI-10; KRI-10 |
| Vendor Management | KPI-13; KRI-13 |

Metric ownership does not eliminate the Control Owner's responsibility for the underlying process.

## Data Collection and Validation

For each reporting cycle, the metric owner should:

1. Obtain data from the authoritative system or process owner.
2. Confirm the reporting period, time zone, population, filters, exclusions, and data owner.
3. Reconcile population totals to an independent source where practical.
4. Apply the approved formula consistently.
5. Retain supporting evidence using the evidence standards in `docs/12-evidence-and-control-testing-plan.md`.
6. Compare the result with the prior period, target, and threshold.
7. Explain material changes, missing data, and exceptions.
8. Assign corrective actions when thresholds are exceeded.
9. Obtain reviewer approval before executive reporting.

## Data Quality Rating

Each reported metric should receive a data-quality rating.

| Rating | Definition |
|---|---|
| High | Automated or authoritative data; population validated; calculation reproducible |
| Moderate | Reliable source with limited manual processing or minor known limitations |
| Low | Material manual processing, incomplete population, inconsistent source, or unverified assumptions |
| Unavailable | Metric cannot be calculated reliably for the period |

A Green performance result supported by Low-quality data should be reported as Gray until the measurement limitation is resolved.

## Reporting Cadence

| Audience | Frequency | Reporting Focus |
|---|---|---|
| IT / Security Operations | Daily or weekly | Authentication, endpoints, vulnerabilities, backups, active incidents |
| Control and Process Owners | Monthly | Performance, exceptions, root causes, and corrective actions |
| GRC and Risk Owners | Monthly | Risk thresholds, findings, trends, and residual-risk changes |
| Executive Leadership | Quarterly and for urgent Red events | Material risks, business impact, overdue remediation, decisions, and resources |
| Board or Governing Body, if applicable | At least annually and for material events | Enterprise risk trends, significant incidents, and management response |

## Executive Dashboard Template

| Metric ID | Metric | Current | Target | Status | Prior Period | Trend | Data Quality | Owner | Action / Decision |
|---|---|---:|---:|---|---:|---|---|---|---|
| KPI-01 | MFA Coverage | TBD | 98% overall / 100% high risk | Gray | N/A | Baseline | TBD | IAM Administrator | Establish baseline |
| KPI-04 | Timely Offboarding | TBD | 98% overall / 100% high risk | Gray | N/A | Baseline | TBD | HR / IAM | Establish baseline |
| KPI-08 | Vulnerability Remediation | TBD | 95% | Gray | N/A | Baseline | TBD | IT Director | Establish baseline |
| KPI-09 | Training Completion | TBD | 95% overall / 100% before sensitive access | Gray | N/A | Baseline | TBD | HR / GRC | Establish baseline |
| KPI-11 | Incident Response Targets | TBD | 95% | Gray | N/A | Baseline | TBD | Incident Commander | Establish baseline |
| KRI-01 | Orphaned Accounts | TBD | 0 | Gray | N/A | Baseline | TBD | IAM Administrator | Establish baseline |
| KRI-08 | Overdue Critical Vulnerabilities | TBD | 0 unapproved | Gray | N/A | Baseline | TBD | IT Director | Establish baseline |
| KRI-09 | Medical-Delivery Exceptions | TBD | 0 material events | Gray | N/A | Baseline | TBD | Medical Courier Manager | Establish baseline |
| KRI-10 | Payment-Control Exceptions | TBD | 0 unapproved | Gray | N/A | Baseline | TBD | Finance Manager | Establish baseline |
| KRI-15 | Security Control Friction | TBD | 0 safety conflicts | Gray | N/A | Baseline | TBD | GRC / Operations | Establish baseline |

`TBD` and Gray are intentional until PLG obtains valid baseline data. Fictional results should not be represented as actual measured performance.

## Trend Indicators

Use the following symbols consistently:

- `↑ Improving` — performance is improving or risk exposure is decreasing.
- `→ Stable` — no material change.
- `↓ Worsening` — performance is declining or risk exposure is increasing.
- `? Unknown` — data is insufficient or not comparable.

For KRIs, make the direction explicit. A lower incident-reporting delay is improving, while a higher phishing-reporting rate may also be improving.

## Escalation Process

### Amber Status

1. Metric owner validates the data.
2. Control Owner determines the cause and operational impact.
3. A corrective action is assigned when the condition is not temporary or self-correcting.
4. GRC tracks the metric in the next reporting cycle.
5. Repeated Amber status may be escalated to Red.

### Red Status

1. Metric owner validates and immediately reports the result.
2. The accountable manager and GRC Analyst assess whether incident response is required.
3. The Risk Owner determines immediate containment, remediation, resource, or service-continuity actions.
4. Legal, Privacy, HR, Finance, Vendor Management, or executive leadership is involved as appropriate.
5. A documented action plan, owner, and due date are established.
6. Residual risk and any temporary acceptance are formally documented.

### Gray Status

1. Document why the data is missing or unreliable.
2. Assign ownership for correcting the measurement process.
3. Use a manual or alternative measure when practical.
4. Do not infer that risk is low because evidence is unavailable.

## Operational Balance Measures

Security improvements should be evaluated alongside logistics performance. PLG should review whether control changes affect:

- Order-processing time
- Dispatch-assignment time
- Delivery timeliness
- Warehouse throughput
- Driver wait time
- Medical-courier service windows
- Help-desk demand
- Account lockouts
- Authentication failures
- Approved exception volume
- Reported safety concerns
- Use of unapproved workarounds

A control should not be weakened solely because it creates inconvenience. However, repeated workarounds, safety conflicts, or material service delays may indicate that the control needs redesign.

## Risk Register Integration

Each material KPI or KRI result should be linked to:

- The affected asset, process, or third party
- The corresponding risk register entry
- The related control or control family
- Current inherent and residual risk
- Open findings and remediation plans
- The accountable Risk Owner

The risk score should be reconsidered when:

- A KRI remains Red across reporting periods
- A control KPI declines materially
- A material incident occurs
- Control testing identifies an ineffective control
- A remediation is validated and sustained
- Business, threat, system, or vendor conditions change

## Metric Change Control

Changes to a metric should document:

- The prior and revised definition
- Reason for the change
- Formula or population changes
- Threshold changes
- Effective date
- Owner and approver
- Impact on historical comparability
- Whether prior results were recalculated

Thresholds should not be changed merely to convert an unfavorable result into a favorable one.

## 90-Day Measurement Rollout

### Days 0–30: Establish Baselines

- Confirm metric owners and authoritative data sources.
- Validate formulas, populations, reporting periods, and evidence requirements.
- Calculate priority identity, vulnerability, device, training, incident, and vendor metrics.
- Rate data quality.
- Record results as baseline values rather than assumed performance.

### Days 31–60: Validate and Tune

- Compare results with the risk register and control-testing findings.
- Correct data-quality problems.
- Confirm that thresholds identify meaningful issues.
- Add operational-balance measures.
- Assign corrective actions for Amber and Red results.

### Days 61–90: Operationalize Reporting

- Publish the first management dashboard.
- Present material trends and decisions to executive leadership.
- Confirm escalation and risk-acceptance workflows.
- Automate reliable data collection where practical.
- Approve the next quarterly measurement cycle.

## Governance and Review

The GRC Analyst should coordinate review of this document at least annually and after:

- A material incident or control failure
- A change to the risk register or control matrix
- A new system, vendor, service, or high-risk workflow
- A significant change in the workforce or technology environment
- Repeated data-quality problems
- Evidence that a target encourages unsafe behavior, underreporting, or metric manipulation
- A material change in contractual, privacy, or security obligations

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. The targets and thresholds in this document are proposed starting points, not measured results from a real organization. They should be validated against actual baseline data, risk appetite, contractual obligations, operational requirements, and qualified legal or compliance guidance before use in a real environment.
