# Contextual - Business View

## Purpose

The Contextual / Business View defines **why security controls exist**.  

It captures the **business objectives, risk drivers, and impact considerations** that shape all downstream security architecture decisions.

This view establishes the **non-negotiable business context** against which security principles, designs, implementations, and governance are derived.

---

## Architectural Scope

This view focuses on:

- Business goals and strategic drivers
- Risk appetite and tolerance
- Business impact of security failure
- Regulatory, contractual, and trust obligations
- Executive expectations for security outcomes

No technologies, tools, or implementations are defined at this level.

---

## Business Drivers and Security Outcomes

Security outcomes are anchored to the organisation’s core business drivers.  
Each driver expresses **why protection is required**, not how it is implemented.

---

### BD-01: Product-First Development

| **Business Driver** | Product-First Development |
|------|-------------|
| **ID** | BD-01 |
| **Statement** | Embed security by design and by default into every product increment and integration so that delivery velocity and assurance increase together. |
| **Rationale** | Security must accelerate, not obstruct, delivery. Shifting security left through integrated threat modelling, automated code analysis, and dependency health checks enables faster releases with fewer incidents. Treating security controls as reusable product components (patterns, libraries, pipelines) reduces time to market and ensures consistent guardrails across teams. |
| **Security Implementation** | • Codify secure defaults as versioned platform patterns (API gateways, cloud resources, database servers, WAF) so teams consume security as code rather than reinventing controls per service.<br>• Mandate threat modelling at feature kick-off, capturing misuse and abuse cases and mapping mitigations directly into backlogs and pipeline checks.<br>• Integrate SAST, SCA, DAST, and container image scanning into CI/CD with quality gates that block releases on critical findings and automatically generate audit evidence. |
| **Operational Execution** | • Define Product Security Champions within each squad responsible for triage of findings, exception handling, and coordination with the central security function.<br>• Run sprint-level security reviews and vulnerability burn-down, with remediation SLAs tied to severity and asset criticality.<br>• Ensure platform teams maintain golden base images and IaC modules, with changes governed through change control and regression-tested against security baselines. |
| **Business & Governance** | • Report secure delivery metrics (e.g., first-pass quality-gate success rate, mean remediation time per severity) to executive dashboards.<br>• Link security debt to product OKRs and customer SLA risk to enable portfolio-level prioritisation.<br>• Ensure policy exemptions are time-bound, formally risk-accepted by accountable owners, and visible within the GRC system. |

<br>

### BD-02: Safeguard Data

| **Business Driver** | Safeguard Data |
|------|-------------|
| **ID** | BD-02 |
| **Statement** | Protect customer, partner, and operational data across all states with unified governance, lawful processing, and verifiable control effectiveness. |
| **Rationale** | Modern platforms process sensitive telemetry, identifiers, and proprietary data. Trust depends on robust protection and demonstrable privacy controls. A unified data strategy that harmonises classification, encryption, access governance, lineage, and retention enables analytics and data sharing without leakage or unlawful processing. |
| **Security Implementation** | • Implement tiered data classification (Public, Internal, Confidential, Restricted) that drives encryption strength, access policies, and retention rules across cloud and on-prem environments.<br>• Use envelope encryption with centralised key custody (HSM / Key Vault), short key rotation windows, dual-control for key access, and hardware roots of trust for critical secrets.<br>• Apply field-level protections such as masking and tokenisation for PII and sensitive telemetry exposed to analytics or downstream consumers. |
| **Operational Execution** | • Define Data Owners per domain and automate approval workflows for access requests; log and review access patterns through UEBA/SIEM for anomalous behaviour.<br>• Embed data retention and deletion jobs into data pipelines; validate effectiveness through periodic “right-to-erasure” and “prove delete” exercises.<br>• Operate a privacy incident process integrated with Incident Response to assess scope, notify stakeholders, and execute remediation timelines. |
| **Business & Governance** | • Maintain evidence of lawful basis, consent records, and DPIAs within the GRC system.<br>• Run quarterly control effectiveness reviews covering encryption coverage, access review completion, and erasure SLAs to demonstrate continuous compliance.<br>• Tie data protection KPIs to customer trust, regulatory standing, and contract renewals to reinforce competitive differentiation. |

<br>

### BD-03: Enhance Customer & User Experience

| **Business Driver** | Enhance Customer & User Experience |
|------|-------------|
| **ID** | BD-03 |
| **Statement** | Design security to be adaptive and unobtrusive so that protection strengthens trust without degrading usability. |
| **Rationale** | Excessive user friction increases abandonment and support costs. Adaptive, risk-based controls maintain smooth user journeys while increasing assurance where risk is higher. Privacy transparency, clear consent, and self-service options transform security from a hurdle into a feature that customers value. |
| **Security Implementation** | • Use standardised OAuth/OIDC flows with strong session management, token binding where supported, and short-lived tokens with continuous re-authentication for sensitive actions.<br>• Instrument user experience flows for security telemetry (failed authentication, anomalous behaviour) feeding UEBA/SIEM without collecting unnecessary personal data.<br>• Adopt adaptive MFA based on contextual risk signals such as device posture, geo-velocity, and behavioural anomalies, applying step-up authentication only when required. |
| **Operational Execution** | • Provide self-service credential recovery and access request workflows with defined guardrails to reduce ticket volume while maintaining strong assurance.<br>• Use canary releases and feature flags for new security flows; A/B test to balance user friction against risk reduction and capture satisfaction metrics tied to security changes.<br>• Ensure customer support tooling enforces least privilege and provides auditable troubleshooting capabilities. |
| **Business & Governance** | • Publish transparent privacy notices and consent records; surface purpose and retention information in customer-facing portals where applicable.<br>• Include experience-focused security metrics (authentication success rates, average step-ups, abandonment ratios) in governance dashboards to continuously calibrate policies.<br>• Align contractual SLAs for availability and incident response with customer expectations reinforced by secure and usable experiences. |

<br>

### BD-04: Cloud First Enablement

| **Business Driver** | Cloud First Enablement |
|------|-------------|
| **ID** | BD-04 |
| **Statement** | Leverage cloud elasticity and automation while preserving consistent governance and control parity with on-premises estates. |
| **Rationale** | Cloud platforms accelerate feature delivery and global reach, but materially increase misconfiguration and exposure risk. Standardised landing zones and guardrails ensure that speed and safety remain aligned. Security baselines must be codified as policy-as-code and infrastructure-as-code to ensure repeatability, consistency, and auditability across regions and accounts. |
| **Security Implementation** | • Deploy secure cloud landing zones with enforced network segmentation, identity boundaries, centralised logging, and key management by default.<br>• Use policy-as-code to block non-conformant resources at creation; validate infrastructure-as-code pre-deployment using security scanners and detect configuration drift post-deployment.<br>• Adopt managed cloud services with shared responsibility models clearly documented and integrate service hardening guidance into reusable golden modules. |
| **Operational Execution** | • Operate a central cloud enablement function with a defined platform “paved road”; provide reusable modules and service catalogues, and review exceptions through an architecture governance forum.<br>• Implement continuous security posture management (CSPM) feeding the SOC and enterprise risk dashboards; ensure remediation owners are assigned, tracked, and measured.<br>• Coordinate FinOps and SecOps activities to right-size resources, reduce waste, and retire unused assets identified through telemetry. |
| **Business & Governance** | • Demonstrate compliance equivalence across regions, including data residency and sovereignty requirements, and maintain assurance packages to support customer and regulator audits.<br>• Publish periodic conformance scores and exception registers to leadership, linking deviations to formal risk acceptance where applicable.<br>• Quantify cost avoidance achieved through automated policy enforcement and remediation to evidence return on investment. |

<br>

### BD-05: Build Resilience

| **Business Driver** | Build Resilience |
|------|-------------|
| **ID** | BD-05 |
| **Statement** | Engineer for graceful degradation, rapid recovery, and assured continuity under cyber events and infrastructure faults. |
| **Rationale** | Downtime directly erodes brand trust, safety, and revenue. Designing for failure through redundancy, segmentation, and automated recovery protects customer SLAs and business-critical services. Resilience spans both technology and process, including backups, disaster recovery patterns, chaos testing, and crisis communications. |
| **Security Implementation** | • Architect multi-region deployments for critical services and isolate blast radius through micro-segmentation and rate-limiting at architectural choke points.<br>• Encrypt and regularly test backups through restore drills; maintain immutable backup copies segmented from production identity and network domains.<br>• Codify runbooks and playbooks for ransomware, credential compromise, and data exfiltration; simulate attacks to validate control effectiveness and recovery timelines. |
| **Operational Execution** | • Maintain a 24x7 Security Operations capability with clearly defined escalation paths to Incident Response, Legal, and Communications functions; run quarterly cross-functional exercises using realistic scenarios.<br>• Track service dependency maps and service-level objectives; ensure capacity headroom for failover and monitor disaster recovery readiness as a standing KPI.<br>• Integrate supplier failure modes and third-party contingencies into enterprise continuity and recovery planning. |
| **Business & Governance** | • Report resilience posture metrics (RTO/RPO attainment, exercise outcomes, recovery success rates) to executive leadership and align with regulatory and operational resilience obligations.<br>• Embed resilience criteria into product go-live and change approval processes; block release where recovery objectives cannot be met under defined failure modes.<br>• Quantify avoided downtime and incident cost to demonstrate the business value of resilience investments. |

<br>

### BD-06: Optimise Cost

| **Business Driver** | Optimise Cost |
|------|-------------|
| **ID** | BD-06 |
| **Statement** | Invest in controls that deliver measurable risk reduction and operational efficiency; automate wherever repeatable. |
| **Rationale** | Security investment must demonstrably reduce risk and support business outcomes. Instrumentation enables data-driven prioritisation, while automation and consolidation reduce tooling overlap, human error, and operational overhead. Cost efficiency is achieved by focusing spend where it produces the greatest marginal risk reduction. |
| **Security Implementation** | • Consolidate security telemetry into a unified SIEM to reduce licence duplication and operational complexity; rationalise agents and scanners to a minimal, effective set.<br>• Automate low-risk approvals, account lifecycle actions, and standard remediation tasks using SOAR and workflow orchestration engines.<br>• Define and track control efficacy metrics (e.g., prevented misconfigurations, blocked high-risk deployments, automated remediations) to inform future investment decisions. |
| **Operational Execution** | • Establish a FinSecOps operating cadence aligning Finance, Security Operations, and Platform teams to regularly review cost versus risk outcomes and optimise allocations.<br>• Introduce show-back or charge-back models for security services to drive responsible consumption and architectural discipline across product teams.<br>• Publish quarterly ROI narratives alongside KPI dashboards to sustain executive sponsorship and transparency. |
| **Business & Governance** | • Tie security spend directly to movement in the risk register and SLA outcomes; present scenarios demonstrating marginal risk reduction per unit of investment.<br>• Ensure tooling and platform choices support exit strategies to avoid vendor lock-in and preserve negotiating leverage.<br>• Codify deprecation plans for redundant or low-value tools with measurable milestones and accountable owners. |



