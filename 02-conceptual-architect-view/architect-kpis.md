# Recommended KPIs - Conceptual / Architect View

This page defines **architecture-level Key Performance Indicators (KPIs)** aligned to the **Conceptual / Architect View** of the SABSA framework.

These KPIs measure **adoption, effectiveness, and consistency of security principles** across the enterprise and provide early indicators of architectural drift or maturity gaps.

---

## Security Principle KPIs

| Category | Metric | Purpose / Outcome |
|--------|--------|-------------------|
| **Zero Trust (SEC-01)** | % of systems enforcing continuous MFA and conditional access | Confirms adoption of Zero Trust principles across identities, devices, and access points. |
| **Defence in Depth (SEC-02)** | % of critical assets protected by at least three independent defensive layers | Verifies redundancy and coverage within the layered defence architecture. |
| **Data Protection & Privacy (SEC-03)** | % of classified data encrypted with validated key management | Demonstrates compliance with privacy-by-design and data-protection principles. |
| **Application Security (SEC-04)** | % of critical vulnerabilities remediated within defined SLAs | Confirms maturity of secure SDLC and DevSecOps practices. |
| **Risk-Based Security (SEC-05)** | % of high-impact risks treated or formally accepted within governance timelines | Validates prioritisation discipline and risk-treatment effectiveness. |
| **Continuous Monitoring (SEC-06)** | % of telemetry coverage across IT, OT, and cloud environments | Ensures detection completeness and situational awareness. |
| **Automation & Orchestration (SEC-07)** | % of repeatable security tasks automated via orchestration and infrastructure-as-code | Measures operational efficiency and consistency in control execution. |
| **Transparency & Governance (SEC-08)** | % of compliance reports generated automatically and reviewed on a defined cadence | Ensures continuous assurance and stakeholder visibility. |

---

## Governance Notes

- These KPIs are **architecture-aligned**, not tool-specific.
- Metrics should be:
  - Defined consistently across domains
  - Collected automatically where feasible
  - Reviewed through architecture and risk governance forums
- KPI thresholds and targets should evolve as maturity increases.

---

## Traceability

Conceptual KPIs must be traceable to:

- Contextual Business Drivers and risk appetite
- Logical control objectives and design patterns
- Management dashboards and executive reporting

KPIs that cannot be traced to a security principle or architectural decision should be retired.
