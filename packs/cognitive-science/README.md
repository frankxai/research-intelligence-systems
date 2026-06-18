# Cognitive Science Research Intelligence Pack

## Overview

This pack provides research intelligence for the interdisciplinary science of mind — spanning computation, representation, reasoning, language, perception, and action. It supports systematic literature synthesis, computational model extraction, and theoretical framework mapping across the full breadth of cognitive science, from experimental psycholinguistics to formal Bayesian models of perception. Coverage extends across paradigms and levels of analysis: behavioral, computational, neural, and philosophical.

Cognitive science integrates artificial intelligence, linguistics, neuroscience, philosophy of mind, and psychology into a unified project of explaining how minds work. This pack is designed for agents and researchers synthesizing theoretical and empirical work across those constituent disciplines — navigating fragmented literatures, identifying convergent findings, and tracking the evolving relationship between classical symbolic models, probabilistic frameworks, and modern deep learning approaches to cognition.

---

## Domain Scope

### Cognitive Architecture

Cognitive architectures such as ACT-R (Anderson et al.) and SOAR (Newell, Laird) specify the fixed structural and procedural constraints within which cognition operates — production rules, memory modules, and performance mechanisms. Global Workspace Theory (Baars) and predictive processing frameworks (Clark, Friston) offer alternative architectural proposals emphasizing broadcasting dynamics and hierarchical generative models respectively. Architectural assumptions are not neutral: they constrain which phenomena count as explananda, what counts as a model, and how cognitive components interact under time pressure and resource limitation.

### Reasoning & Decision-Making

Dual-process theory distinguishes fast, automatic Type 1 processing from slow, deliberate Type 2 processing; Stanovich and Evans have refined Kahneman's System 1/2 popularization into a more technically precise account with distinct theoretical commitments. Kahneman and Tversky's heuristics-and-biases program established systematic deviations from classical rationality norms, while Gigerenzer's ecological rationality framework reframes these findings — arguing that heuristics are often adaptive responses to real-world statistical structure rather than errors. Bayesian rationality models (Griffiths, Tenenbaum) offer a third position: that human cognition approximates optimal inference under uncertainty, with apparent biases explained by prior structure or sampling limitations.

### Language & Cognition

Psycholinguistics investigates how language is produced, perceived, and comprehended in real time, with paradigms including garden-path sentence processing, syntactic priming, and self-paced reading. Embodied accounts of language comprehension (Glenberg, Barsalou) argue that meaning is grounded in sensorimotor simulation rather than abstract symbolic representations, while distributional semantics models (word2vec, GloVe, large language models) provide formal accounts of lexical meaning from co-occurrence statistics. The relationship between language and thought — Whorfian linguistic relativity, conceptual structure, and the semantics-pragmatics interface — remains an active empirical and theoretical debate.

### Perception & Action

Gibson's affordance theory holds that perception is directly informative about action possibilities, without requiring intermediate representational computation — organisms perceive the environment in terms of what it enables them to do. Embodied cognition (Varela, Lakoff, Johnson) extends this insight, arguing that cognitive structures are constitutively shaped by the body's morphology and sensorimotor capacities, challenging the view that cognition is substrate-independent computation. Perception-action loops, predictive coding accounts of perception, and active inference frameworks (Friston) unify perception and action under a single probabilistic framework in which organisms act to minimize prediction error.

### Memory Systems

The Baddeley and Hitch working memory model distinguishes a central executive from phonological loop and visuospatial sketchpad slave systems, with later additions of the episodic buffer; working memory capacity limits (~4 chunks) predict a range of cognitive performance outcomes. Long-term memory divides into episodic (autobiographical events), semantic (world knowledge), and procedural (skill-based) systems, supported by dissociable neural substrates with distinct learning dynamics. Memory reconsolidation — the finding that retrieved memories become labile and can be modified or extinguished — has significant implications for understanding memory updating, trauma, and learning.

### Attention & Executive Control

Executive functions encompass a family of control processes — inhibition, updating, and task switching — whose unity and diversity have been formally characterized by Miyake et al.'s latent variable analyses. Task switching costs (both switch costs and mixing costs) index the efficiency of reconfiguring cognitive sets, and are sensitive to aging, individual differences in fluid intelligence, and pharmacological manipulation. Top-down (goal-directed) and bottom-up (stimulus-driven) attention interact in models such as Desimone and Duncan's biased competition account, with frontoparietal networks implementing the top-down biasing of sensory processing.

### Computational Cognitive Science

Probabilistic Bayesian models treat cognition as inference under uncertainty, with priors encoding knowledge and likelihoods encoding the relationship between hypotheses and data; this framework has been applied to perception, concept learning, causal reasoning, and language comprehension. Neural network models — from the parallel distributed processing (PDP) models of Rumelhart and McClelland to modern transformer architectures — serve as both engineering tools and cognitive models, with representational similarity analysis (RSA) bridging the neural and computational levels. The field is increasingly engaged in adjudicating between these frameworks: determining when transformers constitute genuine cognitive models versus engineered approximations, and what empirical evidence can distinguish the accounts.

---

## Theoretical Frameworks

### Predictive Processing / Active Inference

Predictive processing (Clark, Friston) proposes that the brain is fundamentally a hierarchical generative model that continuously generates predictions about sensory input, with perception and action understood as precision-weighted prediction error minimization. Karl Friston's free energy minimization framework unifies perception (updating internal models to minimize prediction error) and action (moving the body to confirm predictions) under a single variational inference objective, extended further in the active inference formulation where agents sample the environment to resolve uncertainty. Applications span perception, attention, motor control, interoception, psychiatric disorders, and consciousness, making predictive processing one of the most ambitious theoretical unifications in contemporary cognitive science.

### Global Workspace Theory

Baars' Global Workspace Theory (GWT) proposes that consciousness corresponds to the broadcasting of information to a globally accessible workspace, making it available to diverse specialized processors; Dehaene and colleagues' Global Neuronal Workspace Theory (GNWT) operationalizes this in neural terms, identifying a frontoparietal ignition signature associated with conscious access. The COGITATE Consortium (2023) conducted a large-scale adversarial collaboration testing GWT predictions against Integrated Information Theory predictions, with results supporting the GNWT's emphasis on prefrontal cortex involvement while raising challenges for some IIT-specific predictions about posterior cortex. GWT has been particularly influential in consciousness science, cognitive neuroscience of attention, and the design of cognitive architectures.

### Integrated Information Theory

Tononi's Integrated Information Theory (IIT, currently version 4.0) proposes that consciousness is identical to integrated information (Φ, phi) — a formal measure of the cause-effect power of a system that cannot be reduced to its parts. IIT derives from five phenomenological axioms (intrinsicality, information, integration, exclusion, composition) and uses these to generate a structural account of consciousness applicable to any physical system. The theory's empirical status remains contested: Φ is computationally intractable for large systems, the COGITATE results raised challenges for some IIT predictions, and critics have raised concerns about the theory's panpsychist implications and its resistance to straightforward empirical falsification.

### Dual-Process Frameworks

The dual-process tradition distinguishes fast, automatic, associative processing (Type 1) from slow, deliberate, rule-governed processing (Type 2), with Stanovich's formalization introducing important refinements including the role of the autonomous mind, the reflective mind, and the algorithmic mind as distinct levels. Default-interventionist models hold that Type 1 processing provides a default output that Type 2 may or may not override, while parallel-competitive models allow both systems to contribute simultaneously, with output determined by the stronger representation. The framework faces ongoing critique regarding the heterogeneity of processes within each type, the measurement of individual differences in Type 2 engagement, and whether "dual process" is a theoretical commitment or an empirical generalization about processing speed and automaticity.

### 4E Cognition

The 4E framework (Embedded, Embodied, Enacted, Extended) groups together several anti-Cartesian positions that challenge the view of cognition as internal symbolic computation occurring in an isolated brain. The extended mind thesis (Clark & Chalmers 1998) argues that cognitive processes can extend beyond the skull into the environment when external resources play the right functional role, while enactivism (Varela, Thompson, Rosch) holds that cognition is constitutively enacted through organism-environment interaction rather than representation of a pre-given world. These views remain controversial relative to classical computationalism, with disputes centering on whether coupling to the environment is sufficient for cognitive extension, and what explanatory work the "embodied" modifier is doing.

---

## Computational Modeling Standards

- **ACT-R** (Anderson): Production rules and declarative memory modules communicate via a central buffer architecture; the Python ACT-R interface (python-actr) and Lisp ACT-R (7.x) both support model specification; model evaluation typically uses RMSE across RT distributions and accuracy by condition, with predictions derived from running simulations rather than closed-form solutions.
- **Bayesian cognitive models**: Priors should be theoretically motivated and reported explicitly; posterior inference via MCMC (Stan, PyMC) or variational methods; model comparison using WAIC, LOO-CV, or Bayes factors with careful attention to their distinct assumptions; marginal likelihood estimation is sensitive to prior specification.
- **Neural network models as cognitive models**: RSA (Representational Similarity Analysis) compares geometry of neural network representations to human neural activity or behavioral dissimilarity matrices; transformer attention patterns have been compared to eye-tracking and reading time data as cognitive-level proxies.
- **Parameter recovery**: Before fitting a model to real data, simulate data from the model at known parameter values, refit, and verify recovery; failure to recover indicates unidentified parameters or insufficient data.
- **Model mimicry tests**: Two models that make equivalent predictions are not empirically distinguishable; G² tests and parameter space partitioning methods determine whether models make genuinely distinct predictions prior to model comparison.
- **Model-based cognitive neuroscience** (Daw et al.): Latent model variables (e.g., prediction errors, uncertainty estimates) serve as regressors in GLM analyses of neural data, linking computational and neural levels of analysis.

---

## Reproducibility & Open Science

- **Preregistration**: OSF (osf.io) and AsPredicted (aspredicted.org) support paradigm preregistration; specify design, exclusion criteria, primary DV, and planned analyses before data collection; distinguish confirmatory and exploratory analyses in reporting.
- **Computational model preregistration**: Register model structure, prior distributions, fitting algorithm, and model comparison criterion before data analysis to prevent HARKing in model selection.
- **Open stimuli and data**: OSF, Pavlovia (pavlovia.org) for PsychoPy experiments, PCIbex Farm for web-based experiments, jsPsych for browser-based paradigms; experiment files and raw data should accompany publications.
- **Registered Reports**: Cognition (Elsevier), Psychological Review, Cognitive Science, and Psychonomic Bulletin & Review offer Registered Report formats providing in-principle acceptance before data collection.
- **Replication initiatives**: ManyBabs, Many Minds Project (comparative cognition), OpenCogSci; coordinate large-N multi-site replications of foundational paradigms.

---

## Modern Methods

- **Signal Detection Theory (SDT)**: d' (sensitivity) and β or c (criterion) decompose hit and false alarm rates into independent sensitivity and bias parameters; ROC curves characterize the full sensitivity-criterion tradeoff; dprime available in Python via mne.stats and psychopy.data.
- **Diffusion models**: EZ-diffusion (Wagenmakers et al.) provides analytic parameter estimates; HDDM (Wiecki et al.) implements hierarchical Bayesian DDM in Python; brms/Stan enable flexible DDM extensions; drift rate indexes evidence accumulation speed, boundary separation indexes speed-accuracy tradeoff, non-decision time indexes perceptual/motor overhead.
- **Time-frequency EEG analysis**: MNE-Python and EEGLAB support ERP and time-frequency decomposition; theta (4–8 Hz) indexes working memory maintenance and cognitive control; alpha (8–12 Hz) indexes attentional suppression; gamma (>30 Hz) indexes local processing and feature binding.
- **Eye-tracking**: Fixation duration, saccade amplitude, and pupillometry (indexing cognitive load and arousal); PyGaze (Python), SR Research DataViewer, R eyetrackingR; useful for reading studies, visual search, and covert attention paradigms.
- **Computational phenotyping**: Fit cognitive model to individual participant's trial-level behavioral data; extract individual-level parameter estimates as phenotypes for individual differences analysis, clinical stratification, or neural correlation.
- **Multilevel Bayesian models**: Partial pooling across participants via random effects; brms (R) and Stan support full posterior inference over random slope structures; avoids shrinkage artifacts of frequentist mixed models.

---

## Agent Workflows

| Agent | Function |
|---|---|
| `cogmod-literature-scout` | Targets Cognition, Psychological Review, Cognitive Science, PsyArXiv, NeurIPS (cognitive track), CogSci proceedings for new empirical and computational work |
| `theory-mapper` | Extracts theoretical commitments from papers; maps to frameworks (PP, GWT, IIT, dual-process, 4E); links concepts to Cognitive Atlas entries |
| `computational-model-extractor` | Identifies model type (Bayesian, connectionist, rule-based, hybrid), parameters, fit criteria, and datasets; outputs structured model record |
| `paradigm-extractor` | Pulls experimental paradigm name, stimuli type, task structure, dependent variable, and exclusion criteria into structured paradigm records |
| `cross-species-comparator` | Flags claims requiring cross-species validity check; links to comparative cognition literature and Many Minds Project datasets |

---

## Key Ontologies & Standards

- **Cognitive Atlas** (cognitiveatlas.org): A community-developed ontology of cognitive concepts, tasks, and their prerequisite and contrast relations; linked to neuroimaging activation data via Neurosynth integration.
- **Behavior Ontology (BehaviorOnto)**: Covers behavioral observations across species, supporting cross-disciplinary and comparative cognition work.
- **Mental Functioning Ontology (MF)**: WHO ICF-aligned ontology of mental functions; useful for clinical cognitive science and neuropsychological research.
- **SNOMED CT cognitive aspects**: Standardized clinical terminology for cognitive symptoms and functions; relevant for cognitive phenotyping and clinical trial integration.

---

## Integration Points

**`paper.schema.json`**: `paradigm` (task name linked to Cognitive Atlas), `sub_domain` (cognitive process mapped to ontology term), `study_type` (`computational` | `empirical` | `theoretical`), `software_versions` (for reproducible model code), `open_code_url` (OSF or GitHub link for model sharing).

**`evidence-table.schema.json`**: `model_fit_criterion` (`BIC` | `WAIC` | `LOO`), `effect_type` (`behavioral` | `neural` | `both`), `population` (age range, expertise level, clinical status).

---

## Recommended Resources

**Journals**: Cognition, Psychological Review, Cognitive Science, Journal of Cognitive Neuroscience, Psychonomic Bulletin & Review, Trends in Cognitive Sciences, Computational Brain & Behavior

**Conferences**: CogSci (Annual Conference of the Cognitive Science Society), Psychonomics Society Annual Meeting, ICCM (International Conference on Cognitive Modeling)

**Preprints**: PsyArXiv (psyarxiv.com), arXiv cs.AI and q-bio.NC

**Databases**: PsycINFO, Semantic Scholar, OpenAlex, ACL Anthology (for language and cognition intersection)

**Tools**: R (`brms`, `lme4`, `BayesFactor`, `diffIRT`, `eyetrackingR`), Python (`PyMC`, `Stan` via pystan, `MNE`, `HDDM`, `jsPsych`, `python-actr`)
