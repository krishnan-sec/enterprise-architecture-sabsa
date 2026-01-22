# Conceptual - Architect View

## Purpose

The Conceptual / Architect View defines **what security must achieve** in order to support business objectives and manage risk.

This view translates the **business drivers and risk posture** defined in the Contextual / Business View into a **set of security principles, capabilities, and architectural intent** that guide all downstream design and implementation decisions.

At this level, security is expressed in terms of **principles and outcomes**, independent of specific technologies or vendors.

---

## Architectural Scope

This view focuses on:

- Security principles and architectural intent
- Enterprise-wide security capabilities
- Trust and threat assumptions
- Control objectives derived from business risk
- Consistent guidance for design and implementation teams

No platform-specific designs, configurations, or tooling decisions are defined here.

---

## Relationship to Other Views

The Conceptual / Architect View acts as the **architectural bridge** between business context and technical design:

- It **derives principles** from the Contextual / Business View
- It **guides logical control design** in the Logical / Designer View
- It **constrains technology choices** in the Physical / Builder View
- It **anchors governance and assurance** in the Management / Manager View

All security designs and controls must be traceable back to this view.

---

## Security Principles

Security principles define **how the organisation approaches protection and risk management**.  
They are stable over time and apply consistently across domains and platforms.

The following principles form the conceptual foundation of the architecture.

---

### SEC-01: Zero Trust


| **Security Principle** | Zero Trust |
|------|-------------|
| **ID** | SEC-01 |
| **Statement** | Assume breach and verify explicitly. Enforce least-privilege access with continuous evaluation of identities, devices, workloads, and data flows across all environments. |
| **Rationale** | Hybrid architectures, cloud services, and partner integrations make network location an unreliable indicator of trust. Zero Trust recentres security control around identity assurance, device posture, and contextual risk signals. This enables secure scalability for distributed systems and APIs without reliance on flat networks or static boundaries. |
| **Security Implementation** | • Implement strong identity proofing, multi-factor authentication, device health attestation, and continuous access evaluation; adopt micro-segmentation and per-request authorisation at access gateways.<br>• Design explicit policy decision points (PDPs) and policy enforcement points (PEPs) close to protected resources; log fine-grained decisions to support analytics and forensics.<br>• Align secrets and key lifecycles with just-in-time (JIT) access models to eliminate standing privileges and reduce blast radius. |
| **Operational Execution** | • Run identity hygiene initiatives to remove orphaned accounts, stale roles, and excessive privileges; operate recurring access review and certification cycles supported by automation.<br>• Maintain golden baselines for gateway and access policies; continuously test allow/deny rules using synthetic transactions and controlled failure scenarios.<br>• Implement and regularly test break-glass access with strict guardrails, monitoring, and post-use review. |
| **Business & Governance** | • Report Zero Trust maturity to leadership using coverage metrics, posture scores, and policy drift indicators.<br>• Demonstrate accelerated partner and customer onboarding while maintaining defined assurance levels.<br>• Map Zero Trust evidence to client due diligence requirements, audits, and relevant certifications. |

<br>

### SEC-02: Defence in Depth

| **Security Principle** | Defence in Depth |
|------|-------------|
| **ID** | SEC-02 |
| **Statement** | Layer preventive, detective, and corrective controls so that the compromise of a single control or layer does not result in systemic failure. |
| **Rationale** | Modern enterprise environments are heterogeneous and highly interconnected, making single-point control strategies fragile. Layered security forces attackers to evade multiple independent mechanisms, increasing cost and detection probability. Controls should be selected with diverse prevention and detection methods to reduce correlated failure across layers. |
| **Security Implementation** | • Combine endpoint protection with network segmentation, API and application-layer controls (e.g., WAF, rate limiting), and behavioural analytics; regularly validate effectiveness through red-team and adversary emulation exercises.<br>• Enforce comprehensive logging and tamper protection at every layer; encrypt telemetry both in transit and at rest to preserve integrity and evidentiary value.<br>• Include backup immutability and offline recovery paths as the final corrective layer to ensure recoverability following destructive attacks. |
| **Operational Execution** | • Operate continuous control health monitoring (e.g., sensor coverage, policy currency, signature freshness) with defined SLOs; automatically remediate coverage gaps where possible.<br>• Maintain and rehearse playbooks for the failure or degradation of primary controls, including fallback detection paths and alternative telemetry sources.<br>• Periodically rebalance the control stack to remove obsolete, overlapping, or low-value layers and maintain architectural clarity. |
| **Business & Governance** | • Evidence layered control effectiveness during audits and assurance activities; link defence-in-depth posture to uptime, incident containment, and recovery KPIs.<br>• Prioritise investment in layers that demonstrate the highest marginal risk reduction per unit of cost.<br>• Publish architectural decision records explaining why specific layers exist, how they interlock, and under what conditions they may be retired or adjusted. |

<br>

### SEC-03: Data Protection & Privacy

| **Security Principle** | Data Protection & Privacy |
|------|-------------|
| **ID** | SEC-03 |
| **Statement** | Protect data confidentiality, integrity, and lawful use from creation through destruction by designing for minimal exposure and provable control. |
| **Rationale** | Data value and sensitivity vary across the enterprise, requiring controls that are proportionate, risk-driven, and automated across the data lifecycle. Privacy-by-design reduces misuse, simplifies regulatory compliance, and enables confident data sharing in regulated environments. |
| **Security Implementation** | • Automate data classification and tagging; enforce encryption, masking, and access controls through data gateways and policy-driven enforcement mechanisms.<br>• Implement consent management and purpose limitation across data flows; maintain data lineage, inventories, and catalogues to support traceability and auditability.<br>• Adopt confidential computing, secure enclaves, or equivalent isolation mechanisms for high-sensitivity data processing where feasible. |
| **Operational Execution** | • Operate periodic access recertification and purpose reviews; integrate privacy risk assessments into product backlogs and delivery workflows.<br>• Execute regular erasure verification and retention conformance reporting to validate end-of-life controls.<br>• Coordinate closely with legal and compliance functions to manage DPIAs and cross-border data transfer controls. |
| **Business & Governance** | • Expose data protection and privacy posture to customers and partners through formal attestations to reduce sales friction and due-diligence overhead.<br>• Reduce breach impact and regulatory exposure by minimising data footprint and controlling access pathways.<br>• Link privacy KPIs to contract renewals, customer trust metrics, and regulatory outcomes. |

<br>

### SEC-04: Application Security

| **Security Principle** | Application Security |
|------|-------------|
| **ID** | SEC-04 |
| **Statement** | Integrate security into the software development lifecycle using automation, secure patterns, and continuous testing for APIs, services, and user-facing components. |
| **Rationale** | Application compromise can cascade rapidly across services and tenants. Shifting security left reduces blast radius and rework, while standardised patterns prevent the introduction of bespoke and inconsistent vulnerabilities. Embedding security into delivery pipelines ensures that risk is addressed early and continuously. |
| **Security Implementation** | • Adopt reference architectures, approved secure libraries, and dependency pinning to reduce exposure to known weaknesses; enforce automated pipeline gates using SAST, SCA, DAST, and infrastructure-as-code scanning.<br>• Require structured threat modelling per application or epic and integrate identified mitigations directly into backlogs and build pipelines; instrument runtime protections such as API gateways and WAF where appropriate.<br>• Continuously fuzz critical parsers, deserialisers, and protocol handlers to detect implementation flaws before exploitation. |
| **Operational Execution** | • Run purple-team loops between application security, development teams, and security operations to validate detections and response for application-layer attacks.<br>• Maintain vulnerability remediation SLAs and automatically generate and track work items aligned to code ownership.<br>• Operate software bill of materials (SBOM) generation and supply-chain attestation for third-party and open-source components. |
| **Business & Governance** | • Reduce incident-driven downtime and investigation cost by preventing vulnerabilities earlier in the delivery lifecycle and generating compliance evidence automatically.<br>• Improve development velocity by providing curated, paved-road components that reduce friction and decision overhead for product teams.<br>• Align application security assurance with customer due-diligence requirements, audits, and relevant certifications. |

<br>

### SEC-05: Risk-Based Security

| **Security Principle** | Risk-Based Security |
|------|-------------|
| **ID** | SEC-05 |
| **Statement** | Allocate security resources according to quantified business impact and threat likelihood, and continuously reassess as conditions change. |
| **Rationale** | Not all risks warrant equal investment. Quantifying risk in terms of business impact, service availability, safety, and legal exposure enables informed trade-offs, prioritised remediation, and effective budget alignment. Risk-based decision making improves executive confidence and focuses effort where it delivers the greatest reduction in exposure. |
| **Security Implementation** | • Maintain a live enterprise risk register mapped to assets, threats, and controls; integrate vulnerability data, security posture signals, and threat intelligence to drive prioritisation.<br>• Use scenario analysis and attack path modelling to test residual risk after mitigation; drive remediation campaigns with clearly defined owners and service-level objectives.<br>• Instrument key risk indicators (KRIs) that predict risk growth, such as patch latency, control drift, and exposure concentration. |
| **Operational Execution** | • Operate a regular risk governance cadence (e.g., quarterly risk councils) to review posture, approve treatment plans, and manage risk exceptions.<br>• Tie remediation progress and risk reduction outcomes to team objectives; escalate blockers early where risk remains unacceptably high.<br>• Synchronise risk assessment and remediation activities with audit and assurance calendars to avoid disruption and peak-load conflicts. |
| **Business & Governance** | • Demonstrate return on investment by showing measurable risk reduction trends over time and their impact on service reliability and safety outcomes.<br>• Meet regulatory, customer, and assurance expectations by maintaining transparent and auditable risk narratives.<br>• Strengthen stakeholder trust through clear communication of risk posture, decisions, and accepted trade-offs. |

<br>

### SEC-06: Continuous Monitoring

| **Security Principle** | Continuous Monitoring |
|------|-------------|
| **ID** | SEC-06 |
| **Statement** | Ensure end-to-end telemetry, correlation, and analytics across enterprise, cloud, and operational environments to enable rapid detection, response, and continuous risk awareness. |
| **Rationale** | Visibility gaps create blind spots that attackers exploit. Unified and high-quality telemetry enables correlated detection, faster response, and informed decision making. Continuous monitoring also provides essential insight into control effectiveness, platform reliability, and capacity planning. |
| **Security Implementation** | • Onboard all relevant assets and data sources into a central monitoring capability; normalise logs and signals across endpoints, networks, applications, APIs, and messaging systems.<br>• Implement detection-as-code with version control, testing, and peer review; integrate detections directly with automated response and orchestration workflows.<br>• Retain telemetry in line with regulatory, legal, and forensic requirements, ensuring integrity protection, time synchronisation, and secure access controls. |
| **Operational Execution** | • Operate continuous detection tuning cycles; regularly review false positives and false negatives in collaboration with security operations and engineering teams.<br>• Monitor ingestion health and telemetry quality; automatically alert on signal loss, parsing failures, or coverage gaps.<br>• Exercise end-to-end detection and response workflows, measuring time-to-detect and time-to-close as standard operational metrics. |
| **Business & Governance** | • Report monitoring effectiveness and operational outcomes to leadership using metrics such as MTTD and MTTR, explicitly linking incidents to service availability and customer SLAs.<br>• Provide audit-ready evidence of monitoring coverage, retention, and control effectiveness.<br>• Use monitoring insights to drive platform resilience improvements, capacity optimisation, and informed investment decisions. |

<br>

### SEC-07: Automation & Orchestration

| **Security Principle** | Automation & Orchestration |
|------|-------------|
| **ID** | SEC-07 |
| **Statement** | Automate repeatable security and compliance activities and orchestrate multi-system responses to reduce dwell time, error rates, and operational cost. |
| **Rationale** | Enterprise scale and complexity require machines to perform repetitive, deterministic tasks so that human effort is reserved for judgment and decision making. Automation enforces standards consistently, accelerates response, and reduces human error while enabling security operations to scale without proportional cost growth. |
| **Security Implementation** | • Implement security orchestration and automated response capabilities for enrichment, containment, and notification; integrate with ticketing systems and collaboration platforms to ensure traceability and accountability.<br>• Use infrastructure-as-code and configuration management to enforce golden baselines, detect configuration drift, and automatically remediate low-risk deviations.<br>• Automate compliance evidence collection and mapping to regulatory and assurance frameworks to reduce manual effort and audit friction. |
| **Operational Execution** | • Measure automation coverage, success rates, and failure modes; maintain human-in-the-loop controls for high-risk or business-impacting actions.<br>• Establish playbook lifecycle management with version control, testing, approval workflows, and rollback capability.<br>• Coordinate automated actions with change management processes to prevent unintended service disruption or policy conflict. |
| **Business & Governance** | • Reduce operational expenditure and incident impact by shortening response times and improving consistency.<br>• Demonstrate continuous compliance to customers, regulators, and auditors through automated and repeatable evidence generation.<br>• Free engineering and operations capacity to focus on product delivery, reliability, and innovation. |

<br>

### SEC-08: Transparency & Governance

| **Security Principle** | Transparency & Governance |
|------|-------------|
| **ID** | SEC-08 |
| **Statement** | Make security posture, decisions, and trade-offs visible, auditable, and explicitly tied to business outcomes and KPIs. |
| **Rationale** | Lack of transparency erodes trust and slows decision making. Clear, evidence-based governance accelerates audits, reduces sales friction, and strengthens partnerships. Meaningful metrics and decision records convert security from a cost centre into a value narrative aligned with business objectives. |
| **Security Implementation** | • Build role-based dashboards (executive, engineering, audit) that expose posture, risk trends, and control effectiveness; automate evidence collection from pipelines, platforms, and monitoring systems.<br>• Track policy exceptions and deviations with defined expiry, accountable owners, and formal risk acceptance records.<br>• Maintain architectural decision records documenting security waivers, trade-offs, and rationale to ensure repeatability and institutional memory. |
| **Operational Execution** | • Establish regular governance cadences including architecture review boards, risk councils, and audit-readiness reviews.<br>• Assign clear data and metric owners and enforce reporting and review cycles.<br>• Run security culture and enablement programs that explain the intent and value behind controls, not just the rules themselves. |
| **Business & Governance** | • Shorten audit and due-diligence cycles while improving renewal and deal close rates.<br>• Improve cross-functional prioritisation and reduce rework through shared visibility and decision transparency.<br>• Strengthen credibility with regulators, customers, and insurers through consistent, evidence-backed governance. |






