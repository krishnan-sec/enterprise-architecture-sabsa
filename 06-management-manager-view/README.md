# Management - Manager View

## Purpose

The Management / Manager View defines **how security architecture is governed, measured, funded, and continuously improved**.

This view ensures that security is treated as a **managed business capability**, not a collection of technical controls. It translates architectural outcomes into **leadership decisions, accountability models, performance metrics, and investment roadmaps**.

It answers the question:  
**“How is security effectiveness governed, measured, and sustained over time?”**

---

## Architectural Scope

This view focuses on:

- Security leadership and decision-making structures
- Governance, risk, and assurance oversight
- Performance measurement and reporting
- Policy, standard, and exception management
- Strategic planning and maturity roadmaps
- Investment prioritisation and accountability

Technical implementation details are **explicitly out of scope**.

---

## Relationship to Other Views

The Management / Manager View provides **oversight and direction** across the architecture:

- It **consumes telemetry and evidence** from the Component / Tradesman View
- It **validates control effectiveness** implemented in the Physical / Builder View
- It **measures outcomes** against Logical and Conceptual objectives
- It **ensures alignment** with business drivers defined in the Contextual View

No architectural decision is considered complete until it is governed and measured here.

---

## Management Control Domains

Management controls are organised into the following domains.

---

### MG-01: Security Leadership & Oversight

| **Management & Governance** | Security Leadership & Oversight |
|------|-------------|
| **ID** | MG-01 |
| **Statement** | Establish a formal security leadership and oversight model, chaired by executive security leadership, to govern security strategy, risk posture, and architectural decisions across the enterprise. |
| **Rationale** | Strong leadership and structured oversight ensure that security architecture remains aligned with business objectives, regulatory expectations, and an evolving threat landscape. Clear decision authority and accountability prevent fragmented strategy and inconsistent execution. |
| **Security Implementation** | • Formally define the charter, membership, and decision-making authority of the security architecture and risk governance forums.<br>• Integrate architectural and security reviews into change, investment, and portfolio governance processes to ensure initiatives meet security-by-design expectations.<br>• Maintain version-controlled security architecture documentation reviewed on a defined cadence to ensure relevance, accuracy, and completeness. |
| **Operational Execution** | • Conduct regular governance forums with cross-functional participation from technology, engineering, risk, legal, and compliance stakeholders.<br>• Record, track, and publish architectural and security decisions in a central governance repository with clearly assigned action owners.<br>• Review major incidents, risk posture changes, and emerging threats as standing agenda items to enable timely and informed leadership decisions. |
| **Business & Governance** | • Provide a single, accountable authority for enterprise security direction and architectural integrity.<br>• Ensure consistency in security strategy execution across programs, platforms, and partners.<br>• Strengthen executive and board confidence through demonstrable oversight, traceable decisions, and measurable outcomes. |

<br>

### MG-02: Policy & Standard Lifecycle Management

| **Management & Governance** | Policy & Standard Lifecycle Management |
|------|-------------|
| **ID** | MG-02 |
| **Statement** | Maintain a structured, living framework of cybersecurity policies, standards, and baselines that evolve in response to changing business needs, risk exposure, and technology. |
| **Rationale** | Policies and standards translate architectural intent into enforceable guidance and operational consistency. Regular review and controlled updates ensure alignment between documented expectations and real-world implementation as environments and threats evolve. |
| **Security Implementation** | • Develop and categorise security documentation—including policies, standards, procedures, and guidelines—mapped to recognised control frameworks.<br>• Enforce standards through policy-as-code mechanisms integrated into platforms and delivery pipelines to ensure consistent compliance.<br>• Establish formal review, approval, and versioning processes so all policies are assessed on a defined cadence or upon significant regulatory or architectural change. |
| **Operational Execution** | • Manage policy exceptions through a centralised waiver process that includes documented risk acceptance, compensating controls, and expiry dates.<br>• Maintain accessible, authoritative repositories for current policy and standard documentation, supported by awareness and enablement activities.<br>• Require technical teams to validate configurations, deployments, and changes against the latest approved standards. |
| **Business & Governance** | • Demonstrate compliance with legal, regulatory, and contractual obligations through clear, current, and enforceable documentation.<br>• Improve audit efficiency and reduce control ambiguity across teams through consistent and well-governed standards.<br>• Enable adaptive governance by ensuring security expectations evolve alongside business growth and technology adoption. |

<br>

### MG-03: Risk & Performance Reporting

| **Management & Governance** | Risk & Performance Reporting |
|------|-------------|
| **ID** | MG-03 |
| **Statement** | Provide integrated dashboards and executive reporting that link cybersecurity risk, control performance, and business impact to support informed decision making. |
| **Rationale** | Transparent, accurate risk visibility enables leadership to prioritise investments, allocate resources effectively, and demonstrate measurable improvement in security posture over time. |
| **Security Implementation** | • Design role-based dashboards that aggregate data from risk, monitoring, and compliance systems to present real-time posture and residual risk.<br>• Automate data collection, validation, and reporting pipelines to reduce manual effort and reporting errors while improving timeliness.<br>• Define standardised reporting views for tactical, operational, and strategic audiences to ensure consistency and comparability. |
| **Operational Execution** | • Conduct regular operational reviews of risk metrics, KPIs, and KRIs within established security governance forums.<br>• Validate dashboard accuracy through periodic sampling and reconciliation against source systems.<br>• Deliver executive and board-level briefings that summarise risk trends, control effectiveness, and return on security investment. |
| **Business & Governance** | • Align security risk reporting with corporate objectives, enterprise risk management, and regulatory disclosure expectations.<br>• Enable leadership to track progress in reducing residual risk and improving control effectiveness.<br>• Reinforce accountability by linking governance metrics to ownership, performance objectives, and investment decisions. |

<br>

### MG-04: Workforce Enablement & Culture

| **Management & Governance** | Workforce Enablement & Culture |
|------|-------------|
| **ID** | MG-04 |
| **Statement** | Develop and sustain a security-aware culture that empowers employees, contractors, and partners to act as proactive defenders of information assets. |
| **Rationale** | People are both the strongest defence and the most common source of risk. A security-conscious workforce reduces human error, insider threats, and policy violations while strengthening organisational resilience. |
| **Security Implementation** | • Implement role-based security awareness programs combining e-learning, simulations, and targeted training for technical staff, business users, and leadership.<br>• Integrate just-in-time learning and contextual security prompts into enterprise applications to reinforce secure behaviour at the point of decision.<br>• Maintain centralised tracking of training completion, effectiveness metrics, and coverage across organisational roles and business units. |
| **Operational Execution** | • Conduct periodic phishing simulations and behavioural analytics to measure risk awareness and improvement trends.<br>• Partner with human resources to embed security expectations into onboarding, role changes, and performance review processes.<br>• Continuously update awareness content to reflect new threats, technologies, and regulatory requirements. |
| **Business & Governance** | • Improve overall security posture by reducing policy violations, preventable incidents, and human-driven risk.<br>• Demonstrate compliance with recognised standards through measurable awareness, training coverage, and competency evidence.<br>• Foster a security-first mindset that strengthens customer confidence, partner trust, and internal accountability. |

<br>

### MG-05: Strategic Maturity Roadmaps

| **Management & Governance** | Strategic Maturity Roadmaps |
|------|-------------|
| **ID** | MG-05 |
| **Statement** | Define and maintain a multi-year cybersecurity maturity roadmap that guides the evolution from reactive controls to predictive, risk-informed security capabilities. |
| **Rationale** | A structured maturity roadmap aligns investment, resource planning, and architectural evolution with business strategy. It ensures that security capabilities grow deliberately, sustainably, and in proportion to risk and organisational priorities. |
| **Security Implementation** | • Use recognised maturity and capability frameworks to baseline current security capabilities and define target maturity levels by domain.<br>• Align roadmap milestones with business objectives, regulatory expectations, and threat trends, incorporating funding forecasts and dependencies.<br>• Integrate roadmap planning with enterprise architecture, transformation initiatives, and technology modernisation programs. |
| **Operational Execution** | • Review roadmap progress on a defined cadence within security and architecture governance forums, documenting achieved milestones and upcoming priorities.<br>• Re-baseline maturity periodically using objective assessments, internal reviews, and independent assurance where appropriate.<br>• Adjust timelines and sequencing in response to emerging threats, regulatory change, or shifts in technology and business strategy. |
| **Business & Governance** | • Provide executives with a forward-looking view of the organisation’s security transformation trajectory and expected outcomes.<br>• Support sustained funding decisions by mapping improvement initiatives to measurable risk reduction and capability gains.<br>• Ensure security posture evolves predictably and transparently, maintaining resilience, compliance, and competitive confidence over time. |



