# Recommended KPIs - Physical / Builder View

This page defines **physical implementation-level Key Performance Indicators (KPIs)** aligned to the **Physical / Builder View** of the SABSA framework.

These KPIs measure **control enforcement, operational reliability, and technical effectiveness** across implemented security services and platforms.

---

## Physical Control KPIs

| Category | Metric | Purpose / Outcome |
|--------|--------|-------------------|
| **Identity & Access Management** | % of privileged accounts under privileged access management (PAM/PIM) control | Ensures elevated access is governed, monitored, and time-bound. |
| **Network Security** | % of critical firewalls and network security groups with reviewed and approved rules | Confirms controlled connectivity and adherence to least-connectivity principles. |
| **Data Protection** | % of key-rotation and backup-encryption tests passed | Validates confidentiality, integrity, and reliability of cryptographic controls. |
| **Monitoring & Detection Tools** | % of telemetry sources feeding centralised monitoring platforms | Confirms visibility coverage and detection completeness. |
| **Automation & Orchestration** | % of incidents remediated automatically | Measures automation effectiveness and reduction in manual operational effort. |
| **Risk Assessment Tools** | % of high-risk findings closed within defined SLAs | Demonstrates continuous risk mitigation and vulnerability management performance. |
| **Compliance & Reporting** | % of compliance controls validated through automation | Shows alignment with regulatory frameworks and audit readiness. |

---

## Governance Notes

- Physical KPIs focus on **control enforcement**, not design intent.
- Metrics should:
  - Be collected directly from operational platforms
  - Be validated regularly for accuracy and completeness
  - Feed logical, conceptual, and management reporting layers
- KPI thresholds should reflect service criticality and risk exposure.

---

## Traceability

Physical KPIs must be traceable to:

- Logical control designs and objectives
- Component-level operational execution
- Management risk and performance reporting

Metrics that cannot be traced to a physical control or service should be retired.
