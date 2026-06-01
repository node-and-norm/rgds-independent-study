# RGDS: Regulated Gate Decision Support

**Decision-Centric AI Governance for Biopharma/Biotech Development**

[![Deploy MkDocs](https://github.com/mj3b/rgds-independent-study/actions/workflows/deploy-mkdocs.yml/badge.svg)](https://github.com/mj3b/rgds-independent-study/actions/workflows/deploy-mkdocs.yml)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20242004-blue)](https://doi.org/10.5281/zenodo.20242004)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0001--8121--2878-brightgreen)](https://orcid.org/0009-0001-8121-2878)

---

## Overview

FDA Complete Response Letters cite "insufficient information" in 50% of first-cycle submissions. In most of those cases, the underlying science is defensible—what organizations cannot provide is a coherent account of *why* specific decisions were made 6–18 months earlier. The decision logic that once existed in emails, meeting notes, and individual memory cannot be reconstructed under inspection pressure.

**RGDS (Regulated Gate Decision Support)** addresses this reconstructability crisis by treating decisions, not documents, as the primary governance artifact. The framework provides a schema-validated structure for capturing decision logic at the moment choices are made—recording the question, options considered, evidence completeness, risk posture, contingency, and approvers—so that retrieval under FDA scrutiny takes two minutes rather than two weeks.

This repository documents a ten-question independent study (November 2025 – January 2026) examining RGDS across its core research dimensions: reconstructability, AI accountability, integration overhead, FDA deficiency prevention, decision velocity, strategic alignment, ROI, implementation, disclosure, and regulatory trajectory. The evidence base draws on 96 sources spanning FDA guidance, Tufts CSDD analysis, McKinsey, Deloitte, and peer-reviewed regulatory science.

---

## Research Questions

| # | Question | Focus |
|---|----------|-------|
| [Q1](docs/questions/q1.md) | Decision Reconstructability | Converting 2–3 week forensic exercises into 2-minute retrieval |
| [Q2](docs/questions/q2.md) | AI Accountability | Documenting human oversight of AI-assisted regulatory work |
| [Q3](docs/questions/q3.md) | Integration Without Overhead | Consolidating RACI, risk registers, and status artifacts |
| [Q4](docs/questions/q4.md) | FDA Deficiency Prevention | Addressing the 25–30% of CRLs driven by reconstructability gaps |
| [Q5](docs/questions/q5.md) | Decision Velocity | Compressing 45–90 day phase-gate cycles to 20–35 days |
| [Q6](docs/questions/q6.md) | Strategic Alignment | Forcing cross-functional consensus on risk posture upfront |
| [Q7](docs/questions/q7.md) | ROI Measurement | Three-tier value framework with confidence stratification |
| [Q8](docs/questions/q8.md) | Implementation Roadmaps | 24-month phased adoption with pilot validation gates |
| [Q9](docs/questions/q9.md) | AI Governance Disclosure | Mapping to FDA's 7-step AI credibility framework |
| [Q10](docs/questions/q10.md) | Regulatory Mandate Trajectory | FDA Phase 1 (2026–27) voluntary → Phase 2 (2027–28) likely mandate |

---

## Framework Design

RGDS operates on a non-agentic AI governance principle: AI tools provide analytical support; human accountability remains singular and explicit. The decision log schema enforces this boundary at the artifact level.

A decision log captures six fields at the moment a phase-gate choice is made:

```
decision_question     → What choice was required?
options_considered    → What alternatives were evaluated?
evidence_base         → What data informed the decision, at what completeness?
risk_posture          → What risk level was accepted, and why?
contingency           → What triggers a revisit?
approvers             → Who authorized this decision, and in what role?
```

Schema validation runs in CI/CD (GitHub Actions) before any decision log merges, ensuring required fields cannot be omitted under time pressure.

---

## Key Findings

**Operational ROI (high confidence):** $1.8–2.3M for a 5-IND portfolio over 3 years. Decision cycle compression of 30–50%; deficiency response acceleration of 60–70%.

**Regulatory ROI (medium confidence):** 12–25% reduction in total FDA deficiency rates for the reconstructability-addressable slice (25–30% of CRLs). Clinical hold rate reduction from 8.9% baseline to 3–5% for governance-driven holds.

**Regulatory trajectory:** FDA's January 2025 draft guidance on AI in regulatory submissions signals Phase 1 voluntary incentives (2026–27) followed by anticipated mandate for AI-assisted decisions in 2027–28. Organizations implementing RGDS now avoid retroactive compliance remediation.

---

## Repository Structure

```
rgds-independent-study/
├── docs/
│   ├── index.md                    # Full study: foreword, preface, introduction
│   ├── questions/
│   │   ├── q1.md – q10.md          # Ten research questions with full analysis
│   │   └── results-overview.md     # Synthesized findings across all questions
│   └── references/
│       ├── about-the-author.md
│       ├── acknowledgements.md
│       ├── bibliography.md         # 96 annotated sources
│       ├── appendix-a.md           # Financial impact and ROI methodology
│       └── methods-and-tools.md    # AI disclosure and research workflow
├── .github/workflows/
│   └── deploy-mkdocs.yml           # GitHub Pages CI/CD pipeline
├── mkdocs.yml                      # MkDocs Material theme configuration
├── requirements.txt
└── LICENSE                         # Apache License 2.0
```

Related repositories:
- **[rgds](https://github.com/mj3b/rgds)** — Decision log schemas, governance covenants, canonical example logs (RGDS-DEC-0001 through RGDS-DEC-0006), and JSON schema validation pipeline
- **[rgds-ai-governance](https://github.com/mj3b/rgds-ai-governance)** — Non-agentic AI governance boundaries and constraints for regulated decision support

---

## Documentation Site

The full ten-question study is published via GitHub Pages using MkDocs Material:

**[https://mj3b.github.io/rgds-independent-study](https://mj3b.github.io/rgds-independent-study)**

To build locally:

```bash
pip install -r requirements.txt
mkdocs serve
```

---

## Scope and Limitations

This study addresses a specific failure mode: the inability to reconstruct decision logic under regulatory scrutiny. It does not address scientific insufficiency, manufacturing gaps, or clinical data quality—the remaining 70–75% of FDA deficiencies that governance cannot resolve.

ROI projections are modeled against a 5-IND portfolio using published benchmarks from Tufts CSDD, Deloitte, and industry analysis. Operational ROI (cycle compression, deficiency response, inspection efficiency) carries high confidence. Regulatory ROI (deficiency rate reduction, clinical hold avoidance) carries medium confidence and depends on implementation fidelity. Financial ROI projections (valuation premiums, M&A uplifts) are excluded from business cases as speculative.

---

## AI-Assisted Research Disclosure

This project used Claude (Anthropic), Perplexity AI (deep research mode), and ChatGPT (OpenAI) for literature synthesis, framework development, schema design, documentation, and drafting (November 2025 – January 2026). All AI-generated output was treated as draft material subject to human review. All 96 bibliography entries were verified for accuracy, accessibility, and direct source linkage. The author assumes sole responsibility for selection, interpretation, integration, and accuracy of all content.

Full disclosure is in [Supplementary Materials and Technical Notes](docs/references/methods-and-tools.md).

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

---

## License

Copyright © 2026 Mark Julius Banasihan. Licensed under the [Apache License 2.0](LICENSE).

---

## Author

**Mark Julius Banasihan**
Decision governance systems for regulated, high-stakes environments.

[GitHub](https://github.com/mj3b) · [LinkedIn](https://linkedin.com/in/markjuliusbanasihan) · [ORCID](https://orcid.org/0009-0001-8121-2878) · Atlanta, Georgia, United States
