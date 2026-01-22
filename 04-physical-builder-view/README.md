# Physical - Builder View

## Purpose

The Physical / Builder View defines **how logical security controls are realised using concrete platforms, services, and enforcement mechanisms**.

This view translates the **logical control objectives** defined in the Logical / Designer View into **deployable, operable, and supportable security architectures** while remaining aligned with architectural intent and business risk.

It answers the question:  
**“Which classes of platforms and mechanisms enforce the logical controls, and how are they composed?”**

---

## Architectural Scope

This view focuses on:

- Platform and service categories used to enforce controls
- Physical trust boundaries and enforcement points
- Control placement and integration patterns
- Operational dependencies and shared responsibility
- Resilience, scalability, and availability considerations

Detailed configuration, detections, and queries are **explicitly out of scope** and belong to the Component / Tradesman View.

---

## Relationship to Other Views

The Physical / Builder View serves as the **realisation layer** of the architecture:

- It **implements logical controls** from the Logical / Designer View
- It **constrains implementation choices** in the Component / Tradesman View
- It **inherits intent and principles** from the Conceptual / Architect View
- It **feeds governance and assurance** in the Management / Manager View

Every physical control must map to a logical control, and every component-level implementation must map to a physical control.

---

## Physical Control Domains

Physical controls are organised into the following domains, each representing a class of enforcement capability rather than a specific product.

---

### PS-01: Identity & Access Management

| **Physical Service** | Identity & Access Management |
|------|-------------|
| **ID** | PS-01 |
| **Statement** | Deploy an integrated enterprise identity and access management capability that centralises authentication, authorisation, and privilege control for users, devices, workloads, and partners across hybrid and cloud environments. |
| **Rationale** | Identity and access management provides the primary enforcement mechanism for Zero Trust by verifying identity and context before granting access. Centralised IAM standardises how credentials, privileges, and access tokens are issued, governed, monitored, and revoked, reducing attack surface and enabling consistent assurance. |
| **Security Implementation** | • Implement a central identity platform providing single sign-on, multi-factor authentication, and conditional access, integrated with authoritative identity sources across environments.<br>• Enforce privileged access management with just-in-time elevation, approval workflows, session monitoring, and automatic expiry of elevated privileges.<br>• Use managed identities, workload identities, and secure token issuance for service-to-service communication, eliminating long-lived static credentials. |
| **Operational Execution** | • Automate identity lifecycle management by integrating joiner–mover–leaver processes with authoritative HR and project systems to prevent orphaned or over-privileged accounts.<br>• Monitor authentication activity, privilege escalation, and anomalous access patterns through centralised telemetry and correlation.<br>• Perform recurring privileged access reviews and certification campaigns, retaining access logs and session records for investigation and audit purposes. |
| **Business & Governance** | • Strengthen compliance with identity and access control requirements through consistent enforcement and auditable evidence.<br>• Reduce the risk of unauthorised access, insider threat, and credential compromise across critical systems and services.<br>• Provide demonstrable assurance of identity governance maturity to customers, partners, regulators, and auditors. |

<br>

### PS-02: Network Security

| **Physical Service** | Network Security |
|------|-------------|
| **ID** | PS-02 |
| **Statement** | Deploy layered network security controls that protect hybrid and cloud environments through controlled connectivity, threat prevention, and enforced micro-segmentation. |
| **Rationale** | Network security ensures that data movement and service communications occur only through monitored, authorised paths. Layered controls reduce attack surface, limit lateral movement, and prevent data exfiltration while supporting defence in depth across diverse environments. |
| **Security Implementation** | • Enforce zoning and segmentation using network control planes that apply least-connectivity principles for ingress, egress, and east–west traffic.<br>• Establish secure connectivity for inter-site and remote access using encrypted tunnels with device and user posture validation.<br>• Integrate network-based threat detection and prevention capabilities to inspect traffic, identify malicious patterns, and block unauthorised activity in real time. |
| **Operational Execution** | • Regularly review and validate network security rules against topology and application changes to detect drift, redundancy, or unintended exposure.<br>• Continuously collect and forward telemetry from network enforcement points to central monitoring for correlation and investigation.<br>• Perform periodic network penetration testing, segmentation validation, and resilience exercises to confirm containment effectiveness. |
| **Business & Governance** | • Demonstrate compliance with network security and segmentation requirements through auditable controls and documented evidence.<br>• Reduce the likelihood and impact of lateral movement, denial-of-service events, and data exfiltration, protecting service availability and continuity.<br>• Increase customer, partner, and regulator confidence through demonstrable defence in depth at the network perimeter and core. |

<br>

### PS-03: Data Protection

| **Physical Service** | Data Protection |
|------|-------------|
| **ID** | PS-03 |
| **Statement** | Implement enterprise-wide data protection controls, including encryption, key management, and integrity validation, to safeguard structured and unstructured data across all platforms and environments. |
| **Rationale** | Strong cryptographic protection and disciplined key governance preserve data confidentiality and integrity throughout its lifecycle. Effective data protection reduces breach impact, supports lawful processing, and enables compliance with privacy and security obligations without constraining business operations. |
| **Security Implementation** | • Enforce encryption for data at rest and in transit using strong, industry-standard cryptography, ensuring end-to-end protection across storage systems, applications, and APIs.<br>• Centralise cryptographic key and secret management using controlled key stores or hardware-backed security modules, with separation of duties, rotation policies, and access auditing.<br>• Apply integrity controls such as digital signatures, hashing, and tamper-detection mechanisms to protect data authenticity and prevent unauthorised modification. |
| **Operational Execution** | • Automate key rotation, access reviews, and recovery testing for cryptographic systems to maintain readiness and reduce operational risk.<br>• Audit encryption, decryption, and key access events to verify policy adherence and surface anomalous activity for investigation.<br>• Regularly validate backup encryption and restoration processes, maintaining documented evidence to support incident response and assurance activities. |
| **Business & Governance** | • Demonstrate compliance with data protection, privacy, and cryptographic control requirements through consistent enforcement and auditable evidence.<br>• Reduce the likelihood and impact of data compromise, regulatory penalties, and contractual breaches.<br>• Strengthen trust with customers, partners, and regulators by evidencing mature, enterprise-grade data protection practices. |

<br>

### PS-04: Monitoring & Detection Tools

| **Physical Service** | Monitoring & Detection Tools |
|------|-------------|
| **ID** | PS-04 |
| **Statement** | Deploy comprehensive monitoring and detection capabilities that collect, analyse, and respond to security-relevant telemetry across enterprise, cloud, and operational environments. |
| **Rationale** | Centralised and high-fidelity monitoring enables early detection of anomalies and coordinated response to security incidents. Effective detection tooling forms the operational backbone of resilience by validating control effectiveness and reducing time to detect and respond. |
| **Security Implementation** | • Deploy enterprise-grade telemetry collection and correlation capabilities to aggregate identity, endpoint, application, network, and operational technology signals.<br>• Apply behavioural analytics and anomaly detection to baseline normal activity and identify insider threats, compromised accounts, and lateral movement.<br>• Ensure telemetry storage is immutable where required, encrypted, time-synchronised, and retained in accordance with regulatory, legal, and forensic requirements. |
| **Operational Execution** | • Operate continuous monitoring workflows with standardised playbooks for alert triage, investigation, containment, and escalation.<br>• Perform regular detection rule tuning and false-positive analysis, feeding improvements back into version-controlled detection logic.<br>• Execute periodic adversary emulation and purple-team exercises to validate detection coverage, visibility gaps, and response readiness. |
| **Business & Governance** | • Reduce the business impact of security incidents by lowering mean time to detect and respond through effective monitoring and response coordination.<br>• Provide continuous assurance and auditable evidence of monitoring coverage and control effectiveness.<br>• Strengthen transparency and accountability in incident detection and management through consistent reporting and metrics. |

<br>

### PS-05: Automation & Orchestration

| **Physical Service** | Automation & Orchestration |
|------|-------------|
| **ID** | PS-05 |
| **Statement** | Utilise security automation and orchestration capabilities to standardise enforcement, streamline incident response, and maintain configuration integrity across enterprise environments. |
| **Rationale** | Automation reduces manual effort and error while ensuring consistent application of controls at scale. Orchestration enables coordinated, multi-system response to security events, improving speed, reliability, and cost efficiency as operational complexity grows. |
| **Security Implementation** | • Implement orchestration platforms to automate repetitive response actions such as account containment, endpoint isolation, configuration rollback, and credential rotation.<br>• Integrate automation with governance and compliance systems to support evidence generation, exception tracking, and remediation lifecycle management.<br>• Apply infrastructure-as-code and configuration automation to enforce security baselines, validate changes, and detect drift across environments. |
| **Operational Execution** | • Continuously monitor automation performance, including success rates, rollback frequency, and failure modes, to validate reliability and safety.<br>• Conduct regular reviews and testing of playbooks and automation logic to ensure alignment with evolving threats, architecture changes, and compliance requirements.<br>• Maintain explicit approval checkpoints and guardrails for high-impact or sensitive actions to balance speed with accountability. |
| **Business & Governance** | • Reduce operational overhead while improving consistency and response speed through automated enforcement and remediation.<br>• Demonstrate proactive control governance through repeatable, automated evidence collection and reporting.<br>• Enable measurable cost optimisation and operational resilience without compromising assurance or control quality. |

<br>

### PS-06: Risk Assessment Tools

| **Physical Service** | Risk Assessment Tools |
|------|-------------|
| **ID** | PS-06 |
| **Statement** | Implement integrated risk assessment capabilities that quantify, prioritise, and track vulnerabilities, control gaps, and risk exposure across enterprise environments. |
| **Rationale** | Continuous and evidence-based risk assessment ensures that security effort and investment are directed toward mitigating the most significant threats. Effective tooling supports informed decision making, aligns remediation with business impact, and maintains consistency with governance and assurance expectations. |
| **Security Implementation** | • Deploy automated assessment capabilities to identify vulnerabilities, misconfigurations, and control weaknesses, producing risk signals aligned to asset criticality and exposure.<br>• Correlate technical risk findings with business impact, service importance, and threat context within governance and risk management workflows to drive prioritisation and escalation.<br>• Generate automated notifications and workflows for high-risk findings that require remediation, mitigation, or formal risk acceptance. |
| **Operational Execution** | • Perform continuous and scheduled assessments, including vulnerability scanning and posture validation, feeding results directly into the enterprise risk register.<br>• Conduct periodic reviews of residual risk and exposure trends to inform remediation planning and investment decisions.<br>• Validate closure of critical findings through re-assessment, evidence capture, and auditable confirmation of risk reduction. |
| **Business & Governance** | • Demonstrate alignment with enterprise risk management and governance standards through consistent, traceable risk reporting.<br>• Enable leadership to visualise exposure trends, remediation effectiveness, and return on security investment.<br>• Provide assurance that risk treatment, exception handling, and acceptance decisions are consistently tracked, reviewed, and governed. |

<br>

### PS-07: Compliance & Reporting

| **Physical Service** | Compliance & Reporting |
|------|-------------|
| **ID** | PS-07 |
| **Statement** | Implement automated compliance and reporting capabilities that continuously monitor adherence to internal standards, control frameworks, and regulatory requirements. |
| **Rationale** | Automated compliance tracking reduces manual audit effort, improves policy adherence, and provides transparent, real-time visibility into control effectiveness. Continuous evidence generation enables assurance at scale while reducing operational overhead and audit fatigue. |
| **Security Implementation** | • Enforce baseline configurations and control requirements using policy evaluation and validation mechanisms across platforms and environments.<br>• Integrate governance and compliance workflows with delivery pipelines and operational systems to automate evidence collection, deviation detection, and exception tracking.<br>• Map technical controls to recognised standards and frameworks to enable consistent, audit-ready reporting and traceability. |
| **Operational Execution** | • Review compliance posture and deviation trends on a regular cadence to prioritise remediation and manage risk acceptance timelines.<br>• Automate generation and distribution of compliance reports for auditors, customers, and internal stakeholders.<br>• Maintain version-controlled evidence repositories documenting control design, operation, and effectiveness over time. |
| **Business & Governance** | • Demonstrate continuous and transparent compliance with contractual, regulatory, and internal governance obligations.<br>• Reduce audit preparation time and administrative burden through automated evidence and reporting processes.<br>• Strengthen customer, partner, and regulator confidence through consistent, repeatable compliance assurance. |

