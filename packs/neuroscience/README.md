# Neuroscience Research Intelligence Pack

## Overview

This pack provides structured, reproducible, agent-assisted neuroscience research intelligence for automated literature review, evidence synthesis, and methodology standardization. It covers the full breadth of modern neuroscience — from cellular signaling cascades to systems-level oscillatory dynamics, from cognitive neuroimaging paradigms to computational models of neural coding — with an emphasis on open science practices and FAIR data principles that make findings replicable and machine-readable.

Designed for AI agents and researchers building automated literature review and evidence synthesis systems, this pack defines the schemas, vocabularies, agent workflows, and quality gates needed to ingest raw publications and transform them into structured, queryable evidence tables. Every component is aligned with community data standards (BIDS, NWB), reporting checklists (COBIDAS), and ontologies (Cognitive Atlas, NIFSTD) so that outputs from one agent can feed cleanly into the next stage of a synthesis pipeline.

---

## Domain Scope

### Cognitive Neuroscience
Cognitive neuroscience investigates the neural substrates of mental processes — perception, attention, memory, language, and executive function — using convergent methods including fMRI, EEG, MEG, and behavioral measures. Studies typically link brain activity (BOLD signal, oscillatory power, ERPs) to task performance or individual differences. Key methodological pillars are experimental design (event-related vs. block), multivariate decoding of representations, and careful control of confounds such as head motion and vascular reactivity.

### Computational Neuroscience
Computational neuroscience builds mathematical and algorithmic models of neural systems, from single-neuron integrate-and-fire models to large-scale Bayesian brain frameworks and deep learning analogues. It encompasses neural coding theory (rate codes, population vectors, spike timing), dynamical systems analysis of circuit attractors, and normative accounts of perception and learning. Tools include Brian2, NEST, and NEURON for spiking networks, and Stan or PyMC for Bayesian inference.

### Systems Neuroscience
Systems neuroscience examines how circuits and inter-area networks collectively generate behavior, focusing on oscillations, long-range connectivity, and synaptic plasticity. Techniques include multi-electrode array recordings, calcium imaging, and optogenetic perturbations that allow causal testing of circuit hypotheses. Key phenomena include theta-gamma coupling in memory, predictive coding loops between cortical hierarchies, and dopaminergic reinforcement signals.

### Cellular & Molecular Neuroscience
This sub-discipline characterizes the properties of neurons and glia at the level of ion channels, synaptic transmission, receptor signaling, and gene expression. Optogenetics (ChR2, halorhodopsin) and chemogenetics (DREADDs) allow precise manipulation of defined cell populations in vivo. Patch-clamp electrophysiology, single-cell RNA sequencing, and expansion microscopy have transformed our understanding of neuronal diversity and synaptic organization.

### Clinical & Translational Neuroscience
Translational neuroscience bridges bench and bedside by identifying biomarkers for neurological and psychiatric disorders — Alzheimer's disease, Parkinson's, schizophrenia, depression — and testing mechanistic interventions. CSF and plasma biomarkers (amyloid-β, tau, neurofilament light chain), neuroimaging endophenotypes, and polygenic risk scores are all active areas. The field increasingly depends on large-scale consortia (ADNI, ABCD, UK Biobank) for statistical power.

### Neuroimaging
Neuroimaging encompasses structural MRI (cortical thickness, volumetry), diffusion MRI tractography (probabilistic and deterministic), resting-state and task-based functional connectivity, and quantitative MRI (T1/T2 mapping, MRS). Preprocessing pipelines must handle slice-timing correction, motion realignment, spatial normalization, and smoothing consistently. Parcellation atlases (AAL, Schaefer-400, HCP-MMP) define the nodes in functional and structural connectomes.

---

## Data Standards & Infrastructure

### BIDS (Brain Imaging Data Structure)
BIDS is the community standard for organizing neuroimaging and electrophysiology data into a human- and machine-readable directory hierarchy. A compliant dataset separates raw data by subject (`sub-<label>/`), session (`ses-<label>/`), and modality subfolder (`func/`, `anat/`, `dwi/`, `eeg/`, `meg/`). Each data file is paired with a sidecar JSON containing acquisition parameters (TR, TE, slice order, electrode impedances) and a TSV events file for task designs. The `bids-validator` CLI (`npx bids-validator /path/to/dataset`) or Python package checks compliance before submission to OpenNeuro or any shared repository, making BIDS the reproducibility contract between data producers and downstream analysis tools.

```
my-dataset/
├── dataset_description.json
├── participants.tsv
├── participants.json
├── sub-01/
│   ├── ses-01/
│   │   ├── anat/
│   │   │   ├── sub-01_ses-01_T1w.nii.gz
│   │   │   └── sub-01_ses-01_T1w.json
│   │   ├── func/
│   │   │   ├── sub-01_ses-01_task-rest_bold.nii.gz
│   │   │   ├── sub-01_ses-01_task-rest_bold.json
│   │   │   └── sub-01_ses-01_task-rest_events.tsv
│   │   └── dwi/
│   │       ├── sub-01_ses-01_dwi.nii.gz
│   │       ├── sub-01_ses-01_dwi.bval
│   │       └── sub-01_ses-01_dwi.bvec
│   └── ses-02/
│       └── eeg/
│           ├── sub-01_ses-02_task-n200_eeg.edf
│           └── sub-01_ses-02_task-n200_eeg.json
└── derivatives/
    └── fmriprep/
        └── sub-01/
```

### NWB (Neurodata Without Borders)
NWB 2.x stores electrophysiology, calcium imaging, and behavioral data in HDF5 files with a standardized typed schema. The PyNWB and MatNWB APIs provide read/write access; `nwbinspector` checks files for spec compliance and best practices. The DANDI Archive (dandiarchive.org) is the primary public repository for NWB datasets, with versioned DOI minting for citable data publication. NWB's typed data model ensures that downstream analysis tools can discover recording metadata — electrode locations, spike sorting provenance, stimulus parameters — without custom parsers, enabling true pipeline reuse across labs.

### MEG-BIDS and EEG-BIDS Extensions
The MEG-BIDS and EEG-BIDS extensions add channel type definitions, coordinate system files (`*_coordsystem.json`), and electrode location files (`*_electrodes.tsv`) to the core spec. OpenNeuro (openneuro.org) accepts both MRI-BIDS and EEG/MEG-BIDS datasets and provides free public hosting with FAIR compliance, persistent DOIs, and direct integration with analysis platforms.

### DataLad
DataLad provides Git-annex-backed versioned dataset management for large neuroimaging datasets. Use `datalad clone <url>` to register a remote dataset locally and `datalad get <path>` to fetch only the files needed for a given analysis step. Every analysis step is a DataLad run record linking inputs, outputs, and the exact command executed, enabling full provenance tracking and automated re-execution.

### BIDS Apps
BIDS Apps are containerized (Docker/Singularity) analysis pipelines that accept any valid BIDS dataset as input and produce BIDS Derivatives. Key apps include **fMRIPrep** (robust fMRI preprocessing with visual QC reports), **MRIQC** (image quality metrics without analysis), and **qsiprep** (diffusion MRI preprocessing and reconstruction). Because all parameters are encoded in the container image and dataset sidecar JSONs, running a BIDS App requires no environment configuration and produces fully reproducible outputs across sites and operating systems.

---

## Reproducibility & Open Science

- **Preregistration** on OSF (osf.io) and AsPredicted should occur before data collection in confirmatory neuroimaging studies. A complete preregistration specifies hypotheses, regions of interest (ROIs) with anatomical justification, correction methods (FWE vs. FDR), planned sample size with power justification, exclusion criteria (motion thresholds, task performance cutoffs), and the planned statistical model including covariates.
- **Registered Reports** at eLife, Nature Neuroscience, NeuroImage, and Cortex provide In-Principle Acceptance (IPA) at Stage 1 based on the introduction and methods alone, before data are collected. This eliminates publication bias and HARKing (Hypothesizing After Results are Known). Agents should flag papers with IPA badges as methodologically higher quality in evidence tables.
- **COBIDAS checklist** (cobidas.github.io) specifies minimum reporting requirements for MRI, fMRI, and EEG/MEG publications — scanner parameters, preprocessing steps, statistical thresholds, software versions, and coordinate space. The `reproducibility-assessor` agent uses COBIDAS items as a structured rubric when scoring paper quality.
- **Code sharing**: fMRIPrep and derivative pipelines should be containerized with pinned software versions and shared via Zenodo or GitHub releases alongside the paper. BIDS App version numbers serve as a reproducibility fingerprint.
- **fMRIPrep, FreeSurfer, FSL, SPM** are the canonical shareable analysis pipelines. Studies using these tools with documented version numbers are assigned higher reproducibility scores than those using in-house scripts.
- **Effect sizes and power analysis**: neuroimaging studies routinely report Cohen's d or partial η² alongside p-values. G\*Power and the `pwr` R package compute sample sizes for conventional thresholds (α = 0.05, power = 0.80), though neuroimaging effect sizes are often smaller than assumed, requiring n > 25–30 per group for robust detection.

---

## Modern Statistics & Analysis Methods

- **Bayesian approaches**: Stan, brms (R), and JASP enable prior specification, posterior predictive checks, and Bayes factor computation. Bayesian mixed models are increasingly preferred over frequentist GLMs because they propagate uncertainty and handle small samples with partial pooling, avoiding the binary pass/fail logic of NHST.
- **Mixed-effects models**: `lme4`/`nlme` (R) and `fitlme` (MATLAB) account for within-subject repeated measures, random slopes, and nested structures common in neuroimaging (trials within sessions within subjects). Fixed-effects-only models that ignore random structure produce anti-conservative p-values.
- **MVPA and RSA**: Multivariate pattern analysis uses linear (SVM, LDA) or cross-validated classifiers to decode stimulus or task information from distributed activation patterns. Representational similarity analysis (RSA) compares neural geometry to model-predicted dissimilarity matrices without assuming a linear mapping between neural and behavioral spaces.
- **Cluster correction**: Family-wise error (FWE) correction via random field theory (RFT) or permutation controls the probability of any false positive cluster. FDR (Benjamini-Hochberg) controls the expected fraction of false discoveries across voxels. TFCE (threshold-free cluster enhancement) in FSL `randomise` integrates cluster extent and peak height without an arbitrary cluster-forming threshold, and is regarded as the most sensitive and assumption-free method.
- **Cross-validation**: To avoid double-dipping (using the same data for feature selection and classification), all model selection steps must be nested within cross-validation folds. Scikit-learn's `Pipeline` with `cross_val_score` enforces this automatically.
- **Non-parametric permutation tests**: FSL `randomise` and SnPM generate empirical null distributions by permuting condition labels, avoiding assumptions about the Gaussian distribution of test statistics. These are regarded as the gold standard for second-level neuroimaging inference when sample sizes permit.

---

## Agent Workflows

| Agent | Function |
|---|---|
| `literature-scout` | Queries PubMed, bioRxiv, and Semantic Scholar; extracts BIDS dataset and OpenNeuro accession links from full text |
| `neuro-claim-extractor` | Pulls empirical claims, effect sizes, sample N, paradigm, and imaging modality from abstracts and methods sections |
| `reproducibility-assessor` | Checks for preregistration link, open data/code URLs, COBIDAS checklist compliance, and registered report status |
| `evidence-synthesizer` | Meta-analytic pooling of neuroimaging effect sizes using random-effects models; quantifies heterogeneity (I²) |
| `methods-standardizer` | Normalizes methods descriptions to ontology terms from Cognitive Atlas and Neurolex |
| `bids-validator-agent` | Clones datasets from OpenNeuro/DANDI and runs `bids-validator`; reports errors and warnings with remediation suggestions |

---

## Key Ontologies & Vocabularies

- **Cognitive Atlas** (cognitiveatlas.org): Formally defines cognitive concepts (e.g., working memory, response inhibition), experimental tasks, and their theoretical relationships. Used to standardize paradigm descriptions across labs and enable cross-study meta-analysis without manual harmonization.
- **Neurolex** (neurolex.org): Covers brain regions, cell types, subcellular compartments, and experimental conditions. Being superseded by NIFSTD but remains widely cited in pre-2023 literature.
- **NIF Standard Ontology (NIFSTD)**: Comprehensive neuroscience ontology integrating anatomical, cell type, and resource terms; maintained by the Neuroscience Information Framework. The authoritative vocabulary for structured claims about brain structure and function.
- **OpenMINDS**: The EBRAINS metadata framework defines linked-data schemas for neuroscience data, models, and software, enabling cross-dataset queries on the EBRAINS research infrastructure.
- **Standard spaces and atlases**: MNI152 (volumetric) and fsaverage (surface) are the canonical template spaces. Common parcellations include AAL (116 regions), Schaefer-400 (400 cortical parcels, 7/17 networks), Brodmann areas, and the HCP Multi-Modal Parcellation (MMP 1.0).

---

## Integration Points

**With `paper.schema.json`**: Relevant fields for neuroscience papers include `paradigm` (maps to Cognitive Atlas task ID), `imaging_modality` (array: `["fMRI", "EEG"]`), `preprocessing_pipeline` (e.g., `"fMRIPrep 23.1.3"`), `software_versions` (object), `data_standard` (enum: `"BIDS"` / `"NWB"` / `"other"`), `preregistered` (boolean), `preregistration_url`, `open_data_url` (OpenNeuro accession or DANDI dandiset), and `open_code_url`.

**With `evidence-table.schema.json`**: Neuroscience-specific columns include `N` (sample size), `ROI` (anatomical label or MNI coordinate), `imaging_modality`, `correction_method` (FWE / FDR / TFCE / uncorrected), `effect_size_type` (Cohen's d / partial η² / AUC / Pearson r), `effect_size_value`, `coordinate_space` (MNI152 / Talairach / fsaverage), and `cluster_extent_voxels`.

**Parent systems**: This pack is consumed by the `neuroscience-research-intelligence-system` repo and participates in the `mind-intelligence-swarm` ecosystem, where agent outputs from multiple domain packs are cross-linked for interdisciplinary synthesis (e.g., linking neuroeconomics findings from this pack with behavioral economics evidence from the psychology pack).

---

## Recommended Resources

**Journals**: Nature Neuroscience, Neuron, eLife (Neuroscience), NeuroImage, Human Brain Mapping, Cerebral Cortex, Journal of Neuroscience, PLOS Computational Biology, Cortex

**Preprint servers**: bioRxiv (category: Neuroscience / q-bio.NC), medRxiv (clinical and translational neuroscience)

**Databases**: PubMed / PubMed Central, Semantic Scholar, OpenAlex, Europe PMC

**Data repositories**:
- OpenNeuro (openneuro.org) — BIDS-validated MRI, fMRI, EEG, MEG datasets with free hosting
- DANDI Archive (dandiarchive.org) — NWB electrophysiology and calcium imaging, DOI minting
- INDI / fcon_1000 (fcon_1000.projects.nitrc.org) — resting-state fMRI consortia
- UK Biobank (ukbiobank.ac.uk) — neuroimaging at scale (n > 40,000)
- Allen Brain Atlas (brain-map.org) — gene expression and structural connectivity

**Analysis tools**:
- **Preprocessing**: fMRIPrep, FreeSurfer, FSL, SPM12, AFNI, qsiprep
- **EEG/MEG**: MNE-Python, EEGLAB, Fieldtrip
- **Statistics**: R (lme4, brms, ggplot2), Python (nilearn, pingouin, statsmodels), JASP
- **Simulation**: Brian2, NEST, NEURON, PyMC
- **Visualization**: Nilearn, Connectome Workbench, BrainPainter, MRIcroGL
