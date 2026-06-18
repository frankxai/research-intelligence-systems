# Learning Science Research Intelligence Pack

## Overview

This pack provides interdisciplinary research intelligence for the science of learning, spanning cognitive psychology of learning, educational psychology, instructional design science, learning analytics, and the science of expertise. It aggregates evidence-based principles, methodological standards, data infrastructure references, and agentic workflows to support systematic synthesis of what works in learning contexts. Designed for researchers, educational data scientists, and AI agents tasked with evaluating interventions, interpreting effect sizes, modeling learner knowledge states, and connecting empirical findings to actionable instructional design decisions.

---

## Domain Scope

### Cognitive Science of Learning

The empirical core of this sub-discipline rests on a small set of highly replicated memory and practice phenomena. Retrieval practice (the testing effect) demonstrates that attempting to recall information from memory produces substantially better long-term retention than re-studying — Roediger & Karpicke (2006) established this across content domains with effect sizes exceeding re-reading by d > 0.50. Spaced repetition (the spacing effect) shows that distributing practice across time intervals outperforms massed practice, with Cepeda et al. (2006) meta-analyzing 254 studies and finding optimal spacing ratios vary with the target retention interval. Interleaving (mixing problem types during practice) and elaborative interrogation (generating explanatory "why" answers) round out the core set of desirable difficulties with strong meta-analytic support across K–12 and higher education settings.

### Educational Psychology

Motivation research is anchored by self-determination theory (Deci & Ryan), which distinguishes intrinsic motivation, identified regulation, and external regulation, and predicts that autonomy-supportive instruction produces deeper learning and greater persistence. Expectancy-value theory (Eccles et al.) operationalizes task value as attainment, intrinsic, utility, and cost components — directly informing why students disengage from STEM tracks. Self-regulation and metacognition research (Zimmerman, Flavell) documents the role of planning, monitoring, and evaluation in academic achievement, with formative assessment (Black & Wiliam 1998) providing the instructional mechanism: high-quality feedback loops during learning produce effect sizes d ≈ 0.40–0.70, among the largest intervention effects in the educational literature.

### Instructional Design Science

The ADDIE model (Analyze, Design, Develop, Implement, Evaluate) remains the dominant practitioner framework but has been critiqued for its linear sequence masking the iterative, evidence-driven nature of effective design. Cognitive load theory (Sweller 1988, 1994) provides a more rigorous scientific foundation: working memory is a bottleneck, so instructional design must minimize extraneous cognitive load while supporting schema formation and proceduralization. The worked-example effect — where studying solved examples outperforms equivalent time problem-solving for novices — is one of the most replicated findings in instructional science. Mayer's cognitive theory of multimedia learning operationalizes these principles into 12 design principles (modality, coherence, signaling, segmenting, pre-training, and others), each supported by controlled experiments synthesized in his 2009 handbook.

### Learning Analytics & Educational Data Mining

Learning analytics (LA) and educational data mining (EDM) differ in emphasis: LA prioritizes actionable feedback to instructors and students; EDM prioritizes discovery of new patterns in learner behavior data. Both operate on clickstream, assessment, and interaction data from learning management systems, intelligent tutoring systems, and MOOCs. xAPI (Experience API) and LRS infrastructure enable event-level tracking across heterogeneous platforms, producing learner-level process data at millisecond granularity. Key applications include knowledge component (KC) modeling, which maps learner performance sequences to underlying skill mastery; early warning systems predicting at-risk students weeks before course failure; and dashboards providing instructors real-time actionable signals.

### Expertise Research

Deliberate practice theory (Ericsson, Krampe & Tesch-Römer 1993) proposes that expert performance results from thousands of hours of effortful, feedback-rich practice targeting performance weaknesses — not mere experience accumulation. Chase & Simon's (1973) chunking hypothesis showed chess masters perceive meaningful configurations rather than individual pieces, explaining both their superior memory for game positions and their faster pattern recognition relative to novices. The "10,000-hour rule" (popularized by Gladwell) has been significantly qualified: Macnamara et al.'s (2014) meta-analysis of 88 studies found deliberate practice accounted for only 12% of variance in performance across domains, with domain, age of starting, and genetic factors contributing additional variance. Knowledge compilation (Anderson's ACT-R theory) describes the shift from declarative to procedural knowledge as skills become automated through practice.

### Technology-Enhanced Learning

Intelligent tutoring systems (ITS) — particularly Cognitive Tutor (Carnegie Learning) and ASSISTments — provide individualized problem sequences, hints, and error-specific feedback, producing consistent effect sizes of d ≈ 0.35–0.76 in controlled evaluations. Adaptive learning platforms (Knewton, Smart Sparrow, McGraw-Hill ALEKS) apply psychometric models to dynamically route students through content based on estimated mastery. The emerging field of AIED (Artificial Intelligence in Education) encompasses automated essay scoring, dialogue-based tutors, emotion detection, and, most recently, the integration of large language models as tutoring agents, pedagogical co-designers, and automated feedback generators — raising both pedagogical opportunities and concerns around validity, equity, and over-reliance.

---

## Evidence-Based Learning Principles

### Desirable Difficulties (Bjork & Bjork)

Robert Bjork's desirable difficulties framework distinguishes conditions that feel easier but produce less durable learning from conditions that feel harder but produce stronger, more transferable memory traces.

- **Spacing effect**: Distributing practice sessions across time (e.g., Day 1, Day 3, Day 7) substantially outperforms massed same-day practice for long-term retention, even when total time-on-task is equated. Cepeda et al. (2006) meta-analysis (254 experiments) quantified spacing advantages as a function of retention interval.
- **Interleaving effect**: Practicing different problem types in interleaved sequences (ABCABC) produces better discrimination and transfer than blocked practice (AABBCC), even though blocked practice feels more fluent during training. Taylor & Rohrer (2010) demonstrated this for mathematics; Kornell & Bjork (2008) for inductive category learning.
- **Generation effect**: Generating an answer — even an incorrect one — before receiving the correct answer produces better retention than reading the answer directly. Closely related to the pre-testing and hypercorrection effects, where confident errors that are corrected are remembered better than uncertain ones.
- **Variability of practice**: Training on varied exemplars (surface features, contexts, formats) reduces performance during training but enhances transfer to novel instances; particularly important for procedural and perceptual-motor learning.

### Cognitive Load Theory (Sweller)

Cognitive load theory (CLT) proposes that working memory capacity is severely limited and that all instructional design must be evaluated against its load profile.

- **Intrinsic load**: Determined by element interactivity — the number of interacting elements that must be held simultaneously in working memory — and moderated by learner expertise. Cannot be reduced without changing content; managed via sequencing and scaffolding.
- **Extraneous load**: Imposed by poor instructional design — split-attention materials (diagrams separated from explanatory text), redundant information channels, irrelevant decorative details. Must be minimized.
- **Germane load**: Cognitive effort directed toward schema construction and automation. The expertise reversal effect shows that techniques effective for novices (worked examples, redundant explanations) become extraneous load for more proficient learners.
- **Key design effects**: split-attention effect (integrate spatially or temporally separated information), redundancy effect (eliminate redundant channels for proficient learners), modality effect (prefer spoken + visual over text + visual for dual-coding benefits).

### Multimedia Learning (Mayer's 12 Principles)

Mayer's cognitive theory of multimedia learning (CTML, 2009) proposes dual channels (auditory/verbal and visual/pictorial), limited capacity in each, and active processing through selecting, organizing, and integrating. The 12 evidence-based design principles — each derived from controlled experiments — include:

- **Modality principle**: People learn better from words + graphics than from text + graphics, because speech and imagery use separate channels.
- **Coherence principle**: Remove extraneous material (background music, decorative graphics, tangential text) even when it seems engaging or motivating.
- **Signaling principle**: Cues that highlight organization and key ideas (arrows, color coding, outlines) improve learning without adding content.
- **Segmenting & pre-training**: Learner-paced segments and prior training on component concepts reduce cognitive overload in complex animations and dynamic visualizations.

### Retrieval Practice

The testing effect (Roediger & Karpicke 2006) established that a single free-recall test after studying produced far better 1-week retention than three additional study periods. Key moderators: corrective feedback enhances retrieval practice substantially; the advantage holds across verbal and conceptual content, across age groups (elementary through graduate), and in authentic classroom settings. Retrieval-augmented studying protocols — interleaving short low-stakes quiz segments into reading — are among the highest-leverage low-cost interventions identified in applied cognitive psychology.

### Formative Assessment (Black & Wiliam 1998)

Black and Wiliam's landmark 1998 review synthesized evidence across 250+ studies and concluded that improving formative assessment practices — defined as assessment used to adapt instruction during the learning process — produces among the largest effect sizes of any school-based intervention (d ≈ 0.40–0.70). Key mechanisms include: hinge questions (diagnostic multiple-choice questions designed to surface specific misconceptions), exit tickets, peer assessment (which requires students to internalize success criteria), and self-assessment against explicit standards. The critical theoretical contribution is that feedback must close the loop: information about gaps must produce instructional action, not merely a grade.

---

## Data Standards & Infrastructure

- **xAPI (Experience API / Tin Can)**: Actor–verb–object statement structure (`{"actor": ..., "verb": ..., "object": ...}`) transmitted to a Learning Record Store (LRS). Enables tracking of learning events across mobile apps, simulations, on-the-job activities, and LMS platforms in a unified, queryable log. Key verbs: `attempted`, `completed`, `passed`, `answered`, `progressed`.
- **IMS Global Standards**: LRS interoperability specifications; QTI (Question & Test Interoperability) for portable item formats; Caliper Analytics as an alternative event framing to xAPI, widely adopted in North American higher education.
- **PSLC DataShop** (`datashop.web.cmu.edu`): The largest open repository of educational interaction data (~300 datasets), supporting KC model creation, learning curve analysis, and AFM (Additive Factors Model) fitting. Enables reanalysis and model comparison across ITS contexts.
- **Open University Learning Analytics Dataset (OULAD)**: Anonymized data for 32,000+ students across 7 courses, including demographics, assessment scores, and VLE interaction logs. Widely used benchmark for early warning systems and dropout prediction models.
- **IES What Works Clearinghouse (WWC)**: U.S. Department of Education's evidence clearinghouse. Applies group design standards (RCT, quasi-experimental) and rates studies as "Meets WWC Standards Without Reservations," "With Reservations," or "Does Not Meet." ESSA evidence tiers: I (strong/RCT), II (moderate/quasi-experimental), III (promising/pre-post), IV (demonstrates rationale).
- **Learning Engineering (IEL)**: An emerging discipline combining learning science, human-centered design, and data engineering to iteratively improve learning experiences using evidence from deployment — operationalizing the "What Works" pipeline into continuous improvement cycles.

---

## Reproducibility & Open Science

- **IES WWC Standards**: Rigorous review protocol covering attrition thresholds, baseline equivalence, clustering corrections, and implementation fidelity reporting. Single-case design standards (ABAB, multiple baseline) are separately specified.
- **CONSORT-SPI**: CONSORT extension for Social and Psychological Interventions; relevant for reporting educational RCTs with appropriate detail (randomization unit, blinding, fidelity checks, implementation monitoring).
- **Preregistration**: OSF Registries and AEA RCT Registry for field experiments. Preregistering hypothesis, design, and analysis plan separates confirmatory from exploratory findings, a critical distinction given publication pressure in education research.
- **Registered Reports**: Offered at *npj Science of Learning*, *Educational Psychology Review*, and *British Journal of Educational Psychology*; in-principle acceptance before data collection eliminates publication bias on null results.
- **ERIC Open Access**: ERIC (`eric.ed.gov`) provides ED-number indexed full-text access to many technical reports, government-funded studies, and conference papers not indexed in PsycINFO. ED numbers persist as stable archival identifiers.
- **Open Data & FERPA**: Educational data de-identification is governed by FERPA (U.S.) and GDPR (EU). Best practice: release aggregate KC-level data with student identifiers hashed; document suppression rules for cells with n < 5. Creative Commons CC-BY or CC0 licensing for derived datasets.
- **Replication landscape**: Education research has a replication problem concentrated in small-n laboratory studies. WWC replication requirements mandate independent replications before a "Strong" evidence designation can be assigned.

---

## Modern Methods & Statistics

- **Multilevel Modeling (MLM)**: Students nested in classrooms nested in schools produces non-independent residuals that violate OLS assumptions. `lme4` (R) and HLM7 are standard tools. ICC (intraclass correlation) at the classroom level typically runs 0.10–0.25 in U.S. data; ignoring it inflates Type I error substantially. Random slopes for time extend MLM to longitudinal growth curve modeling.
- **Causal Inference for Educational Interventions**: RCT is the gold standard but is rarely feasible at scale. Regression discontinuity design (RDD) exploits cutoff-based assignment rules (e.g., test score thresholds for remediation). Instrumental variables (IV) leverage natural experiments (lottery-based school assignment). Difference-in-differences (DiD) uses parallel trends between treated and untreated groups across time. Synthetic control constructs a weighted counterfactual for single-unit policy evaluations.
- **Learning Curve Analysis**: The power law of practice describes accuracy and RT improvement: `T = aN^{-b}` where N is the practice trial count. Fitting learning curves to KC-level accuracy data in DataShop identifies poorly-defined KCs (flat curves) from well-defined ones (steep drop to asymptote), informing KC model refinement.
- **Knowledge Tracing**: Bayesian Knowledge Tracing (BKT; Corbett & Anderson 1994) models student mastery as a hidden Markov model with four parameters: P(L₀) prior mastery, P(T) learning rate, P(G) guess rate, P(S) slip rate. Deep Knowledge Tracing (DKT; Piech et al. 2015) uses LSTMs to model sequential interaction data without explicit KC annotations. SAKT (self-attention knowledge tracing) and AKT (monotonic attention knowledge tracing) are transformer-based extensions with stronger empirical performance on benchmark datasets.
- **NLP for Education**: Automated essay scoring (AES) systems (e-rater, Turnitin) use feature-based and neural models evaluated against human rater agreement. Dialogue act classification labels tutor–student exchanges (hint request, correct answer, off-task, metacognitive comment). LLM-based feedback generation is now an active research area with evaluation rubrics covering specificity, accuracy, and actionability.
- **Computerized Adaptive Testing (CAT)**: IRT-based item selection maximizes Fisher information at the current theta (ability) estimate. Exposure control (Sympson–Hetter, shadow tests) prevents item overuse and content security failures. Termination criteria include fixed length, standard error threshold, or elapsed time.

---

## Agent Workflows

| Agent | Function |
|---|---|
| `learning-literature-scout` | Queries ERIC, PsycINFO, Google Scholar, and SSRN for learning science papers; tags each retrieved study with ESSA evidence tier and WWC standards-met status |
| `effect-benchmarker` | Compares intervention effect sizes against WWC statistical significance thresholds and Hattie's d = 0.40 meta-analytic hinge point; flags trivial, small, medium, and large effects with contextual interpretation |
| `curriculum-mapper` | Maps learning objectives to Bloom's Revised Taxonomy (cognitive process × knowledge dimension), Webb's Depth of Knowledge (DoK 1–4), and SOLO taxonomy levels |
| `learning-analytics-agent` | Parses xAPI statement logs, builds KC models from transaction data, fits learning curves, and generates accuracy-by-opportunity visualizations for instructional review |
| `intervention-typologist` | Assigns BCT (Behaviour Change Technique) taxonomy codes and COM-B mechanism labels to educational interventions to enable cross-study mechanism comparison and causal model building |

---

## Key Frameworks & Taxonomies

- **Bloom's Revised Taxonomy** (Anderson & Krathwohl 2001): Six cognitive process levels (Remember, Understand, Apply, Analyze, Evaluate, Create) crossed with four knowledge dimensions (Factual, Conceptual, Procedural, Metacognitive), producing a 24-cell matrix for aligning objectives, instruction, and assessment.
- **Webb's Depth of Knowledge (DoK 1–4)**: DoK 1 = recall and reproduction; DoK 2 = skills and concepts; DoK 3 = strategic thinking (multi-step, non-routine reasoning); DoK 4 = extended thinking (complex investigation, synthesis across contexts). Used in state standards alignment and high-stakes item writing.
- **SOLO Taxonomy** (Biggs & Collis 1982): Five levels of structural complexity in a learner's response — prestructural, unistructural (one relevant element), multistructural (several disconnected elements), relational (integrated into a coherent structure), extended abstract (generalized to new domains). Applicable across age levels and disciplines as a formative feedback tool.
- **Gagné's Conditions of Learning**: Nine events of instruction (gain attention, inform objectives, stimulate recall of prior learning, present content, provide learning guidance, elicit performance, provide feedback, assess performance, enhance retention and transfer) mapped to five learning outcome categories (verbal information, intellectual skills, cognitive strategies, attitudes, motor skills).
- **CEFR** (Common European Framework of Reference for Languages): Six proficiency levels A1–C2 with Can-Do descriptor criteria; the dominant framework for language learning research, proficiency assessment alignment, and adaptive language ITS design.

---

## Integration Points

**`paper.schema.json` relevant fields**

| Field | Notes |
|---|---|
| `intervention_type` | e.g., `retrieval_practice`, `spaced_repetition`, `ITS`, `formative_assessment` |
| `study_type` | `RCT`, `quasi-experimental`, `observational`, `single-case` |
| `sample_size` | Report at unit of randomization (student / classroom / school) |
| `sample_description.age_group` | `elementary`, `middle`, `secondary`, `higher_ed`, `adult` |
| `sample_description.grade_level` | K–12 grade or postsecondary year |
| `effect_size` | Standardized mean difference or log-odds ratio |
| `effect_size_type` | `Cohen_d`, `Hedges_g`, `OR`, `RR`, `eta_sq` |
| `design_type` | `between-subjects`, `within-subjects`, `mixed`, `single-case_ABAB` |

**`evidence-table.schema.json` relevant fields**

| Field | Notes |
|---|---|
| `essa_tier` | I (strong), II (moderate), III (promising), IV (rationale only) |
| `wwc_standards_met` | `Meets`, `Meets_with_reservations`, `Does_not_meet` |
| `n_students` / `n_classrooms` / `n_schools` | Reported at each nested level |
| `implementation_fidelity` | Percentage of intended components delivered; required for WWC review |

---

## Recommended Resources

### Journals
- *Educational Psychologist* — theoretical review, APA Division 15 flagship
- *npj Science of Learning* (Nature Publishing Group) — open access, registered reports
- *Journal of Educational Psychology* — empirical, APA flagship for educational research
- *Learning and Instruction* — European Science of Learning community
- *British Journal of Educational Psychology* — strong applied and formative assessment coverage
- *Educational Technology Research & Development* — instructional design and AIED

### Preprints
- **PsyArXiv** (`psyarxiv.com`) — psychological and educational sciences
- **EdArXiv** (`edarxiv.org`, via OSF) — education-specific preprint server

### Databases
- **ERIC** (`eric.ed.gov`) — U.S. DOE education research index, many open-access full texts
- **PsycINFO** (APA) — psychology and behavioral science; citation-linked
- **Google Scholar** — broad coverage including grey literature and conference proceedings
- **SSRN** — working papers, especially economics of education and policy evaluations

### Data Repositories
- **PSLC DataShop** (`datashop.web.cmu.edu`) — ITS interaction data, KC models, learning curve tools
- **OULAD** (Open University Learning Analytics Dataset) — VLE interaction and demographic data for 32,000+ students
- **PISA Public Data** (OECD) — cross-national student achievement, motivation, and SES data for 80+ countries

### Tools & Software
- **R**: `lme4` (multilevel modeling), `lavaan` (structural equation modeling), `pwr` (power analysis), `BayesFactor` (Bayes factor hypothesis testing)
- **Python**: `pyBKT` (Bayesian Knowledge Tracing), `scikit-learn` (predictive modeling for learning analytics), `pandas` and `seaborn` (learning curve plotting and visualization)
- **WWC Study Review Tool**: Standardized protocol workbook for applying WWC group design standards to individual studies; required for systematic review submissions to the clearinghouse
