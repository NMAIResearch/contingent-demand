# Contingent vs Robust AI Power Demand — interactive

An interactive front-end to *Contingent vs Robust AI Power Demand*: a realized announced-to-in-service **completion anchor** from the PJM interconnection queue. The thesis is simple — *announced capacity is not deliverable capacity* — and the tool lets you watch any announced headline deflate through the three measured attrition stages.

**Live tool:** https://nmiltonresearch.github.io/contingent-demand/
**Canonical record (frozen, citable):** [DOI 10.5281/zenodo.20559430](https://doi.org/10.5281/zenodo.20559430)
**Author:** N. Milton · ORCID [0009-0003-4213-7769](https://orcid.org/0009-0003-4213-7769) · Licence CC BY 4.0

## What it does

Two views, switched at the top:

- **Deflation calculator.** Enter an announced capacity (GW) and move three sliders — de-duplication (r1), viability survival (r2, entered → signed agreement), and build rate (r3, agreement → in service). A live waterfall shows how much survives each stage and what is finally deliverable. Defaults are the PJM mature-cohort measured base rate (r1 ≈ 0.85, r2 ≈ 0.39, r3 ≈ 0.58 → roughly one announced MW in five built); the sliders are for sensitivity, not invention. "Reset" returns to the measured anchor.
- **PJM evidence.** The published completion funnel (2010–2017 cohort, 204 GW entered) and realized completion by submitted cohort — the empirical base rate behind the calculator's defaults.

## Important: no raw PJM data here

PJM planning data carries a redistribution restriction. This repository therefore bundles **only the published derived aggregates** (`funnel.csv`, `cohorts.csv`). The full method (`reproduce.py`) reads a locally-obtained PJM export and is reproducible only by someone who has independently obtained PJM access — see the Zenodo record.

## Files

- `index.html` — the interactive tool, self-contained (no dependencies, no server needed).
- `funnel.csv`, `cohorts.csv` — the published aggregates the tool displays.
- `build.py` — regenerates `index.html` by embedding the CSVs (pure standard library).

## Guardrails

The mature 2010–2017 cohort is *generic historical generation* used as a completion base rate, not capacity announced to serve AI — transferring that rate to the AI cohort is the named load-bearing assumption (cohort comparability). This deflates the **supply** side, not the ~950 TWh demand headline. "Built" counts only In Service (conservative). The output is a band; treat any announced figure as a scenario, not a baseline.

## Disclosure

No third party reviewed, funded, or directed this work. Independent analysis, not investment advice.

## Licence

Creative Commons Attribution 4.0 International (CC BY 4.0).
