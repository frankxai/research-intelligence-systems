# Reproducibility Review Workflow

## Purpose

Systematic assessment of reproducibility quality across a body of literature or for individual studies. Generates reproducibility scores, open science compliance reports, and identifies high-confidence versus fragile findings for downstream use in claim graphs and evidence synthesis.

## Inputs

| Field | Notes |
|---|---|
| Paper set | `paper.schema.json` records |
| Domain pack | Activates domain-specific reporting standards |
| Review depth | `quick` (metadata only) / `standard` / `deep` (code + data inspection) |

## Step 1: Open Science Metadata Check

For each paper, assess:

| Item | Criteria | Score weight |
|---|---|---|
| Preregistration | Present, accessible, timestamped before data collection | 25 pts |
| Registered Report | Stage 1 IPA obtained and documented | 5 pts bonus |
| Open data | Available, accessible, not broken link | 20 pts |
| Open code | Available, includes README/instructions | 20 pts |
| Open materials | Stimuli, instruments, or protocols shared | 10 pts |
| Data standard | BIDS / NWB / xAPI / OMOP compliance | 10 pts |
| Preprint availability | Author's version freely accessible | 5 pts |

**Data standard validation (deep mode):**
- BIDS: run `bids-validator` CLI against shared dataset; check for warnings/errors
- NWB: run `NWBInspector`; verify required fields populated
- xAPI: check statement structure against xAPI specification

## Step 2: Methods Reporting Assessment

Apply domain-specific reporting checklist:

| Domain | Checklist |
|---|---|
| Neuroimaging (MRI/fMRI) | COBIDAS MRI checklist |
| EEG/MEG | COBIDAS EEG/MEG checklist |
| RCTs | CONSORT 2010 (+ extension for cluster RCTs, non-inferiority) |
| Observational studies | STROBE checklist |
| Systematic reviews | PRISMA 2020 |
| Intervention descriptions | TIDieR checklist (12 items) |
| Educational interventions | CONSORT-SPI |

**Key reporting items assessed:**
- Effect sizes reported (not just p-values)
- 95% CIs reported
- Exact p-values (not "p < .05")
- Power analysis reported with target, achieved power, and effect size assumption
- Exclusion criteria pre-specified and reported

## Step 3: Statistical Red Flags

Automated scan for:

| Flag | Detection Method |
|---|---|
| p-value clustering below .05 | Distribution test (p-checker, statcheck) |
| Impossible statistics | GRIM test (means), SPRITE (SD + N constraints), statcheck |
| Optional stopping / peeking | No preregistration + flexible stopping language |
| HARKing | Exploratory results described as confirmatory; no preregistration |
| Selective outcome reporting | Compare registered outcomes vs. reported; switch primary → secondary |
| Winner's curse / inflated ES | ES > 2 SD above meta-analytic average for that paradigm |
| Underpowered studies | Reported power < 80% or implied power (from N + ES) < 80% |

**Tools:** statcheck (R package), p-checker.shinyapps.io, GRIM/SPRITE via scrutiny (R).

## Step 4: Replication Status

Assess the paper's position in the replication ecosystem:

- **Direct replications**: same paradigm, same primary DV, independent sample — count successes and failures
- **Conceptual replications**: same construct, different operationalization — weight by methodological similarity
- **Multi-lab studies** (Many Labs, PSA, ManyBabies): count as strong replication evidence; weight N ≥ 5 labs
- **Failed replications**: flag if replication_success_rate < 0.5 with ≥ 3 attempts
- **Adversarial collaborations**: highest quality replication evidence; note outcomes

## Step 5: Data and Code Verification (Deep Mode)

1. Attempt to access data repository: follow open_data_url; check for link rot (HTTP 200/404)
2. Verify BIDS/NWB validity if neuroimaging (run bids-validator; check NWBInspector score)
3. Check code runs: README instructions, requirements.txt / renv.lock / environment.yml present
4. Attempt to reproduce one key figure or primary statistic from shared code + data
5. Record outcome: `verified` / `partially-verified` / `could-not-reproduce` / `not-attempted`

## Step 6: Reproducibility Score

Composite score (0–100):

```
score = preregistration_score (0–25)
      + open_data_score (0–20)
      + open_code_score (0–20)
      + methods_reporting_score (0–20)
      + replication_score (0–15)
      [+ bonus: registered_report (+5), data_standard (+10 if verified)]
```

**Traffic light summary:**
- Green (≥ 75): high reproducibility confidence — suitable as strong evidence
- Yellow (40–74): moderate — use with caveats; flag in claim graph
- Red (< 40): low — treat as preliminary; do not base policy/practice on alone

## Step 7: Recommendations

For each paper generate:
- **For authors/teams**: specific items to add (share data, register next study, add CI)
- **For evidence consumers**: how to discount/weight this evidence in a claim graph
- **Field-level insight**: aggregate scores across a literature to identify systemic gaps

## Agent Support

| Agent | Role |
|---|---|
| `reproducibility-assessor` | Orchestrates scoring pipeline |
| `methods-reporter-checker` | Applies COBIDAS/CONSORT/STROBE checklists |
| `stats-red-flag-detector` | Runs statcheck, GRIM, p-distribution tests |
| `data-accessibility-verifier` | HTTP checks + BIDS/NWB validation |
| `replication-tracker` | Queries Many Labs, PSA, replication databases |

## Output Artifacts

1. `reproducibility-score.json` per paper (structured score with component breakdown)
2. Field-level compliance table (% of field papers meeting each criterion)
3. Red flag report (per-paper narrative)
4. Recommendations list (prioritized by impact)
5. PRISMA-style flow for data/code availability verification
