# Preregistration & Registered Reports Workflow

## Purpose

Guide researchers and AI agents through preregistration of studies and the Registered Reports journal track. Maximizes transparency, separates confirmatory from exploratory inference, and eliminates post-hoc hypothesizing. Covers standard preregistration (OSF, AsPredicted, PROSPERO) and the full Registered Reports pipeline (Stage 1 → IPA → data collection → Stage 2).

## When to Preregister

Preregister all **confirmatory** (hypothesis-testing) studies. Timing rules:

| Scenario | When to register | Platform |
|---|---|---|
| Prospective experiment | Before data collection begins | OSF, AsPredicted |
| Secondary data analysis | Before opening / analyzing dataset | OSF (time-stamped) |
| Systematic review | Before searching | PROSPERO |
| Clinical trial | Before first participant enrolled | ClinicalTrials.gov, ISRCTN |
| Field experiment (dev economics) | Before randomization | AEA RCT Registry, RIDIE |
| Education RCT | Before treatment assignment | AEA RCT Registry, OSF |

## Standard Preregistration

### Step 1: Prepare the Registration Document

**Required elements (OSF Standard Pre-Data Collection Template):**

1. **Hypotheses**: State directional, operationalized predictions. Distinguish confirmatory (will be reported as such) from exploratory (will be labeled exploratory).
2. **Design**: Study type, random assignment method, blinding protocol
3. **Participants**: Recruitment source, inclusion/exclusion criteria, stopping rule (exact N or interim analysis plan)
4. **Measures**: All DVs, IVs, and covariates; scale names and reliability expectation; operationalization of each construct
5. **Analysis plan**: Primary statistical model (specify formula-level); secondary analyses; moderator tests; how missing data will be handled
6. **Exclusion criteria**: Pre-specified per-participant exclusion rules that do not depend on outcomes (e.g., > 25% missing trials, performance < chance, motion > 3 mm)
7. **Exploratory analyses**: List explicitly so they're distinguishable from confirmatory

**AsPredicted (9-question form):**
1. Data collected? (No for prospective)
2. Hypothesis
3. Dependent variables
4. Conditions
5. Analyses
6. Outliers
7. Sample size
8. Anything else?
9. Name of study (public)

### Step 2: Register and Timestamp

- **OSF**: Project → Registrations → New Registration → choose template → Submit for immediate public registration
- **AsPredicted**: aspredicted.org → create → download timestamped PDF
- **Embargo**: acceptable up to 4 years for ongoing studies; **make public at journal submission**
- The registration timestamp is the proof-of-preregistration; earlier = better

### Step 3: Maintain a Deviation Log

Any deviation from the preregistration (unavoidable design changes, additional measures added) must be:
1. Documented in a deviation log (versioned OSF wiki or supplementary file)
2. Justified with reason
3. Clearly labeled in the paper ("This analysis was not preregistered; it was conducted because...")

**Not a deviation:** labeling something exploratory that was exploratory in the preregistration.

## Registered Reports Track

Registered Reports provide **in-principle acceptance (IPA)** before data collection, making the publication decision independent of results.

### Stage 1: Submission for IPA

Write Stage 1 manuscript (typically 3,000–5,000 words):

1. **Introduction**: Theoretical motivation, gap in the literature, specific hypotheses
2. **Methods** (complete): Participants (power analysis, recruitment, inclusion/exclusion), design, materials, procedure, analysis plan
3. **Power analysis**: Demonstrate ≥ 90% power for primary analysis at the minimal effect of interest (not at the expected effect, which is inflated by winner's curse)

Submit to a Registered Reports-accepting journal (full list: cos.io/rr). Peer review assesses:
- Importance of the question
- Rigor and completeness of methods
- Feasibility
- Adequacy of power analysis

**IPA outcome options:** Accept / Major revisions / Reject. If IPA received, conduct the study.

### Stage 2: Results Submission

After data collection:
1. Report all preregistered results — including null results (they are guaranteed publication)
2. Clearly separate confirmatory (preregistered) from exploratory (unregistered) analyses
3. Document any protocol deviations with justification
4. Peer review checks **protocol adherence**, not result direction

### Registered Replication Reports (RRR)

Multi-lab format for testing robustness of landmark findings:
- Coordinated by *Perspectives on Psychological Science*, *Advances in Methods and Practices*
- 10+ labs run identical protocol
- Combined power to detect even small effects
- Pre-specified meta-analytic integration of lab-level results

## Tools & Templates

| Tool | Use |
|---|---|
| OSF (osf.io) | Full-featured preregistration, file storage, time-stamping |
| AsPredicted (aspredicted.org) | Fast 9-question form; minimal friction |
| PROSPERO (crd.york.ac.uk/prospero) | Systematic review registration |
| ClinicalTrials.gov | US federal registry for clinical trials |
| AEA RCT Registry | Field experiments in development economics |
| RIDIE (3ie) | International development impact evaluations |
| G*Power | Frequentist power analysis (t, F, χ², z tests) |
| pwr (R) | Programmatic power analysis |
| PANGEA | Mixed designs (crossed and nested random effects) |
| pwrss (R) | General linear mixed model power |

## Power Analysis Guidance

Minimum sample size principles:
- Target **90% power** (not 80%): the ~80% convention produces ~50% post-hoc power replication rate
- Use the **smallest effect of interest** (SESOI), not the expected/hoped-for effect
- Account for **attrition**: inflate N by expected dropout rate
- For multilevel designs: power at the level of randomization (not total N)
- Report: alpha, power, SESOI, design parameters, software used

## Agent Support

| Agent | Role |
|---|---|
| `preregistration-drafter` | Generates OSF-compatible registration document from study description |
| `power-calculator` | Runs power analysis given design parameters (design, alpha, power, SESOI) |
| `deviation-tracker` | Compares final paper methods with preregistration; flags undisclosed deviations |
| `rr-journal-matcher` | Recommends Registered Reports journals by domain + turnaround time |
| `pap-generator` | Generates Pre-Analysis Plan in J-PAL/IPA format for field experiments |

## Output Artifacts

1. Registration document (OSF XML or AsPredicted PDF + timestamp)
2. Power analysis report (design parameters, R/G*Power output)
3. Deviation log template (versioned markdown)
4. Stage 1 manuscript outline (for Registered Reports track)
5. Journal shortlist with RR track details (turnaround, format requirements)
