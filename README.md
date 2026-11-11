> **Research status, as of November 11, 2026: Historical exploratory study.**
>
> **What this repository holds.** Literature synthesis and illustrative reasoning across ten questions about decision records in regulated drug development.
>
> **What remains open.** Retained quantitative, pilot and regulatory-validation claims require supporting-record review; empirical effects are not established.

<h1>
<picture>
  <source media="(max-width: 600px)" srcset="assets/research/v1/banner-mobile-dark.svg">
  <img src="assets/research/v1/banner-dark.svg" alt="RGDS Independent Study" width="1000">
</picture>
</h1>

[![Status: Exploratory study](assets/research/v1/badges/status-dark.svg)](docs/current-review.md) [![Version: v1.4](assets/research/v1/badges/version-dark.svg)](CITATION.cff) [![License: Apache-2.0](assets/research/v1/badges/license-dark.svg)](LICENSE)

How could decision records help reviewers reconstruct choices in regulated drug development? This ten-question study explores that design question through literature synthesis and worked reasoning. [Study purpose](docs/references/acknowledgements.md), [study questions](docs/questions/).

[Policy reader: understand in 90 seconds](#research-in-90-seconds) · [Reviewer: inspect evidence and limits](docs/current-review.md) · [Engineer: build the documentation](docs/reference-verification.md)

## At a glance

| | Current account |
| :--- | :--- |
| Purpose | Explore decision records in regulated drug development. [Study purpose](docs/references/acknowledgements.md) |
| Status | Historical, exploratory study. Quantitative and validation claims need supporting-record review. [Current review](docs/current-review.md) |
| Evidence type | Literature synthesis, proposed methods and illustrative reasoning across ten questions. [Question files](docs/questions/), [methods](docs/references/methods-and-tools.md) |
| Version | v1.4. Citation date: January 9, 2026. [Citation record](CITATION.cff), [release](https://github.com/node-and-norm/rgds-independent-study/releases/tag/v1.4) |
| License | [Apache-2.0](LICENSE). |
| Cite | [Citation metadata](CITATION.cff) · [recorded DOI: 10.5281/zenodo.20242004](https://doi.org/10.5281/zenodo.20242004) |

**Review boundary:** the retained chapters include stronger pilot, financial-return and regulatory-validation claims. The repository snapshot does not supply the underlying empirical records needed to establish those effects. The [review guide](docs/current-review.md#evidence-status) identifies those claims and the missing support.

## Research in 90 seconds

The study asks how an institution could preserve the reasons for a consequential choice. Regulated Gate Decision Support (RGDS) organizes that question around decisions at development gates, where a program advances, pauses or changes direction. The study examines records for evidence, rationale, risk and responsibility. [Study overview](docs/index.md), [first question](docs/questions/q1.md).

Its contribution is an exploratory account of decision documentation in biopharmaceutical development. Ten chapters examine reconstructability, AI assistance, adoption, regulatory interpretation and financial modeling. Reviewers should treat each proposed benefit according to its supporting evidence. [Study questions](docs/questions/), [current evidence boundaries](docs/current-review.md).

The related repositories serve different purposes. [RGDS](https://github.com/node-and-norm/rgds) holds the reference schema and validator. [AI Assistance Governance](https://github.com/node-and-norm/rgds-ai-governance) describes a working method for bounded AI participation. The study supplies exploratory context for those artifacts. [Recorded relationships](CITATION.cff).

## Method and evidence

The documented method combines public sources with a ten-question inquiry. Its outputs are chapters, illustrative reasoning and a numbered bibliography. [Methods](docs/references/methods-and-tools.md), [bibliography](docs/references/bibliography.md).

The current review separates those materials from empirical validation. Claims about pilots, financial return or avoided regulatory action need inspectable underlying records and claim-specific source checks. The [results overview](docs/questions/results-overview.md) retains the historical claims; the [review guide](docs/current-review.md#evidence-status) records their present evidential limits.

## Known limits

- **Quantitative claims:** calculations and outcome assertions require separate supporting-record review. [Review scope](docs/current-review.md#evidence-status)
- **Source coverage:** numbered bibliography entries include duplicate works and incomplete links. Their count establishes the size of the list. [Bibliography](docs/references/bibliography.md), [source-review boundary](docs/current-review.md#sources-and-human-verification)
- **Regulatory interpretation:** the chapters preserve historical interpretations and forecasts. Current applicability requires a new check against the relevant authority. [Interpretive scope](docs/current-review.md#sources-and-human-verification)
- **Transfer:** the study does not supply a field evaluation of either related repository. [Repository relationships and status](https://github.com/node-and-norm/rgds-ai-governance/blob/main/README.md)

## Reproduce the documentation

Use the [verification guide](docs/reference-verification.md) to build the MkDocs documentation with Python 3.11 and the declared dependencies. The build writes HTML to a disposable directory. Successful rendering establishes a documentation-build result. Research claims retain their separate evidence requirements. [Build configuration](mkdocs.yml), [workflow](.github/workflows/deploy-mkdocs.yml).

## AI assistance and human review

The historical disclosure records AI assistance with literature discovery, evidence synthesis, schema design, drafting and editing. It also makes broad verification claims. The current review has no claim-by-claim human verification register that establishes those claims. Their scope remains open for personal source review. [Historical disclosure](docs/references/acknowledgements.md#ai-assisted-research-disclosure), [current review](docs/current-review.md#sources-and-human-verification).

Codex prepared this navigation draft and its bounded review guide. The chapters, bibliography, citation metadata and research results remain as recorded in the [preserved baseline](https://github.com/node-and-norm/rgds-independent-study/tree/6eeb02601440380dda990f2a097eb92164d66558).

## Cite the study

This entry renders the identity recorded in [CITATION.cff](CITATION.cff). The citation file uses the software category for this documentation artifact. Its January 9 date remains distinct from the GitHub release publication date. [Version boundary](docs/current-review.md#version-and-citation).

```bibtex
@software{banasihan2026rgdsstudy,
  author = {Banasihan, Mark Julius},
  title = {RGDS: Regulated Gate Decision Support \textemdash{} Decision-Centric AI Governance in Biopharma/Biotech Development},
  year = {2026},
  month = jan,
  version = {1.4},
  doi = {10.5281/zenodo.20242004},
  url = {https://node-and-norm.github.io/rgds-independent-study},
  note = {Citation date: January 9, 2026}
}
```

<details>
<summary>Historical chapters and earlier navigation</summary>

The [prior README](README-2026-11-03.md) preserves the full entry at [audit commit 6eeb026](https://github.com/node-and-norm/rgds-independent-study/tree/6eeb02601440380dda990f2a097eb92164d66558). Read the chapters alongside the [current review guide](docs/current-review.md).

- [Ten study questions](docs/questions/)
- [Bibliography](docs/references/bibliography.md)
- [Annotated regulatory references](docs/references/appendix-a.md)
- [Methods and tools](docs/references/methods-and-tools.md)
- [Change history](CHANGELOG.md)

</details>
