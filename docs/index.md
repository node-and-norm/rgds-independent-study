# RGDS: Decision-Centric AI Governance in Biopharma/Biotech Development

*Mark Julius Banasihan · Independent Research · November 2025 – January 2026*

[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20242004-blue)](https://doi.org/10.5281/zenodo.20242004)

---

!!! info "Regulatory Status — January 2026"
    FDA's January 2025 draft guidance requires documented human oversight of AI-assisted regulatory submissions. Broader decision governance remains voluntary. This study projects a Phase 1 voluntary incentive structure (2026–27) transitioning to an anticipated mandate for AI-assisted decisions (2027–28), based on FDA's regulatory trajectory and international harmonization patterns. See [Q10](questions/q10.md) for the full analysis.

---

## The Problem

FDA Complete Response Letters cite "insufficient information" in 50% of first-cycle submissions[[1]](references/bibliography/#cite1)[[2]](references/bibliography/#cite2)[[3]](references/bibliography/#cite3). In most of those cases, the science is defensible. What organizations cannot provide is a coherent account of *why* specific decisions were made 6–18 months earlier. The decision logic that once existed in email threads, meeting notes, and individual memory cannot be reconstructed under inspection pressure.

This reconstructability failure costs biopharma organizations an average of 2–4 weeks per FDA question during deficiency letter response cycles, $300K–$500K per clinical hold (8.9% baseline IND hold rate), and 6–12 months in timeline extensions when holds require substantive remediation[[2]](references/bibliography/#cite2)[[3]](references/bibliography/#cite3)[[26]](references/bibliography/#cite26). When organizations produce inconsistent narratives across team members, FDA scrutiny on subsequent submissions increases.

A second challenge compounds the first. AI tools now deliver 35–40% timeline compression in regulatory workflows: medical writing automation (CoAuthor, Yseop, Multiplier AI) reduces Module 2.6 authoring from 180 hours to 80 hours[[4]](references/bibliography/#cite4)[[5]](references/bibliography/#cite5)[[6]](references/bibliography/#cite6); regulatory intelligence platforms scan 200+ IND submissions for hepatic clearance precedent in hours[[7]](references/bibliography/#cite7)[[8]](references/bibliography/#cite8); digital twin simulations predict manufacturing yield with 92% accuracy[[9]](references/bibliography/#cite9). These gains are real. But when FDA asks during inspection "Who reviewed this AI-generated toxicology summary? What was your quality control process?", organizations currently have no systematic answer[[10]](references/bibliography/#cite10)[[11]](references/bibliography/#cite11).

FDA's January 2025 draft guidance on algorithmic decision-making makes this gap a compliance issue, not a theoretical one.

---

## The Framework

**RGDS (Regulated Gate Decision Support)** proposes a single structural response to both problems: treat decisions, not documents, as the primary governance artifact.

A decision log captures six fields at the moment a phase-gate choice is made.

```json
{
  "decision_question": "Proceed to IND submission with incomplete 28-day GLP tox data?",
  "options_considered": [
    "Option A: Defer 4 weeks for final tox report — rejected, conflicts with Series B milestone",
    "Option B: Proceed with audit report and commit to backfill condition"
  ],
  "evidence_base": {
    "completeness": "partial",
    "source": "Study-03 audit report, NOAEL 50 mg/kg; final report expected 2026-01-20"
  },
  "risk_posture": "risk-accepting on timeline; risk-minimizing on data quality",
  "conditions": [
    "C-001: Final GLP tox report received by 2026-01-20",
    "C-002: Exposure metadata backfilled by 2026-01-10"
  ],
  "approvers": ["VP Regulatory Affairs", "Principal AI Business Analyst"]
}
```

Schema validation runs in CI/CD (GitHub Actions) before any decision log merges, ensuring required fields cannot be omitted under time pressure. A decision that cannot satisfy the schema cannot be finalized. The result is 2-minute retrieval of a complete, authoritative record when FDA requests justification months later.

The framework applies a non-agentic AI governance principle. AI tools provide analytical support. Human accountability remains singular, explicit, and documented in the `aiassistance` object embedded in every log where AI contributed.

---

## Core Principles

**Human-governed.** Named humans with expertise and accountability make all decisions. AI accelerates evidence gathering, precedent analysis, and drafting; it does not approve.

**Evidence-linked.** Every decision log references source evidence with completeness classification: complete (final validated data), partial (preliminary data, final pending), or placeholder (estimated or assumed). This makes data gaps explicit before FDA finds them.

**Schema-validated.** Required fields enforce completeness automatically. CI/CD pipeline failures block finalization of incomplete logs.

**Non-agentic.** AI assistance is disclosed in a structured `aiassistance` object recording tool identity, confidence metrics, human reviewer, and override rationale. This maps directly onto FDA's 7-step AI credibility framework.

**Audit-ready.** Decision logs are version-controlled in Git, providing immutable audit trails retrievable in minutes.

---

## Research Questions

This study examines RGDS across ten questions spanning its theoretical foundations and operational implications.

| Question | Focus | Key Finding |
|---|---|---|
| [Q1: Reconstructability](questions/q1.md) | Converting 2–3 week forensic exercises into 2-minute retrieval | Schema-validated contemporaneous logs eliminate decision-documentation findings where consistently used |
| [Q2: AI Accountability](questions/q2.md) | Human oversight documentation for AI-assisted regulatory work | `aiassistance` object satisfies FDA's January 2025 draft guidance while preserving 40–60% efficiency gains |
| [Q3: Integration](questions/q3.md) | Consolidating RACI, risk registers, status meetings into one artifact | Decision logs replace redundant artifacts; they do not add new ones |
| [Q4: FDA Deficiency Prevention](questions/q4.md) | Addressing the 25–30% of CRLs driven by reconstructability gaps | Realistic deficiency rate reduction: 12–25% of total (not 50–75%; governance cannot fix scientific insufficiency) |
| [Q5: Decision Velocity](questions/q5.md) | Compressing 45–90 day phase-gate cycles | Cycle compression to 20–35 days by making assumptions explicit upfront |
| [Q6: Strategic Alignment](questions/q6.md) | Cross-functional consensus on risk posture | Explicit risk-posture field prevents silent assumption conflicts that cost 4–6 weeks of re-litigation |
| [Q7: ROI](questions/q7.md) | Three-tier value framework with confidence stratification | Operational ROI $1.8–2.3M (high confidence); regulatory ROI $22–37M (medium); financial ROI excluded as speculative |
| [Q8: Implementation](questions/q8.md) | 24-month phased adoption roadmap | Pilot validation (months 1–6) before enterprise rollout; 80–90% realistic adoption target |
| [Q9: AI Governance Disclosure](questions/q9.md) | Mapping to FDA's 7-step AI credibility framework | RGDS `aiassistance` object enables compliance at decision time, not retroactively |
| [Q10: Regulatory Trajectory](questions/q10.md) | FDA mandate timeline projection | Phase 1 voluntary incentives (2026–27) → Phase 2 anticipated mandate for AI-assisted decisions (2027–28) |

[Results at a glance →](questions/results-overview.md)

---

## Key Quantitative Findings

**Reconstructability:** Decision reconstruction time from 2–3 weeks to 2 minutes via Git query[[3]](references/bibliography/#cite3). Applies prospectively; does not retroactively fix decisions already made without logs.

**FDA deficiency addressable slice:** 25–30% of CRLs are reconstructability-driven. The remaining 70–75% reflect scientific insufficiency, manufacturing gaps, or clinical data quality. RGDS addresses only the governance slice.

**Operational ROI (high confidence):** $1.8–2.3M for a 5-IND portfolio over 3 years. Clinical hold avoidance $300K–$500K per IND; deficiency response acceleration 60–70%; inspection efficiency $50K–$100K savings per IND.

**Regulatory ROI (medium confidence):** 12–25% reduction in total deficiency rate; 25–35% faster clinical hold resolution. Confidence depends on implementation fidelity and organizational adoption rate.

**Regulatory trajectory:** FDA Phase 2 guidance (2027–28) anticipated to mandate AI governance documentation as Module 1.7 in eCTD submissions. Early adopters avoid retroactive remediation and qualify for Phase 1 inspection waivers ($50K–$200K savings per program).

---

## Scope and Limitations

This study addresses one failure mode: inability to reconstruct decision logic under regulatory scrutiny. It does not address scientific insufficiency, manufacturing quality gaps, or clinical data design. Governance cannot fix bad science.

ROI projections are modeled against a 5-IND portfolio using published benchmarks from Tufts CSDD, Deloitte, McKinsey, and industry analysis. Operational ROI carries high confidence. Regulatory ROI carries medium confidence and depends on implementation fidelity. Financial ROI projections (valuation premiums, M&A uplifts) are excluded from the business case and treated as potential upside.

---

## Contents

- [Research Questions Q1–Q10](questions/index.md)
- [Results Overview](questions/results-overview.md)
- [Bibliography — 96 sources](references/bibliography.md)
- [Appendix A — Financial Analysis and ROI Methodology](references/appendix-a.md)
- [Methods and Technical Notes](references/methods-and-tools.md)
- [About the Author](references/about-the-author.md)
- [Acknowledgements](references/acknowledgements.md)

---

## Related Repositories

- **[rgds](https://github.com/node-and-norm/rgds)** — Decision log schemas (`decision-log.schema.json`), governance covenants, and canonical example logs (RGDS-DEC-0001 through RGDS-DEC-0006)
- **[rgds-ai-governance](https://github.com/node-and-norm/rgds-ai-governance)** — Non-agentic AI governance boundaries and constraints for regulated decision support

Both repositories are licensed under the Apache License 2.0.

---

## Citation

```bibtex
@software{banasihan2026rgds,
  author    = {Banasihan, Mark Julius},
  title     = {{RGDS}: Decision-Centric {AI} Governance in Biopharma/Biotech Development},
  year      = {2026},
  month     = {1},
  version   = {1.4},
  doi       = {10.5281/zenodo.20242004},
  url       = {https://doi.org/10.5281/zenodo.20242004},
  license   = {Apache-2.0}
}
```
