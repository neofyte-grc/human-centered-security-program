# Executive Summary

## Peachtree Logistics Group Security Risk and IAM Program

**Prepared for:** PLG Executive Leadership  
**Prepared by:** GRC Analyst  
**Organization:** Peachtree Logistics Group  
**Assessment Type:** Enterprise Security Risk and Identity and Access Management Assessment  
**Environment:** Mixed cloud and on-premises  
**Project Status:** Portfolio case study and proposed security improvement program

## Executive Overview

Peachtree Logistics Group (PLG) is a fictional regional logistics company headquartered in Atlanta, Georgia. The company employs approximately 225 people and provides warehousing, last-mile delivery, medical-courier services, and freight brokerage throughout the Southeastern United States.

PLG relies on Microsoft 365, cloud logistics applications, an on-premises Warehouse Management System, mobile dispatch and delivery tools, billing systems, employee endpoints, driver devices, independent couriers, and third-party technology providers. These systems support time-sensitive operations while processing employee records, customer information, delivery records, payment information, contracts, vendor data, and medical-delivery information that may include PHI/ePHI.

The assessment identified identity and access management as PLG's central security concern. Inconsistent provisioning, excessive permissions, weak account separation, incomplete offboarding, unmanaged mobile access, and limited third-party oversight could allow a compromised or outdated account to expose sensitive information or interrupt operations.

The recommended program therefore places identity at the center of PLG's risk-reduction strategy. It combines role-based access control, MFA, access lifecycle procedures, mobile and vendor safeguards, security awareness, incident readiness, evidence-based testing, performance measurement, and human-centered control design.

The goal is not to add security steps for their own sake. The goal is to make secure behavior practical during real warehouse, dispatch, delivery, medical-courier, finance, and administrative work.

## Assessment Objective

The project was designed to:

1. Identify security risks across PLG's people, processes, technology, physical locations, and third-party relationships.
2. Evaluate IAM practices across cloud and on-premises systems.
3. Recommend role-based and least-privilege access controls.
4. Establish consistent provisioning, transfer, access-review, and offboarding procedures.
5. Protect mobile and medical-delivery workflows without creating unsafe or impractical requirements.
6. Develop role-based awareness and incident-response materials.
7. Define evidence and control-testing procedures.
8. Establish KPIs and KRIs that show whether controls reduce risk and remain usable.

## Scope Summary

The assessment covers:

- Microsoft 365, including email, Teams, SharePoint, and identity configuration
- Cloud logistics and freight-brokerage applications
- Warehouse Management System
- Dispatch and delivery platform
- Billing and accounting system
- Records archive
- Employee laptops and mobile devices
- Driver and independent-courier devices
- User accounts, permissions, privileged access, and authentication
- Warehouses and corporate offices
- Employee and contractor security practices
- Medical-delivery information handling
- Payment and customer information
- Vendor access and PLG's management of third-party relationships

The project excludes active exploitation, full penetration testing, vendor-owned internal networks, vehicle mechanical systems, and physical building construction.

## Overall Risk Conclusion

PLG's most significant risk is the interaction among identity weaknesses, operational urgency, mobile access, sensitive information, and third-party dependency.

A single compromised or improperly retained account could provide access to Microsoft 365, customer records, delivery details, payment workflows, or medical-delivery information. The impact could extend beyond data exposure to include fraudulent payments, incorrect deliveries, warehouse interruption, client notification obligations, reputational harm, and loss of customer trust.

PLG can materially reduce this exposure through a focused program built around five priorities:

1. Establish reliable identity governance.
2. Protect high-risk access with MFA and contextual controls.
3. Separate employee, privileged, vendor, and independent-courier access.
4. Strengthen mobile, medical-delivery, and payment workflows.
5. Measure control effectiveness and operational friction continuously.

## Priority Risk Themes

### 1. Identity Lifecycle and Excessive Access

PLG lacks a consistently enforced process connecting HR, managers, IT, System Owners, Facilities, Vendor Management, and application administrators. This increases the likelihood that new users receive excessive access, transferred personnel retain permissions from prior roles, and departed employees or vendors remain active.

**Potential impact:**

- Unauthorized access
- Orphaned accounts
- Inaccurate audit trails
- Fraud or inappropriate changes
- Exposure of customer, employee, payment, or medical-delivery information

**Recommended response:**

- Implement a documented joiner-mover-leaver process.
- Use role-based access profiles.
- Require timely offboarding across logical and physical systems.
- Conduct recurring access certifications.
- Maintain named owners for privileged, service, vendor, and external accounts.

### 2. Account Compromise and Weak Authentication

Microsoft 365 and PLG's cloud applications are attractive entry points for phishing, credential theft, MFA fatigue, malicious forwarding, and unauthorized sharing.

**Potential impact:**

- Email and file exposure
- Business email compromise
- Fraudulent payment requests
- Theft of customer and employee information
- Use of a trusted PLG identity to attack clients or vendors

**Recommended response:**

- Require MFA for all appropriate accounts, with no unexplained high-risk gaps.
- Apply conditional access and risk-based authentication.
- Protect privileged accounts with separate identities.
- Monitor sign-ins, inbox rules, application consent, and external sharing.
- Provide practical phishing and MFA training.

### 3. Driver, Courier, and Mobile Device Exposure

Drivers and independent couriers use mobile applications to receive assignments, navigate routes, confirm deliveries, collect signatures, and report exceptions. These workflows occur in public locations, under time pressure, and sometimes on approved personal devices.

**Potential impact:**

- Exposure of recipient addresses, contact details, signatures, photos, and delivery notes
- Unauthorized use of active application sessions
- Sensitive information retained in screenshots, notifications, or caches
- Continued courier access after an assignment ends
- Unsafe device interaction while driving

**Recommended response:**

- Use managed devices or enforce defined security requirements for approved personal devices.
- Limit information by role, assignment, and time.
- Separate PLG employee and independent-courier identities.
- Revoke sessions and access rapidly after loss, theft, separation, or assignment completion.
- Design authentication and incident reporting for parked use only.

### 4. Medical-Delivery Information

Medical-delivery information can appear throughout intake, scheduling, dispatch, transportation, confirmation, billing, and retention. Depending on its content and PLG's contractual role, the information may include PHI/ePHI or reveal a person's relationship with a healthcare service.

**Potential impact:**

- Privacy harm
- Client and contractual consequences
- Legal or regulatory notification obligations
- Loss of healthcare-client trust

**Recommended response:**

- Apply minimum-necessary access and disclosure.
- Avoid sensitive content in lock-screen notifications and unapproved messaging.
- Verify authorized recipients.
- Restrict access after delivery completion.
- Define retention and disposal rules.
- Escalate suspected exposure promptly for qualified legal or privacy review.

### 5. Payment Fraud and Executive Impersonation

Finance and operations personnel may receive urgent requests to redirect payments, change bank information, issue refunds, modify vendor records, or bypass normal approval steps.

**Potential impact:**

- Direct financial loss
- Compromised financial accounts
- Fraudulent vendor or customer changes
- Reputational and contractual harm

**Recommended response:**

- Require independent verification through a known contact method.
- Separate initiation and approval duties.
- Protect finance and executive accounts with strong authentication.
- Monitor unusual account and payment activity.
- Authorize employees to challenge urgent requests regardless of apparent seniority.

### 6. On-Premises System and Ransomware Risk

The Warehouse Management System is operationally critical and may face different patching, segmentation, backup, and recovery challenges than cloud services.

**Potential impact:**

- Warehouse and fulfillment interruption
- Loss or encryption of inventory and shipment records
- Lateral movement to other PLG systems
- Manual-process errors during an outage

**Recommended response:**

- Maintain accurate asset and vulnerability inventories.
- Apply risk-based patching and endpoint protection.
- Segment critical on-premises systems.
- Protect and test backups.
- Document secure manual continuity procedures.
- Reconcile transactions before returning to normal operations.

### 7. Third-Party and Vendor Dependency

PLG depends on SaaS vendors, payment providers, technical support vendors, carriers, and independent couriers. PLG cannot directly inspect most vendor environments and must rely on due diligence, contracts, access controls, monitoring, and response coordination.

**Potential impact:**

- Vendor-hosted data exposure
- Extended operational outages
- Unauthorized vendor support access
- Delayed incident notification
- Continued access after a relationship ends

**Recommended response:**

- Maintain a complete, risk-tiered vendor inventory.
- Perform risk-based due diligence.
- Define security, access, incident-notification, return, and disposal obligations contractually.
- Use named, MFA-protected, time-limited vendor accounts.
- Review critical vendors periodically and validate secure offboarding.

### 8. Human Factors and Control Friction

PLG's personnel work under real operational constraints: delivery windows, high order volume, shift work, small screens, public environments, warehouse noise, intermittent connectivity, and urgent customer demands. Controls that ignore these conditions may encourage workarounds.

**Potential impact:**

- Shared credentials
- Unapproved communication channels
- Delayed incident reporting
- Dismissed alerts
- Unsafe mobile interaction
- Reduced trust in the security program

**Recommended response:**

- Test controls with representative users before broad deployment.
- Treat recurring mistakes as potential design signals.
- Use concise, role-specific instructions.
- Provide safe and approved outage procedures.
- Measure security outcomes and workflow impact together.
- Maintain a supportive, non-punitive reporting culture for good-faith mistakes.

## Recommended Control Strategy

The recommended security model is layered so that PLG does not depend on any single control or on perfect employee behavior.

| Control Layer | Primary Actions | Intended Outcome |
|---|---|---|
| Governance | Assign Risk, System, Data, and Control Owners; maintain policies and exceptions | Clear accountability and consistent decisions |
| Identity | MFA, RBAC, joiner-mover-leaver controls, access reviews, privileged-account separation | Reduced unauthorized and excessive access |
| Technology | Conditional access, endpoint protection, logging, patching, backups, segmentation | Prevention, detection, containment, and recovery |
| Information | Classification, minimum necessary, approved sharing, retention, secure disposal | Reduced sensitive-data exposure |
| Operations | Verified changes, safe mobile workflows, continuity procedures, recipient verification | Secure work that supports delivery commitments |
| Third Party | Risk tiering, contracts, restricted access, monitoring, offboarding | Reduced vendor and external-user exposure |
| People | Role-based training, job aids, exercises, supportive reporting | Better decisions under real working conditions |
| Assurance | Evidence collection, control testing, KPIs, KRIs, remediation validation | Demonstrable and sustained risk reduction |

## 90-Day Priority Roadmap

### Days 0–30: Stabilize High-Risk Access

**Leadership objectives:** Establish ownership, close obvious access gaps, and create reliable escalation paths.

**Priority actions:**

- Confirm executive sponsor, Risk Owners, System Owners, Data Owners, and Control Owners.
- Produce authoritative employee, contractor, courier, vendor, privileged, and service-account inventories.
- Enable or validate MFA for high-risk populations.
- Disable confirmed orphaned and unnecessary shared accounts.
- Define emergency and routine offboarding procedures.
- Establish independent verification for payment and high-risk account changes.
- Publish incident-reporting channels and supportive reporting expectations.
- Confirm that mobile controls never require driver interaction while moving.

### Days 31–60: Implement Repeatable Controls

**Leadership objectives:** Replace informal practices with consistent, role-based procedures.

**Priority actions:**

- Pilot RBAC roles across representative departments.
- Implement joiner-mover-leaver workflows and completion tracking.
- Begin periodic access reviews.
- Separate privileged accounts from standard user accounts.
- Separate PLG-employed driver and independent-courier access.
- Apply assignment-based courier access and expiration.
- Review Microsoft 365 conditional access, sharing, logging, and application-consent settings.
- Establish approved outage workflows for dispatch, warehouse, and delivery operations.
- Deliver high-risk role training for finance, dispatch, drivers, medical-courier personnel, managers, and administrators.

### Days 61–90: Validate and Measure

**Leadership objectives:** Confirm that controls operate effectively and do not create unacceptable operational friction.

**Priority actions:**

- Test identity, offboarding, access-review, mobile, medical-delivery, payment, logging, backup, and vendor controls.
- Conduct Microsoft 365 compromise, lost-device, and warehouse-disruption exercises.
- Validate backup restoration for critical systems.
- Establish KPI and KRI baselines.
- Publish the first executive security dashboard.
- Track findings, owners, target dates, and residual risk.
- Review frontline feedback and redesign impractical controls.

## Leadership Decisions Required

Executive leadership should approve or assign the following:

1. **Risk ownership:** Name accountable executives or senior managers for material risks.
2. **Identity governance:** Approve standardized RBAC and joiner-mover-leaver requirements.
3. **High-risk authentication:** Require MFA and stronger controls for privileged, finance, vendor, remote, and medical-delivery access.
4. **Mobile security:** Define minimum requirements for PLG-issued and approved personal devices.
5. **Independent couriers:** Approve separate identities, assignment-limited access, training, and contractual safeguards.
6. **Medical-delivery handling:** Direct qualified legal or privacy review of applicable obligations.
7. **Payment controls:** Require independent verification and segregation of duties.
8. **Vendor risk:** Approve critical-vendor review and access standards.
9. **Incident readiness:** Assign response authority and approve business-continuity procedures.
10. **Resources:** Allocate appropriate staff time, technology, training, and remediation funding.
11. **Risk acceptance:** Require documented, time-limited approval for material control exceptions.
12. **Reporting culture:** Reinforce that good-faith reporting and verification are expected behaviors.

## Success Measures

PLG should initially emphasize a concise set of executive metrics.

| Measure | Initial Target |
|---|---:|
| MFA coverage | At least 98% overall; 100% for high-risk accounts |
| Timely offboarding | At least 98% overall; 100% for high-risk separations |
| Access review completion | 100% |
| Managed and compliant device coverage | At least 95%; 100% for privileged and Restricted-data access |
| Critical vulnerability remediation within target | At least 95% |
| Required training completed before sensitive access | 100% |
| Material incident milestones met within target | At least 95% |
| Critical restore tests completed successfully | 100% |
| Critical vendor reviews completed on time | 100% |
| High-risk findings with an owner and target date | 100% |
| Orphaned privileged accounts | 0 |
| Credible control-related safety conflicts | 0 |

Targets should be validated after PLG establishes reliable baseline data. Missing or unreliable data should be reported as a measurement gap rather than assumed to be satisfactory.

## Expected Business Benefits

If implemented effectively, the recommended program should provide:

- Reduced likelihood of account compromise and unauthorized access
- Faster removal of access after termination, transfer, contract end, or delivery completion
- Improved protection of customer, employee, payment, and medical-delivery information
- Stronger resistance to phishing, impersonation, and payment fraud
- Better visibility through consistent logging and evidence
- Improved incident containment and recovery
- Clearer accountability across HR, IT, managers, operations, and vendors
- More reliable vendor and external-user oversight
- Fewer insecure workarounds
- Security controls that better support warehouse, dispatch, and delivery operations
- Defensible evidence for clients, audits, assessments, and leadership review

## Residual Risk

The proposed program will reduce risk but will not eliminate it. PLG will continue to face:

- Phishing and social-engineering attempts
- Lost or stolen devices
- Human error
- Vendor incidents and outages
- Emerging vulnerabilities
- Operational pressure and staffing constraints
- Situations where contractual or client requirements change

Residual risk should be monitored through control testing, incidents, exceptions, KPIs, KRIs, and periodic reassessment. Risks exceeding PLG's approved tolerance should be remediated, transferred, avoided, or formally accepted by the appropriate Risk Owner.

## Conclusion

PLG's security challenge is not solely technical. It is an operational governance challenge involving identity, sensitive information, mobile work, third parties, and people performing time-sensitive tasks.

The most effective path forward is a focused, human-centered IAM and risk program that makes access appropriate, activity visible, responsibilities clear, and secure behavior practical.

PLG should begin with high-risk identities and lifecycle controls, then strengthen mobile, medical-delivery, payment, vendor, incident-response, and recovery practices. Control testing and performance measurement should follow implementation so that leadership can distinguish documented intentions from controls that actually work.

With executive sponsorship, clear ownership, and a measured 90-day implementation plan, PLG can reduce risk while preserving the speed, safety, and reliability its customers and operational teams require.

## Project Deliverables

The complete assessment portfolio includes:

1. `docs/01-project-charter.md`
2. `docs/02-stakeholder-analysis.md`
3. `docs/03-data-flow-diagrams.md`
4. `docs/04-asset-and-system-inventory.md`
5. `docs/05-risk-assessment-methodology.md`
6. `docs/06-risk-register.md`
7. `docs/07-security-control-matrix.md`
8. `docs/08-role-based-access-control-model.md`
9. `docs/09-iam-and-security-procedures.md`
10. `docs/10-security-awareness-plan.md`
11. `docs/11-incident-response-scenarios.md`
12. `docs/12-evidence-and-control-testing-plan.md`
13. `docs/13-kpis-and-kris.md`
14. `docs/14-human-factors-analysis.md`
15. `docs/15-executive-summary.md`

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. This executive summary describes a proposed security assessment and improvement program. It does not represent an audit opinion, certification, legal conclusion, regulatory determination, or assessment of a real organization.
