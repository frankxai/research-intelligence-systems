# Psychology Research Intelligence Pack

## Overview

This pack provides construct-driven, reproducible, agent-assisted psychological science research intelligence across the full breadth of empirical psychology. Every workflow in this pack is anchored to named constructs, validated measurement instruments, and traceable effect sizes, so that evidence accumulates coherently rather than fragmenting across incompatible operationalizations. Agents handle the highest-friction steps in evidence synthesis — construct mapping, effect-size extraction, risk-of-bias appraisal, and meta-analytic pooling — while researchers maintain full methodological control.

The pack covers clinical, social, cognitive, developmental, personality, and industrial-organizational psychology. It integrates authoritative ontologies (Cognitive Atlas, RDoC, HiTOP), canonical reporting standards (CONSORT, PRISMA, STROBE), and modern statistical workflows including mixed models, Bayesian hypothesis testing, and multiverse analysis. Researchers using this pack inherit a reproducibility scaffold from first literature search to final synthesis, aligned with open science best practices and the post-replication-crisis methodological consensus.

---

## Domain Scope

### Cognitive Psychology
Covers attention (selective, sustained, divided), working memory capacity, long-term memory consolidation, executive function (inhibition, cognitive shifting, updating), perception, and mental representation. Construct definitions are anchored to the Cognitive Atlas to prevent jingle-jangle proliferation across paradigms — for example, distinguishing Stroop-based response inhibition from stop-signal reactive inhibition, which correlate only modestly despite sharing the label "inhibitory control."

### Social Psychology
Covers attitude formation and change, group dynamics, social cognition, implicit and explicit prejudice, descriptive and injunctive norms, and conformity. Effect sizes in this domain carry elevated replication risk; all syntheses in this pack apply p-curve or three-parameter selection model (3PSM) publication-bias correction by default, and single-lab, un-preregistered findings are flagged as provisional.

### Clinical Psychology
Covers psychopathology classification (DSM-5-TR, ICD-11, HiTOP dimensional alternatives), assessment reliability and validity, intervention efficacy, and randomized controlled trial methodology. Risk-of-bias appraisal uses Cochrane RoB 2.0 for RCTs and ROBINS-I for observational designs. Certainty of evidence grading follows GRADE. The distinction between efficacy (tightly controlled RCTs) and effectiveness (real-world implementation) is tracked as a structured field.

### Developmental Psychology
Covers lifespan development from prenatal through late adulthood, attachment theory (Ainsworth Strange Situation classifications; Main Adult Attachment Interview), Piagetian and neo-Piagetian cognitive development, and moral development (Kohlberg/Gilligan/Haidt social intuitionist model). Large-scale replication consortia — specifically ManyBabies — are tracked as primary benchmarks for developmental findings, given the well-documented replication failure rate in this sub-field.

### Personality Psychology
Covers trait models including the Big Five (NEO PI-R, BFI, BFI-2) and HEXACO (adding Honesty-Humility as a sixth factor), individual differences in cognition and affect, and the rank-order stability vs. mean-level change debate across the lifespan. Measurement invariance testing across demographic groups is mandatory before group comparisons are interpreted — partial invariance is documented and constraints are reported.

### Industrial-Organizational Psychology
Covers workplace behavior, transformational and transactional leadership, selection validity (cognitive ability, structured interviews, work samples, personality), job satisfaction, organizational commitment, and organizational citizenship behavior (OCB). Meta-analytic databases using Schmidt and Hunter artifact-corrected correlation procedures are the primary evidence base for selection validity claims, given the well-established superiority of corrected over uncorrected estimates.

---

## Construct Standards & Measurement

- **Canonical operationalization**: APA Dictionary of Psychology for definitional anchoring; Cognitive Atlas (`cognitiveatlas.org`) for cognitive task-to-construct mappings.
- **Construct proliferation**: New measures must demonstrate discriminant validity (AVE > shared variance with related constructs; HTMT ratio < 0.85) against existing instruments. Jingle-jangle fallacies — same name applied to different constructs, or different names applied to the same construct — are flagged by the `construct-mapper` agent during literature intake.
- **Measurement invariance**: Before comparing latent means across groups, test the configural → metric → scalar invariance sequence with `lavaan` in R. Report χ² difference tests and ΔCFI (threshold for non-invariance: ΔCFI ≤ −0.010). Partial scalar invariance (freeing one or two non-invariant intercepts) is acceptable if reported transparently.
- **Psychometric modeling**: Prefer IRT — graded response model for polytomous items, 2PL for binary — over CTT for item-level analysis. Use the `mirt` package in R. Use McDonald's ω (total and hierarchical) via `psych::reliability()` as the reliability estimate; Cronbach α is reported only for legacy comparability and annotated with its tau-equivalence assumption.
- **CFA/SEM with lavaan**: Minimum adequate fit indices are CFI ≥ 0.95, RMSEA ≤ 0.06 (90% CI upper bound ≤ 0.10), SRMR ≤ 0.08. Standardized loadings and their 95% CIs are required in supplementary materials. Modification indices are reported but not applied without theoretical justification.
- **Network psychometrics**: For constructs where a common-cause latent variable model is theoretically contested (e.g., depression symptom networks, resilience), estimate and report `qgraph`/`bootnet` regularized partial correlation (EBIC-graphLasso) networks alongside — or instead of — CFA solutions. Report edge-weight stability via case-dropping subset bootstrap.

---

## Reproducibility & Open Science

- **Preregistration formats**: AsPredicted 9-question form for focused hypothesis tests; standard OSF template for broader multivariate studies; replication-specific OSF form for direct and conceptual replications. Preregistration must occur before data collection; all deviations are documented in the manuscript methods section.
- **Registered Reports**: 300+ journals now accept the Registered Report format. Stage 1 In-Principle Acceptance (IPA) is granted before data collection, eliminating publication bias for confirmatory findings. Priority submission targets: *Psychological Science*, *JPSP*, *Cognition*, and *Advances in Methods and Practices in Psychological Science* (AMPPS).
- **Reporting standards**: CONSORT 2010 (+ extensions for cluster RCTs, crossover, pilot trials) for randomized trials; PRISMA 2020 (+ PRISMA-P for protocols) for meta-analyses; STROBE for observational studies. Completed checklists are required supplementary materials, not optional.
- **Open Science badges**: The American Psychological Association and Center for Open Science award Open Materials, Open Data, and Preregistered badges. All syntheses in this pack assume badge-level compliance as the target standard — materials and data deposited on OSF or a permanent repository with a DOI.
- **Replication crisis context**: Median statistical power in social psychology is approximately 35% (Smaldino & McElreath, 2016). Widespread p-hacking — inflating α via optional stopping, covariate fishing, and selective reporting — and HARKing (Hypothesizing After Results are Known) inflated false-positive rates far beyond the nominal 5%. This pack treats every un-preregistered, single-lab finding as provisional until independently replicated.
- **Large-scale replication projects**: Many Labs 1–5, ManyBabies (developmental), and the Psychological Science Accelerator (PSA, 80+ countries, explicit WEIRD-bias correction) are the gold-standard replication benchmarks. Effect sizes from these projects supersede original single-lab estimates in meta-analytic pooling.
- **SIPS**: The Society for the Improvement of Psychological Science (`improvingpsych.org`) provides evolving best-practice guidance; its annual meeting proceedings are monitored for emerging methodological norms.

---

## Modern Statistics

- **Mixed models vs. RM-ANOVA**: Linear mixed models (`lme4::lmer`) handle missing data via REML/ML without listwise deletion, accommodate unbalanced designs naturally, and provide partial pooling across participants and stimuli simultaneously — the "crossed random effects" structure treating both participants and items as random effects simultaneously. Use `lmerTest` for Satterthwaite-approximated denominator degrees of freedom and p-values. Use `lme4` with `glmer` for binary outcomes (logistic), `glmer.nb` for count data.

- **Bayesian hypothesis testing**: Compute Bayes factors with the `BayesFactor` R package or JASP. Default Cauchy prior (scale = √2/2 ≈ 0.707) for standardized effect sizes on the two-sided t-test. Interpretation thresholds: BF₁₀ > 3 = moderate, > 10 = strong, > 30 = very strong, > 100 = extreme evidence for H₁; invert for H₀ support.

- **Sequential / ROPE analysis**: Use the Region of Practical Equivalence (ROPE ± 0.1 SD for "negligible" effects) with the Highest Density Interval (HDI) from the posterior to make practical significance decisions. Bayesian Factor Design Analysis (BFDA) replaces traditional power analysis for sequential Bayesian designs.

- **Meta-analysis pipeline**:

  ```r
  library(metafor)

  # Compute standardized mean differences
  dat <- escalc(
    measure = "SMD",
    m1i = m1, sd1i = sd1, n1i = n1,
    m2i = m2, sd2i = sd2, n2i = n2,
    data = df
  )

  # Random-effects model (single level)
  res <- rma(yi, vi, data = dat, method = "REML")

  # Three-level model for nested effects (multiple effects per study)
  res_mv <- rma.mv(
    yi, vi,
    random = ~ 1 | study / effect_id,
    data = dat
  )

  forest(res)   # forest plot
  funnel(res)   # funnel plot for publication bias
  ```

- **Publication bias**: Apply trim-and-fill, PET-PEESE (Peters et al., 2007), and the three-parameter selection model (3PSM; Vevea & Woods, 2005) in parallel. Concordance across methods — and across estimates — strengthens conclusions.

- **Equivalence testing**: Use the Two One-Sided Tests (TOST) procedure (`TOSTER` package, Lakens et al.) to establish that an effect falls within a practically insignificant ROPE. Required for all null-result claims — failing to reject H₀ is not evidence for H₀ without equivalence bounds.

- **Multiverse / specification curve**: Enumerate all defensible analytical choices — outlier exclusion criteria, covariate sets, operationalizations, analysis windows. Run all combinations; plot the specification curve (Simonsohn, Simmons, & Nelson, 2020). A finding is considered robust only if the median effect is statistically significant and the distribution of effects across the curve is predominantly in the same direction.

- **Power analysis**: Use `pwr` (R), G*Power 3.1, or PANGEA (Westfall et al., 2014, for mixed designs with multiple random effects) targeting 90% power — not the conventional 80%, which produces an unacceptably high Type II error rate for costly or long-running studies.

---

## Agent Workflows

| Agent | Function |
|---|---|
| `construct-mapper` | Maps free-text measure names and task labels to Cognitive Atlas, PsychArchives, or APA construct taxonomy; flags potential jingle-jangle conflicts and outputs a structured construct record |
| `effect-size-extractor` | Extracts Cohen's *d*, Pearson *r*, η², odds ratios, and β from statistical tables, inline text, and figure data; converts between formats using `effectsize` package formulae; propagates variance estimates |
| `bias-assessor` | Applies Cochrane RoB 2.0 (RCTs), ROBINS-I (non-randomized studies of interventions), or Newcastle-Ottawa Scale (cohort/case-control) and outputs structured domain-level judgments with supporting rationale |
| `psych-literature-scout` | Queries PsycINFO, PubMed, PsyArXiv, OpenAlex, and Google Scholar with boolean operators and MeSH/PsycINFO Thesaurus controlled vocabulary; deduplicates across sources; outputs PRISMA-compatible flow data |
| `meta-analytic-synthesizer` | Pools effects with `metafor`, computes I², τ², Q-test for heterogeneity, Egger's regression test, and produces forest-plot-ready data frames with citation-keyed rows and subgroup analysis scaffolding |

---

## Key Ontologies & Taxonomies

- **Cognitive Atlas** (`cognitiveatlas.org`): Formal ontology mapping cognitive tasks to the mental processes they measure. Use as the canonical task-to-construct bridge when integrating findings across paradigms.
- **HiTOP** (Hierarchical Taxonomy of Psychopathology): Dimensional, quantitative alternative to categorical DSM/ICD. Organizes psychopathology into spectra (Internalizing, Externalizing, Thought Disorder, Detachment, Somatoform) and facets; preferred for transdiagnostic research.
- **DSM-5-TR / ICD-11**: For clinically-oriented research where categorical diagnoses are required — for example, RCTs that must define inclusion criteria by diagnosis code.
- **NIMH RDoC** (Research Domain Criteria): Five domains (Negative Valence, Positive Valence, Cognitive Systems, Social Processes, Arousal/Regulatory Systems) × units of analysis (genes → circuits → physiology → behavior → self-report). Use when bridging clinical and basic science literatures.
- **COSMIN**: Consensus-based Standards for the selection of health Measurement INstruments. Apply the COSMIN checklist and decision rules when appraising the methodological quality of measurement studies included in a review.
- **APA Division 12 EST criteria**: Empirically Supported Treatments require at least two well-designed RCTs from independent labs demonstrating superiority or equivalence to an active comparator, or nine single-case experiments meeting design quality thresholds.

---

## Integration Points

**`paper.schema.json`** field mappings for psychology literature:

| Schema field | Psychology mapping |
|---|---|
| `construct_measured` | Map to `sub_domain` + Cognitive Atlas / APA taxonomy ID |
| `measure_name` | Full instrument name + version (e.g., `"BDI-II"`, `"Big Five Inventory-2"`) |
| `design_type` | `RCT`, `quasi-experiment`, `cross-sectional`, `longitudinal`, `meta-analysis`, `single-case` |
| `effect_size` | Numeric value (Cohen's *d*, *r*, η²) |
| `effect_size_type` | Enumerated: `d`, `r`, `eta2`, `OR`, `beta` |
| `sample_size` | Analytic N (not enrolled N) |
| `preregistered` | Boolean; OSF/AsPredicted URL if `true` |
| `registered_report` | Boolean; stage at publication (`stage_1_ipa` or `stage_2_accepted`) |
| `risk_of_bias` | Overall RoB 2.0 / ROBINS-I judgment: `low`, `some_concerns`, `high` |

**`evidence-table.schema.json`** relevant fields: `reliability` (ω value), `validity` sub-fields (construct, convergent, discriminant), analytic `N`, `RoB_score` (domain-level breakdown), `grade_certainty` (high / moderate / low / very low per GRADE).

---

## Recommended Resources

**Journals**
- *Psychological Science* — flagship empirical APS journal; accepts Registered Reports
- *Journal of Personality and Social Psychology* — social and personality; high-impact, high replication scrutiny
- *Psychological Review* — theory and integrative review; requires formal modeling
- *Journal of Experimental Psychology: General* — cognitive and experimental; rigorous methods
- *Clinical Psychology Review* — systematic reviews and meta-analyses in clinical science
- *Perspectives on Psychological Science* — methods critique, theory, and commentary
- *Advances in Methods and Practices in Psychological Science* (AMPPS) — open-science methods home base
- *PLOS ONE* — open-access empirical across all sub-disciplines

**Preprints**
- PsyArXiv (`psyarxiv.com`) — psychology-specific preprint server via the Open Science Framework; indexed by Google Scholar

**Databases**
- PsycINFO (APA) — most comprehensive for psychology; controlled vocabulary via the APA Thesaurus of Psychological Index Terms
- PubMed — essential for clinical and cognitive neuroscience overlap; MeSH terms
- OpenAlex — open, REST API-accessible; good for large-scale bibliometric and citation-network work
- Semantic Scholar — AI-assisted relevance ranking; tracks citation intent (supports / disputes / extends)

**Tools**

```r
# Core R packages for this pack
install.packages(c(
  "lavaan",       # CFA / SEM / measurement invariance
  "lme4",         # linear and generalized mixed models
  "lmerTest",     # Satterthwaite df and p-values for lme4
  "metafor",      # meta-analysis (rma, rma.mv, escalc, forest, funnel)
  "BayesFactor",  # Bayes factors (ttestBF, correlationBF, anovaBF)
  "TOSTER",       # equivalence testing (TOST procedure)
  "mirt",         # IRT models (2PL, GRM, MIRT)
  "psych",        # omega reliability, EFA, describe
  "qgraph",       # network psychometrics (regularized partial correlations)
  "bootnet",      # network stability (case-dropping bootstrap)
  "effectsize",   # effect size computation and conversion
  "pwr"           # power analysis for standard designs
))
```

- **JASP** (`jasp-stats.org`): GUI Bayesian and frequentist statistics with reproducible `.jasp` analysis files; directly integrates with OSF
- **G*Power 3.1**: Standalone power analysis covering t-tests, ANOVA, regression, correlation, χ², and mixed designs
- **jamovi**: R-powered GUI; good for teaching and rapid exploratory analysis; exports syntax for reproducibility
- **OSF** (`osf.io`): Preregistration, materials, data hosting, and project coordination under FAIR principles
