# Behavioral Science Research Intelligence Pack

## Overview

This pack provides research intelligence for the evidence-based science of human behavior, bridging behavioral economics, nudge theory, habit science, decision science, health behavior, and population-level behavioral interventions. It covers the full range of empirical methods used to understand and change behavior — from controlled laboratory experiments and large-scale field RCTs to quasi-experimental designs and structural estimation of behavioral models. The pack is designed for policy researchers, behavior change practitioners, and AI agents synthesizing what actually works in changing human behavior at scale, with particular attention to effect size benchmarks, replication reliability, and implementation fidelity.

Behavioral science sits at the intersection of psychology, economics, public health, and organizational theory. This pack operationalizes that convergence: it maps domain frameworks (COM-B, EAST, BCTTv1, MINDSPACE) to literature search strategies, connects agent workflows to standard taxonomies used in systematic reviews, and tracks open science infrastructure (preregistration registries, reporting checklists, registered reports) that separates credible evidence from noise. The result is an intelligence layer purpose-built for practitioners who need not just summaries of findings but actionable guidance on which findings to trust and which mechanisms to target.

---

## Domain Scope

### Behavioral Economics
Rooted in Kahneman and Tversky's Prospect Theory (1979) and extended through Thaler's mental accounting and status quo bias work, behavioral economics documents systematic departures from classical rationality. Loss aversion (losses hurt roughly twice as much as equivalent gains feel good), framing effects, and default effects form the empirical core. Thaler and Sunstein's *Nudge* (2008) translated these findings into choice architecture — the design of decision environments that steer behavior without restricting options.

### Decision Science
Decision science studies how people make choices under risk and uncertainty, over time, and across multiple attributes. Intertemporal choice research (hyperbolic discounting, present bias) explains why people fail to follow through on long-run plans. Moral decision-making research — from trolley problem variants to real allocation dilemmas — maps the conditions under which deontological versus utilitarian reasoning dominates. Multi-attribute decision-making research informs product design, policy evaluation, and medical decision support.

### Health Behavior
The dominant models are the Health Belief Model (perceived susceptibility × severity × benefits − barriers), the Theory of Planned Behavior/TRA (attitudes + norms + perceived behavioral control → intention → behavior), and the COM-B model (see Frameworks section). Habit formation follows the cue-routine-reward loop (Duhigg; Wood & Neal), and the Behavior Change Wheel (Michie et al. 2011) provides a structured process for selecting interventions that target the correct behavioral driver. Health behavior RCTs underpin clinical guidelines and public health campaigns.

### Social Behavior and Norms
Cialdini's foundational work distinguishes descriptive norms (what most people do) from injunctive norms (what most people approve of). Norm-based nudges — famously, hotel towel reuse messages and utility bill comparisons (Opower/Oracle Utilities) — produce modest but reliable effects at near-zero marginal cost. Social proof, conformity, and peer influence also drive health behaviors (vaccination, smoking cessation, physical activity), with effects moderated by reference group salience and perceived similarity.

### Organizational Behavior
Organizational behavior (OB) research covers commitment, organizational citizenship behavior (OCB — discretionary pro-organizational acts), counterproductive work behavior (CWB), and psychological safety (Edmondson 1999). Burnout research (Maslach 3-factor model: exhaustion, depersonalization, reduced efficacy) has direct policy implications for workforce design and management. The field increasingly uses experience-sampling methods (ESM/EMA) and passive sensing to capture within-person behavioral dynamics.

### Environmental and Sustainable Behavior
Pro-environmental behavior (PEB) interventions range from green defaults (opt-out renewable energy tariffs) to carbon footprint feedback to social norm nudges on energy use. Green nudges reliably reduce energy and water consumption by 5–15% in field settings. Sustainable consumption research examines the value-action gap, moral licensing, and rebound effects. Meta-analyses (Nisa et al. 2019, *Nature Energy*) show that combining multiple small-impact nudges may not equal the sum of their parts.

---

## Behavioral Frameworks and Models

### COM-B Model (Michie et al. 2011)
Capability (physical and psychological), Opportunity (physical and social), and Motivation (reflective and automatic) jointly determine Behavior. The model functions as a diagnostic tool: before selecting an intervention, an analyst must identify which COM-B component(s) are the binding constraints for the target behavior in the target population. Misdiagnosis (e.g., running an information campaign when the barrier is Opportunity, not Capability) is a primary cause of ineffective interventions.

### Behavior Change Technique Taxonomy v1 (Michie et al. 2013)
BCTTv1 codifies 93 distinct behavior change techniques organized into 16 clusters (goals and planning, feedback and monitoring, social support, shaping knowledge, natural consequences, and so on). The taxonomy enables systematic coding of intervention content, comparison across trials, and identification of which BCTs drive effects in meta-analyses. The BCTTv1 coding manual and training materials are available at bcttaxonomy.com; inter-rater reliability (kappa) benchmarks exist for most clusters.

### EAST Framework (Behavioural Insights Team)
The Behavioural Insights Team's EAST framework offers a practitioner shorthand: make the desired behavior Easy (reduce friction, simplify the default), Attractive (use incentives, personalization, salience), Social (use norms, networks, commitment devices), and Timely (intervene at moments of transition or high receptivity). EAST is less mechanistic than COM-B but easier to apply rapidly in policy contexts where time and data are limited.

### MINDSPACE (Dolan et al. 2010)
Nine high-impact behavioral influences: Messenger (who delivers the message), Incentives (loss-framed vs. gain-framed), Norms (social proof), Defaults (opt-in vs. opt-out), Salience (attention capture), Priming (contextual cues that activate schemas), Affect (emotional valence), Commitments (pre-commitment devices), and Ego (identity consistency). Originally developed for the UK Cabinet Office, MINDSPACE remains a widely-cited policy framework for non-regulatory interventions.

### Fogg Behavior Model
B = MAP: Behavior happens when Motivation, Ability, and a Prompt converge simultaneously. The model emphasizes that high motivation cannot compensate for low ability (and vice versa), and that even well-designed triggers fail without sufficient motivation-ability alignment. Practical implication: increase ability first (reduce friction), then trigger behavior at the moment of peak motivation.

### Protection Motivation Theory (Rogers 1975, revised 1983)
PMT posits that health behavior change results from two parallel appraisals: threat appraisal (perceived severity × susceptibility, moderated by maladaptive rewards) and coping appraisal (response efficacy × self-efficacy, moderated by response costs). Protection motivation is highest when threats are perceived as severe and when individuals believe the recommended response is both effective and within their capacity. Applied extensively in health risk communication, vaccination uptake, and cybersecurity behavior.

---

## Reproducibility and Open Science

Preregistration infrastructure: the AEA RCT Registry (aeaweb.org/rct) is standard for development economics field experiments; OSF Registries cover lab, online, and survey experiments; ClinicalTrials.gov and ISRCTN serve health behavior RCTs; RIDIE (registry for international development impact evaluations) covers J-PAL and IPA-affiliated trials.

**Pre-Analysis Plans (PAPs)** should specify primary vs. secondary outcomes, subgroup analyses, covariate adjustment strategy, and multiple testing correction (Bonferroni, Benjamini-Hochberg, or pre-specified family-wise error rate) before data collection ends. J-PAL and IPA publish PAP standards and templates; the World Bank DIME wiki provides a practical implementation guide.

Reporting standards: CONSORT 2010 for RCTs (with cluster-RCT and non-inferiority extensions), TIDieR checklist for intervention description fidelity (ensures replication is possible), STROBE for observational behavioral studies, and GRADE for rating certainty of evidence from behavioral intervention systematic reviews.

Registered Reports — where peer review occurs before data collection — are available at Journal of Behavioral Decision Making, Organizational Behavior and Human Decision Processes, Health Psychology, and Psychological Science. The replication crisis in behavioral economics (Camerer et al. 2016 replicated 11 of 18 published results at roughly half the original effect size) and the repeated failures to replicate "classic" nudge findings underscore the value of preregistration and large-sample replication before citing a finding as policy-ready.

---

## Field Experiment Infrastructure

**A/B testing statistical design**: two-proportion z-test for conversion rate outcomes; minimum detectable effect (MDE) calculation requires specifying baseline rate, desired power (80% or 90%), alpha (typically 0.05 two-sided), and expected N. Over-powered studies waste resources; under-powered studies produce unreliable estimates.

**Sequential testing**: Sequential Probability Ratio Test (SPRT) and always-valid inference methods (Johari et al. 2017; implemented in Optimizely Stats Engine, Eppo) permit continuous monitoring without inflating Type I error. This resolves the "peeking problem" endemic to fixed-horizon tests analyzed mid-run.

**Randomization methods**: simple randomization, stratified randomization (block by key covariates), cluster randomization (randomize at the group level — school, clinic, neighborhood), and stepped-wedge designs (all clusters eventually receive treatment, staggered rollout). Balance tables (covariate balance F-tests) are mandatory in published RCT reports.

**Attrition and noncompliance**: intent-to-treat (ITT) analysis preserves randomization but dilutes effect estimates when take-up is low. Per-protocol analysis is biased; CACE (Complier Average Causal Effect) via instrumental variable estimation with treatment assignment as instrument (Bloom 1984) recovers the effect for compliers. Differential attrition by condition is a threat to internal validity; CONSORT flow diagrams must document it.

---

## Modern Methods and Statistics

**Causal inference hierarchy**: RCTs remain the gold standard; quasi-experimental methods (difference-in-differences, regression discontinuity, instrumental variables, synthetic control) fill gaps where randomization is infeasible. Propensity score matching reduces confounding in observational studies but cannot eliminate unmeasured confounders.

**Meta-analysis for behavioral interventions**: `metafor` in R (particularly `rma.mv` for correlated/dependent effect sizes from multiple-outcome studies), `robumeta` for robust variance estimation (Hedges et al. 2010), and three-level meta-analytic models for nested data (studies within research groups). Funnel plot asymmetry and Egger's test flag potential publication bias; trim-and-fill and PET-PEESE corrections adjust for it.

**Heterogeneity of treatment effects (HTE)**: pre-specified subgroup analyses (never post-hoc), and — for large datasets — Conditional Average Treatment Effect (CATE) estimation with causal forests (`grf` package, Wager & Athey 2018); X-learner and DR-learner for high-dimensional covariate settings.

**Survey experiments and conjoint analysis**: vignette studies isolate causal effects of framing; conjoint analysis (`cregg`, `cjoint` in R) estimates willingness-to-pay and attribute importance from multi-profile choice tasks.

**Structural behavioral models**: Cumulative Prospect Theory parameter estimation (probability weighting γ, value function curvature α, loss aversion λ) via maximum likelihood or Bayesian estimation using individual-level choice data. Discrete choice models (`mlogit`, `logitr`): mixed logit accommodates preference heterogeneity across respondents.

---

## Agent Workflows

| Agent | Function |
|---|---|
| `behavioral-literature-scout` | Targets JBDM, Psychological Science, OBHDP, Nature Human Behaviour, JEBO, Health Psychology, PLOS ONE; filters for preregistered studies and effect size reporting |
| `intervention-cataloger` | Extracts BCT codes (BCTTv1), target behavior, mechanism of action (COM-B component), delivery mode, setting (country, clinical/community/online), and sample description |
| `effect-benchmarker` | Compares reported effect sizes against meta-analytic benchmarks by behavior domain and BCT cluster; flags unusually large effects (winner's curse from underpowered studies) |
| `policy-relevance-scorer` | Assesses scalability, cost-effectiveness (cost per unit behavior change), implementation fidelity requirements, political acceptability, and autonomy concerns (nudge ethics) |
| `paap-reviewer` | Checks alignment between a paper's reported analysis and its preregistration or PAP; flags unregistered outcomes, undisclosed subgroup analyses, and outcome switches |

---

## Key Resources and Registries

- **Registries**: AEA RCT Registry, OSF Registries, ClinicalTrials.gov, ISRCTN, RIDIE
- **BCTTv1 taxonomy**: bcttaxonomy.com — coding manual, training, inter-rater reliability guidance
- **Cochrane Collaboration**: gold-standard systematic reviews for health behavior interventions
- **Campbell Collaboration**: social behavioral interventions (education, crime prevention, welfare programs)
- **BIT (Behavioural Insights Team)**: applied nudge research library, EAST applications, government RCTs

---

## Integration Points

**`paper.schema.json`**: `intervention_type` (mapped to BCT cluster), `design_type` (RCT / quasi-experimental / observational), `sample_size`, `sample_description` (country, setting), `effect_size` (Cohen's d or OR with CI), `preregistered` (boolean + registry URL), `open_data` (boolean + repository URL).

**`evidence-table.schema.json`**: `BCT_codes` column (array of BCTTv1 codes), `target_behavior`, `delivery_mode` (individual / group / digital / mass media / environmental), `setting`, `effect_size`, `NNT` (number needed to treat, for health outcomes), `GRADE_certainty` (high / moderate / low / very low).

---

## Recommended Resources

**Journals**: Journal of Behavioral Decision Making, Organizational Behavior and Human Decision Processes, Nature Human Behaviour, Journal of Experimental Psychology: Applied, Psychological Science, Health Psychology, PLOS ONE, Journal of Economic Behavior and Organization

**Preprints**: PsyArXiv, SSRN, OSF Preprints

**Databases**: PsycINFO, Cochrane Library, Campbell Collaboration library, Google Scholar, Web of Science

**Software**: R (`metafor`, `grf`, `mlogit`, `lme4`, `cjoint`, `robumeta`, `cregg`), Stata (standard in development economics field experiments), Python (`causalml`, `econml`, `dowhy`)

**Infrastructure**: AEA RCT Registry, J-PAL Abdul Latif Jameel Poverty Action Lab (data and evaluation resources), IPA (Innovations for Poverty Action), Open Science Framework
