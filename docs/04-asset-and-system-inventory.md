# Asset and System Inventory

## Purpose

This inventory identifies the information, systems, devices, infrastructure, facilities, and third-party services that support Peachtree Logistics Group's operations. It establishes a working baseline for risk assessment, control selection, access design, evidence requests, and recovery planning.

The inventory is based on the fictional PLG scenario and currently represents a logical, not configuration-level, view. Technical details, ownership assignments, data locations, and control implementation must be validated during discovery.

## Classification and Criticality Legend

### Information Classification

| Classification | Definition | Examples |
|---|---|---|
| Public | Approved for public release | Published service information and public contact details |
| Internal | Intended for PLG personnel and authorized contractors | Internal procedures, routine operational communications, and training materials |
| Confidential | Disclosure could harm PLG, its workforce, clients, or partners | Employee records, contracts, customer information, shipment details, and vendor information |
| Restricted | Requires the strongest handling controls because unauthorized access could create significant legal, regulatory, safety, financial, or privacy consequences | Applicable PHI/ePHI, authentication secrets, privileged-access information, and applicable payment-card data |

### CIA Criticality

| Rating | Meaning |
|---|---|
| High | Loss of confidentiality, integrity, or availability could cause major operational, legal, financial, safety, privacy, or customer consequences |
| Medium | Loss could cause meaningful disruption or harm, but alternate processes or recovery options are available |
| Low | Loss would have limited operational or business effect |

## Asset Inventory

| Asset ID | Asset or Information Type | Category | Environment / Location | Business Owner | Classification | Confidentiality | Integrity | Availability | Primary Business Use |
|---|---|---|---|---|---|---|---|---|---|
| A-01 | Microsoft 365 | Cloud application | PLG Cloud / SaaS Zone | IT Director; business data owners | Confidential | High | High | Medium | Email, Teams communications, SharePoint/OneDrive documents, customer correspondence, and reporting |
| A-02 | Identity and Access Management Service | Security service | Hybrid Services Zone | IT Director | Restricted | High | High | High | Authentication, authorization, role assignment, account lifecycle management, and access logging |
| A-03 | Logistics and Freight Platform | Cloud application | PLG Cloud / SaaS Zone | Operations Director | Confidential | High | High | High | Customer orders, shipment coordination, freight brokerage, scheduling, and account management |
| A-04 | Warehouse Management System | On-premises application | PLG On-Premises Zone | Warehouse Operations Manager | Confidential | Medium | High | High | Inventory, fulfillment, shipment staging, and warehouse-status management |
| A-05 | Dispatch and Delivery Platform | Cloud and mobile application | PLG Cloud / SaaS and Mobile / Field Zones | Dispatch Manager | Confidential; Restricted when applicable | High | High | High | Driver assignments, routes, status, location, delivery instructions, and proof of delivery |
| A-06 | Billing and Accounting System | Cloud or hybrid application | PLG Cloud / SaaS Zone | Finance Manager | Confidential; Restricted when applicable | High | High | High | Invoicing, payment records, customer billing, reconciliation, and financial reporting |
| A-07 | Records Archive | Information repository | Hybrid Services Zone | Compliance Manager; relevant data owners | Confidential; Restricted when applicable | High | High | Medium | Policy-based retention of order, delivery, financial, contractual, and compliance records |
| A-08 | Employee Laptops and Workstations | Endpoint devices | Corporate offices, warehouses, and remote locations | IT Director | Confidential | High | High | Medium | Access to PLG systems, communications, documentation, and administrative work |
| A-09 | PLG-Issued Driver Mobile Devices | Endpoint devices | Managed Mobile / Field Zone | Dispatch Manager; IT Director | Confidential; Restricted when applicable | High | High | High | Route receipt, status updates, delivery instructions, and proof-of-delivery capture |
| A-10 | Approved Personal Mobile Devices | External or partially managed endpoints | Mobile / Field Environment | Department Manager; device user | Confidential; Restricted when applicable | High | High | Medium | Approved access to PLG communications or delivery applications under BYOD requirements |
| A-11 | On-Premises Servers and Network Infrastructure | Infrastructure | Corporate office and PLG warehouses | IT Director | Internal; Confidential | Medium | High | High | Local connectivity, application hosting, directory services, file storage, and cloud connectivity |
| A-12 | Physical Access-Control System and Records | Physical security system | Corporate office and PLG warehouses | Facilities Manager | Confidential | Medium | High | High | Badge access, visitor accountability, restricted-area control, and physical-access evidence |
| A-13 | Customer, Shipment, and Recipient Information | Information asset | D1, D2, D4, D5, and D6 as applicable | Operations Director; client relationship owners | Confidential | High | High | High | Order fulfillment, routing, delivery confirmation, client service, billing, and reporting |
| A-14 | Medical-Delivery Information and Applicable PHI/ePHI | Information asset | D1, D2, D4, and D6 as validated | Medical Courier Program Manager; healthcare client | Restricted when PHI/ePHI applies | High | High | High | Authorized coordination, chain of custody, delivery confirmation, and client reporting |
| A-15 | Employee and Contractor Records | Information asset | Microsoft 365, HR repositories, IAM, and archive as applicable | Human Resources Manager | Confidential; Restricted when applicable | High | High | Medium | Workforce administration, screening, onboarding, role assignment, and offboarding |
| A-16 | Contracts and Vendor Records | Information asset | Microsoft 365, procurement repository, and archive | Vendor Management / Procurement | Confidential | High | High | Medium | Vendor due diligence, contractual requirements, access authorization, and relationship oversight |
| A-17 | Security, Authentication, and Operational Logs | Information asset | IAM and in-scope platforms | IT Director; GRC Analyst | Confidential; Restricted when applicable | High | High | Medium | Monitoring, investigation, control testing, access review, and incident response |
| A-18 | Logistics Technology Vendors | Third-party service | External Zone | Vendor Management; applicable system owner | Based on information processed | High | High | High | Hosting and supporting logistics, dispatch, delivery, billing, and related platforms |
| A-19 | Payment Processor / Financial Institution | Third-party service | External Zone | Finance Manager | Restricted when payment data applies | High | High | High | Processing authorized payments and returning transaction status or confirmation |
| A-20 | PLG-Operated Offices and Warehouses | Facility | Atlanta-area and regional PLG locations | Facilities Manager; Operations Director | Internal | Medium | High | High | Corporate administration, inventory storage, staging, dispatch support, and fulfillment |

## High-Value and High-Criticality Assets

The following assets warrant priority during the risk assessment because they combine sensitive information, broad access, operational dependency, or cross-boundary connectivity:

1. **IAM Service (A-02):** A compromise or lifecycle failure could affect access across several cloud and on-premises systems.
2. **Logistics and Freight Platform (A-03):** Central to order processing, scheduling, customer service, and freight operations.
3. **Dispatch and Delivery Platform (A-05):** Connects internal staff, employee devices, independent couriers, recipients, and clients.
4. **Billing and Accounting System (A-06):** Processes sensitive financial and customer billing information.
5. **Customer, Shipment, and Recipient Information (A-13):** Moves through several systems and trust boundaries throughout the delivery lifecycle.
6. **Medical-Delivery Information and Applicable PHI/ePHI (A-14):** May create significant privacy, contractual, and regulatory consequences if improperly accessed or disclosed.
7. **On-Premises Infrastructure and WMS (A-04 and A-11):** Directly support warehouse availability and may have different patching, segmentation, monitoring, and recovery maturity than cloud services.

## Preliminary Observations

- PLG's most critical business processes depend on integrations between cloud platforms, on-premises systems, and mobile endpoints.
- The same customer or delivery information may exist in Microsoft 365, operational platforms, mobile applications, billing systems, and archives, increasing the need for data minimization and retention controls.
- Independent couriers and approved personal devices introduce less-trusted access paths that require separate identities, limited authorization, monitoring, and prompt offboarding.
- The hybrid IAM service is a concentration point: weak provisioning, role assignment, privileged access, or deprovisioning could affect multiple assets simultaneously.
- Availability is particularly important for warehouse, dispatch, delivery, IAM, and billing services because outages can disrupt time-sensitive operations.
- The exact presence and flow of PHI/ePHI and payment-card data must be validated before asserting HIPAA or PCI DSS scope.

## Evidence Gaps and Validation Needs

| Validation Item | Evidence Needed | Proposed Owner |
|---|---|---|
| Confirm complete technology inventory | Current hardware, software, SaaS, integration, and owner lists | IT Director |
| Confirm identity architecture | IAM diagrams, directory configuration, federation details, role lists, and authentication settings | IT Director |
| Confirm PHI/ePHI handling | Data samples, client requirements, workflow interviews, contracts, and system-field review | Medical Courier Program Manager; Privacy or Compliance Lead |
| Confirm payment-data handling | Payment workflow, processor agreement, system configuration, and data-flow evidence | Finance Manager |
| Confirm endpoint ownership and management | Mobile-device inventory, MDM status, BYOD agreements, and application controls | IT Director; Dispatch Manager |
| Confirm asset ownership | Approved business and technical owner assignments | COO; IT Director; department managers |
| Confirm retention locations and periods | Retention schedule, archive configuration, deletion evidence, and legal requirements | Compliance Manager; Legal Counsel |
| Confirm vendor dependencies | Vendor inventory, contracts, security documentation, integrations, and support-access records | Vendor Management / Procurement |
| Confirm recovery requirements | Business impact analysis, recovery objectives, backups, restoration results, and continuity procedures | IT Director; Operations Director |

## Inventory Maintenance Requirements

- Assign a named business owner and technical custodian to each system and information asset.
- Review the inventory at least annually and after material system, vendor, integration, or business-process changes.
- Reconcile the inventory with IAM, procurement, finance, endpoint-management, vulnerability-management, and vendor-management records.
- Track unsupported software, shadow IT, unmanaged devices, and systems without confirmed ownership as exceptions requiring remediation.
- Document data classification, retention, backup, recovery, and disposal requirements for each high-value information asset.

## Portfolio Disclaimer

Peachtree Logistics Group is a fictional organization created for educational and portfolio purposes. Inventory entries and ownership assignments are scenario-based assumptions that require validation in a real engagement.
