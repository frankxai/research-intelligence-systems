# Evidence Table Workflow

## Purpose

Construct structured, queryable evidence tables from a set of papers (output of the literature-review workflow). Produces populated `evidence-table.schema.json` records with risk-of-bias scoring, quantitative synthesis statistics, GRADE certainty ratings, and narrative conclusions.

## Inputs

| Field | Notes |
|---|---|
| Paper set | `paper.schema.json` records, post-screening |
| Research question | PICO/PECO formatted |
| Synthesis type | `quantitative` (meta-analysis) or `qualitative` (narrative) |
| Effect size metric | Specify upfront: Cohen's d, OR, RR, partial η², etc. |

## Step 1: Table Design

Before extraction, specify:
- **Columns**: core (DOI, authors, year, design, N, intervention, outcome, effect size, RoB) + domain-specific (imaging modality for neuro; BCT codes for behavioral; WWC tier for learning)
- **Risk-of-bias tool** matched to predominant study design
- **Primary outcome** (one effect size per study; separate tables for secondary outcomes)
- **Synthesis strategy**: fixed vs. random effects; REML estimator preferred for random effects (Viechtbauer 2005)

## Step 2: Data Extraction (Two-Pass)

**Pass 1 — Automated extraction:**
- Pull from `paper.schema.json` where already populated
- Extract effect sizes from statistical tables using regex patterns (t, F, r, χ², OR)
- Convert between effect size metrics using standard formulas (d from t, r from F, etc.)

**Pass 2 — Human verification:**
- Flag records where: effect size missing, design ambiguous, multiple outcomes not disambiguated
- Resolve contact-author queries for unpublished data
- Record extraction decisions in notes field

## Step 3: Risk of Bias Assessment

Apply tool appropriate to design:

| Design | Tool | Domains assessed |
|---|---|---|
| RCT | Cochrane RoB 2.0 | Randomization, deviations, missing data, measurement, selection of reported result |
| Non-randomized | ROBINS-I | Confounding, selection, classification, deviations, missing data, measurement, reporting |
| Cohort/case-control | Newcastle-Ottawa | Selection (4), comparability (2), outcome (3); star system |
| Diagnostic accuracy | QUADAS-2 | Patient selection, index test, reference standard, flow/timing |

Overall RoB judgment feeds into GRADE Step 1 (start at RCT = high certainty, observational = low certainty).

## Step 4: Quantitative Synthesis

When ≥ 2 studies report the same outcome in a compatible format:

**Effect size pooling:**
```r
library(metafor)
res <- rma(yi = effect_size, vi = variance, data = df, method = "REML")
```

**Heterogeneity:**
- I² < 25%: low; 25–50%: moderate; 50–75%: substantial; > 75%: considerable
- τ² (between-study variance) and its 95% CI
- Cochran's Q test (note: underpowered with few studies)

**Publication bias** (if ≥ 10 studies):
- Funnel plot visual inspection
- Egger's regression test (intercept ≠ 0 = asymmetry)
- PET-PEESE: precision-effect test and precision-effect estimate with standard error

**Subgroup and moderator analysis:**
- Pre-specified moderators only (to avoid capitalizing on chance)
- Mixed-effects model with moderator as predictor
- Report between-group Q (Qb) and within-group I²

## Step 5: Narrative Synthesis

For heterogeneous or non-quantifiable outcomes:
- Direction of effect: consistent positive, consistent negative, mixed, null
- Magnitude: tabulate effect sizes and ranges
- Consistency: proportion of studies in expected direction
- Dose-response: test for linear trend if quantity/intensity varies

## Step 6: GRADE Assessment

For each outcome, rate four domains, then determine overall certainty:

| Domain | Possible downgrade reasons |
|---|---|
| Risk of bias | Most evidence at high/some-concern RoB |
| Inconsistency | I² > 50%, wide prediction interval |
| Indirectness | Different population, intervention, or outcome from PICO |
| Imprecision | Wide CI crossing MID (minimal important difference) |
| Publication bias | Funnel asymmetry, selective reporting |

Upgrade factors: large effect (d > 0.8), dose-response gradient, opposing confounding.

Final certainty: **high → moderate → low → very-low** per domain downgrade.

## Step 7: Export

- Populate `evidence-table.schema.json` with all fields
- Generate markdown summary table for reports
- Export CSV for external meta-analytic software (RevMan, Comprehensive Meta-Analysis)
- Generate R/Python analysis script for reproducible synthesis

## Agent Support

| Agent | Role |
|---|---|
| `evidence-table-builder` | Orchestrates two-pass extraction |
| `bias-assessor` | RoB tool application and scoring |
| `meta-analytic-synthesizer` | Pooling, heterogeneity, publication bias |
| `grade-assessor` | GRADE domain rating and certainty judgment |
| `effect-converter` | Converts between effect size metrics |
