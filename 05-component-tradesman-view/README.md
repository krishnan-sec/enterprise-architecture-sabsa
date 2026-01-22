# Component - Tradesman View

## Purpose

The Component / Tradesman View defines **how physical security controls are implemented, configured, and operated at the component level**.

This view contains the **executable artifacts** that enforce security across the enterprise, including configurations, detection logic, queries, playbooks, scripts, and runbooks.

It answers the question:  
**“How are controls actually built, deployed, and operated day to day?”**

---

## Architectural Scope

This view focuses on **implementation-level artifacts**, including:

- Platform configurations and baselines
- Detection logic and analytics queries
- Automation playbooks and response workflows
- Security-as-code artifacts (policy, IaC, detections)
- Operational runbooks and procedures

This view is **explicitly constrained** by the Physical / Builder View and must not introduce new control intent or architecture decisions.

---

## Relationship to Other Views

The Component / Tradesman View is the **execution layer** of the architecture:

- It **implements physical controls** defined in the Physical / Builder View
- It **inherits logical intent** from the Logical / Designer View
- It **must align with principles** defined in the Conceptual / Architect View
- It **provides evidence and telemetry** to the Management / Manager View

Any component that cannot be traced upward is considered non-compliant.

---

## Component Domains

Component artifacts are organised according to the physical control they implement.

---

### CO-01: Governance & Ownership

| **Component & Operational** | Governance & Ownership |
|------|-------------|
| **ID** | CO-01 |
| **Statement** | Establish clear accountability and ownership for all security controls, ensuring every domain and capability has explicitly defined Responsible, Accountable, Consulted, and Informed (RACI) roles. |
| **Rationale** | Clear governance prevents fragmented or duplicated responsibility and ensures controls are consistently operated and maintained. Formal ownership enables continuous oversight, measurable performance, and effective escalation when control effectiveness degrades. |
| **Security Implementation** | • Define and document RACI matrices for all security domains and control families, assigning ownership at both control and process levels.<br>• Integrate governance roles into governance, risk, and compliance workflows, mapping ownership to control evidence, approvals, and exception handling.<br>• Maintain governance documentation in version-controlled repositories and review it on a defined cadence to reflect organisational and architectural changes. |
| **Operational Execution** | • Conduct regular governance and ownership reviews to validate control accountability and operational adherence.<br>• Update RACI assignments following organisational change, outsourcing decisions, or platform ownership transitions.<br>• Track control ownership coverage and compliance through automated dashboards, highlighting unassigned, overdue, or conflicting responsibilities. |
| **Business & Governance** | • Strengthen audit defensibility by demonstrating clear, traceable ownership for every control and operational process.<br>• Improve coordination between business, technology, security, and compliance functions through explicitly defined accountability.<br>• Embed governance discipline as a measurable business capability, ensuring security decisions are risk-informed and consistently executed. |

<br>

### CO-02: Configuration & Change Management

| **Component & Operational** | Configuration & Change Management |
|------|-------------|
| **ID** | CO-02 |
| **Statement** | Implement automated, auditable configuration and change-management mechanisms that preserve system integrity, enforce approved baselines, and minimise human error. |
| **Rationale** | Configuration drift and uncontrolled change introduce avoidable vulnerabilities and operational instability. Codified configuration and governed change processes ensure consistency, resilience, and continuous compliance across environments. |
| **Security Implementation** | • Enforce infrastructure-as-code and configuration-as-code for all systems, embedding security baselines that are validated during pre-deployment testing.<br>• Continuously assess system configurations against hardened standards using automated compliance and posture validation mechanisms.<br>• Integrate mandatory change-approval workflows with risk scoring, rollback capability, and segregation of duties to control high-impact changes. |
| **Operational Execution** | • Maintain a version-controlled configuration baseline repository with peer review and approval for all authorised templates and changes.<br>• Run automated configuration compliance checks on a defined cadence, routing deviations to accountable owners for remediation.<br>• Perform post-change validation to confirm rollback readiness, configuration stability, and documentation accuracy. |
| **Business & Governance** | • Ensure continuous adherence to internal configuration standards and external regulatory requirements through enforceable controls.<br>• Reduce downtime, incidents, and operational disruption caused by unauthorised or erroneous changes.<br>• Provide immutable, auditable evidence of configuration integrity to support assurance activities and certifications. |

<br>

### CO-03: Incident Response & Recovery

| **Component & Operational** | Incident Response & Recovery |
|------|-------------|
| **ID** | CO-03 |
| **Statement** | Establish a coordinated incident response and recovery capability that enables rapid containment, eradication, and service restoration while minimising business impact. |
| **Rationale** | Timely detection, coordinated response, and effective recovery are essential to limit disruption, protect reputation, and maintain stakeholder trust. An integrated incident response and recovery model ensures preparedness, consistency, and cross-functional coordination under pressure. |
| **Security Implementation** | • Define incident severity levels, escalation criteria, and communication protocols aligned to recognised incident management standards.<br>• Implement automated containment and response actions through orchestration platforms to isolate affected assets, preserve evidence, and reduce dwell time.<br>• Maintain tested recovery playbooks covering cyber incidents, insider threats, and operational outages, validated through regular simulation exercises. |
| **Operational Execution** | • Operate a 24×7 incident response capability integrated with security operations, legal, communications, and business continuity functions.<br>• Conduct regular tabletop, technical, and disaster recovery exercises to validate readiness, coordination, and restoration timelines.<br>• Produce post-incident reviews documenting root cause, control gaps, lessons learned, and tracked improvement actions. |
| **Business & Governance** | • Demonstrate alignment with continuity, resilience, and incident management expectations through validated response and recovery processes.<br>• Protect brand reputation and financial stability by reducing incident impact and recovery time.<br>• Provide auditable evidence of incident handling maturity during assurance, audit, and due-diligence activities. |

<br>

### CO-04: Threat Intelligence & Analytics

| **Component & Operational** | Threat Intelligence & Analytics |
|------|-------------|
| **ID** | CO-04 |
| **Statement** | Integrate internal and external threat intelligence into monitoring, detection, and decision workflows to anticipate, prioritise, and neutralise emerging cyber risks. |
| **Rationale** | Intelligence-led defence shifts security operations from reactive to proactive. Contextual threat intelligence enables earlier warning, informed prioritisation, and adaptive control tuning based on evolving adversary behaviour and exposure. |
| **Security Implementation** | • Ingest and normalise relevant external and internal threat intelligence sources, including sector, supply-chain, and government advisories, integrating them into detection and risk models.<br>• Enrich security events with intelligence context such as tactics, techniques, procedures (TTPs), indicators of compromise (IOCs), and vulnerability references to improve correlation and prioritisation.<br>• Automate the transformation of validated intelligence into detection logic, hunting queries, and preventative controls using detection-as-code practices. |
| **Operational Execution** | • Conduct regular threat intelligence review cycles to assess relevance, validate sources, and adjust detection and response logic accordingly.<br>• Continuously measure intelligence efficacy by tracking alert quality, coverage improvements, and false-positive reduction.<br>• Correlate intelligence insights with vulnerability, exposure, and risk data to maintain visibility across the attack surface. |
| **Business & Governance** | • Reduce exposure to emerging threats, zero-day vulnerabilities, and supply-chain risk through proactive intelligence-driven prioritisation.<br>• Demonstrate alignment with recognised threat intelligence and resilience expectations through documented processes and evidence.<br>• Build executive and stakeholder confidence by showing data-driven anticipation of threats rather than reactive response alone. |

<br>

### CO-05: Continuous Improvement & Metrics

| **Component & Operational** | Continuous Improvement & Metrics |
|------|-------------|
| **ID** | CO-05 |
| **Statement** | Establish a structured continuous improvement framework that measures, reviews, and enhances the effectiveness of security controls over time. |
| **Rationale** | Security controls must evolve alongside changing business priorities and threat landscapes. Measurement and continuous improvement ensure that controls remain effective, relevant, and aligned with organisational objectives rather than becoming static or compliance-driven. |
| **Security Implementation** | • Define key performance indicators (KPIs) and key risk indicators (KRIs) mapped to architectural layers and control domains, with automated data collection from monitoring and governance systems.<br>• Conduct periodic capability and maturity assessments using recognised models to benchmark progress and identify improvement opportunities.<br>• Implement feedback loops where insights from incidents, audits, exercises, and metrics drive prioritised improvement initiatives and roadmap updates. |
| **Operational Execution** | • Produce regular security performance reports reviewed through defined governance forums to assess trends, gaps, and improvement outcomes.<br>• Validate metric accuracy and context before executive reporting to support informed decision making.<br>• Track improvement initiatives with accountable owners, milestones, and follow-up actions to ensure measurable progress. |
| **Business & Governance** | • Enable evidence-based prioritisation of security investments and resource allocation.<br>• Demonstrate measurable improvement and due diligence to regulators, customers, and insurers.<br>• Position security as a continuous value enabler through transparent measurement and accountability. |


