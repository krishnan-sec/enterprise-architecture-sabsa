# Enterprise Architecture Framework  
## SABSA-Aligned

## Purpose

This repository defines an **Enterprise Architecture (EA) Framework** aligned with **SABSA**, intended to provide a **security-led architectural operating model** for enterprise environments.

The primary purpose of this framework is to ensure that:
- Security architecture is **explicitly driven by business objectives and risk**
- Architectural decisions are **traceable, defensible, and repeatable**
- Security controls are **measurable and continuously governed**
- Strategy, design, implementation, and operations remain **cohesively aligned**

This framework deliberately positions security as a **core architectural concern**, not a downstream technical function.

---

## Architectural Positioning

Within this framework, Enterprise Architecture is treated as:

- A **decision-support discipline** for business and technology leadership  
- A **translation mechanism** between business risk and technical controls  
- A **continuous system**, validated through operational telemetry and outcomes  

Security is not approached as a collection of tools or controls.  
It is addressed as an **architectural discipline** that spans strategy, design, execution, and governance.

---

## SABSA View Model

The framework adopts the SABSA layered model and expresses it through six Enterprise Architecture views.  
Each view answers a distinct architectural question and produces authoritative outputs.

| SABSA View | WHAT (Assets) | WHY (Motivation) | HOW (Process) | WHO (People) | WHERE (Location) | WHEN (Time) |
|-----------|---------------|------------------|---------------|-------------|------------------|-------------|
| **Contextual (Business)** | Business Services & Critical Functions | Business Objectives & Risk Appetite | Business Processes | Roles & Ownership | Business Locations | Business Timing |
| **Conceptual (Architect)** | Information Assets & Asset Classes | Security Principles & Risk Posture | Security Capabilities | Trust Relationships | Trust Zones | Risk Windows |
| **Logical (Designer)** | Data Domains & Data Flows | Control Objectives | Control Logic & Policy Models | Identity Models | Logical Zones | Control Triggers |
| **Physical (Builder)** | Databases / Storage Platforms | Enforcement Goals | Security Services | IAM Platforms | Network / Cloud Segments | Scheduled / Real-Time |
| **Component (Tradesman)** | Tables, Files, Records | Detection & Validation | Configurations & Queries | Accounts, Roles, Policies | Hosts, Endpoints, Sensors | Events, Alerts, Signals |
| **Management (Manager)** | Asset Inventories & Ownership | Risk Treatment & Exceptions | Governance & Assurance Processes | Accountability & Decision Authorities | Organisational & Jurisdictional Scope | Review Cycles & Continuous Improvement |



Each view is **independent in responsibility**, yet **fully traceable** across the architecture lifecycle.

---

## Architectural Structure

The repository is organised according to these architectural views:

1. [Contextual - Business View](01-contextual-business-view/README.md)
2. [Conceptual - Architect View](02-conceptual-architect-view/README.md)
3. [Logical - Designer View](03-logical-designer-view/README.md)
4. [Physical - Builder View](04-physical-builder-view/README.md)
5. [Component - Tradesman View](05-component-tradesman-view/README.md)
6. [Management - Manager View](06-management-manager-view/README.md)

Each directory contains the **authoritative architectural artifacts** for that view and serves as the single source of truth for related decisions.

---

## Architectural Principles

This framework is guided by a defined set of architectural principles that govern all security decisions:

- Security decisions are **business-driven**
- Risk is the **primary prioritisation mechanism**
- Controls are designed with **defence in depth**
- Trust is **explicit, contextual, and continuously evaluated**
- Architecture is **validated through operational telemetry**
- Continuous improvement is **mandatory, not optional**

Formal definitions and rationale for each principle are maintained in the **Conceptual / Architect View**.

---

## Traceability Model

A core requirement of this framework is **end-to-end traceability** across all architectural layers:

```
Business Objectives
   ↓
Business Risks
   ↓
Security Principles
   ↓
Logical Designs
   ↓
Physical Controls
   ↓
Telemetry & Detection
   ↓
Response & Improvement
```

This traceability is **non-negotiable** and applies to all architectural decisions, exceptions, and changes.

---

## Intended Use

This framework is designed to be used by:

- Enterprise and security architects  
- Cloud, platform, and infrastructure engineering teams  
- Security operations and detection engineering functions  
- Governance, risk, and compliance stakeholders  
- Executive and senior technical leadership  

It provides a **shared architectural language** across strategic, design, and operational domains.

---

## Architectural Baseline Statement

Security architecture decisions are driven by business risk, implemented through deliberate design, and continuously validated through operational telemetry.
