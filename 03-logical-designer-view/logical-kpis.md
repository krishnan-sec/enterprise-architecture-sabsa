# Recommended KPIs - Logical / Designer View

This page defines **logical design-level Key Performance Indicators (KPIs)** aligned to the **Logical / Designer View** of the SABSA framework.

These KPIs validate that **logical control designs are implemented consistently, operate as intended, and support architectural principles**.

---

## Logical Control KPIs

| Category | Metric | Purpose / Outcome |
|--------|--------|-------------------|
| **Access Control** | % of accounts protected by multi-factor authentication | Confirms consistent adoption of identity verification mechanisms aligned to Zero Trust design. |
| **Network Segmentation** | % of verified segmentation policy compliance | Validates isolation effectiveness and prevents unauthorised lateral movement between zones. |
| **Data Security** | % of classified assets encrypted at rest and in transit | Demonstrates enforcement of confidentiality and data governance requirements. |
| **Monitoring & Analytics** | Mean Time to Detect (MTTD) / Mean Time to Respond (MTTR) | Measures detection responsiveness and operational effectiveness of monitoring designs. |
| **Automation Framework** | % of automated remediation and playbook success rate | Quantifies reliability and maturity of automated control execution. |
| **Risk Management** | % of critical risks mitigated within defined SLAs | Confirms proactive risk treatment and alignment between design and governance expectations. |
| **Transparency & Reporting** | % of evidence items updated and validated on a defined cadence | Validates continuous compliance readiness and reporting accuracy. |

---

## Governance Notes

- Logical KPIs measure **design effectiveness**, not tool performance.
- Metrics should:
  - Be derived from physical and component telemetry
  - Be reviewed in architecture and risk governance forums
  - Highlight design gaps before they become incidents
- KPI thresholds should increase as control maturity improves.

---

## Traceability

Logical KPIs must be traceable to:

- Conceptual security principles
- Physical control implementations
- Management reporting and risk governance

Metrics that cannot be traced to a logical control objective should be retired.
