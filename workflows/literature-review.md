# Literature Review Workflow

## Purpose

Systematic, agent-assisted literature discovery and evidence synthesis for any domain pack (neuroscience, psychology, cognitive-science, learning-science, behavioral-science, consciousness-studies). Produces a structured evidence table and claim graph ready for downstream synthesis in research-intelligence-os pipelines.

## Inputs

| Field | Format | Required | Notes |
|---|---|---|---|
| `research_question` | PICO/PECO string | Yes | Population, Intervention/Exposure, Comparison, Outcome |
| `domain_pack` | enum | Yes | One of the six domain packs |
| `date_range` | `from`/`to` ISO dates | No | Defaults to last 10 years |
| `study_types` | array | No | Filter: empirical, RCT, meta-analysis, etc. |
| `seed_dois` | array of DOIs | No | Anchor papers to expand from |
| `language` | string | No | Default: English |

## Step 1: Research Question Structuring

Formalize the research question using PICO or PECO format:
- **P** (Population): who is studied (e.g., healthy adults 18–35, MDD patients)
- **I/E** (Intervention/Exposure): what is manipulated or measured
- **C** (Comparison): control condition or comparator group
- **O** (Outcome): what is measured (primary DV)

Extract key constructs and map to the domain ontology:
- Neuroscience: Cognitive Atlas, Neurolex
- Psychology: Cognitive Atlas, APA Dictionary, RDoC domains
- Learning science: Bloom's Taxonomy verbs, BCT taxonomy (if intervention)
- Behavioral science: BCTTv1 cluster, COM-B component
- Consciousness studies: theory tags (IIT/GNWT/RPT/HOT/PP)

## Step 2: Multi-Database Search

Run parallel queries across domain-specific databases:

**By domain:**
- Neuroscience / Psychology / Cognitive science: PubMed, PsycINFO, Semantic Scholar, OpenAlex
- Learning science: ERIC, PsycINFO, Google Scholar, SSRN
- Behavioral science: PsycINFO, EconLit, Cochrane, Campbell Collaboration, Google Scholar
- Consciousness studies: PubMed, PhilPapers, Semantic Scholar

**Query construction:**
- Boolean operators (AND, OR, NOT)
- MeSH terms for PubMed/PsycINFO controlled vocabulary
- Title/abstract field restrictions for precision
- Proximity operators for phrase matching (NEAR/3)

**Grey literature:**
- OSF, SSRN, bioRxiv, PsyArXiv, medRxiv, arXiv (q-bio.NC, cs.AI), EdArXiv
- ClinicalTrials.gov and AEA RCT Registry for registered trials

**Citation chaining:**
- Backward: references of included papers
- Forward: papers citing included papers (Semantic Scholar, Google Scholar)

**Deduplication:** Remove duplicates by DOI, then title+year+first-author.

## Step 3: Screening (PRISMA)

**Stage 1 — Title and abstract screening:**
- Apply inclusion/exclusion criteria
- Dual review recommended; resolve disagreements by discussion or third reviewer
- Record exclusion reason for each excluded record

**Stage 2 — Full-text screening:**
- Retrieve full text via Unpaywall, PubMed Central, Semantic Scholar open PDF
- Apply detailed inclusion/exclusion criteria
- Record PRISMA counts at each stage

**Output:** PRISMA flow diagram (total identified → duplicates removed → screened → full-text assessed → included).

## Step 4: Data Extraction → paper.schema.json

Automated extraction per included paper:
- Identifiers: DOI, PMID, arXiv ID, semantic_scholar_id
- Authorship, year, journal
- Study type, design, paradigm, species
- Sample size and description
- Imaging modality, preprocessing pipeline, software versions
- Primary statistic, effect size, CI, p-value, Bayes factor
- Open science fields: preregistered, open_data, open_code, data_standard

Flag papers where automated extraction confidence is below threshold for human review.

## Step 5: Evidence Quality Assessment

Apply the appropriate risk-of-bias tool:

| Study Design | Tool |
|---|---|
| RCT | Cochrane RoB 2.0 |
| Observational (cohort, case-control) | ROBINS-I |
| Cross-sectional, case-control | Newcastle-Ottawa Scale |
| Diagnostic accuracy | QUADAS-2 |
| Systematic reviews being synthesized | AMSTAR-2 |

Record overall judgment: **low / some concerns / high / not assessed**.

## Step 6: Evidence Table Construction

Populate `evidence-table.schema.json`:
- One entry per included study
- Compute pooled statistics if quantitative synthesis is feasible
- Check I² threshold: I² > 50% triggers heterogeneity flag; narrative synthesis preferred over pooling
- Run publication bias tests: Egger's test, funnel plot asymmetry, PET-PEESE if ≥ 10 studies

## Step 7: Claim Graph Construction

For each included paper, extract top-level empirical claims into `claim.schema.json`:
- Assign `consensus_level` based on `replication_count` and `replication_success_rate`
- Map `supports_claims`, `contradicts_claims`, `refines_claims` edges
- Tag moderators and boundary conditions from included papers

## Step 8: Synthesis Output

Produce:
1. **Evidence table** (`evidence-table.schema.json` populated)
2. **Claim graph** (array of `claim.schema.json` with relationship edges)
3. **PRISMA flow diagram** (Mermaid format)
4. **Synthesis narrative** (structured markdown: background, methods, results by outcome, discussion)
5. **GRADE evidence profile** (one row per outcome)
6. **Open science compliance summary** (% preregistered, % open data, % BIDS/NWB)

## Agent Support

| Agent | Role |
|---|---|
| `literature-scout` | Multi-database query + dedup |
| `effect-size-extractor` | Statistical extraction from tables and text |
| `bias-assessor` | RoB2/ROBINS-I/Newcastle-Ottawa scoring |
| `evidence-synthesizer` | Meta-analytic pooling, I², publication bias |
| `claim-mapper` | Claim extraction + relationship graph |
| `prisma-generator` | PRISMA flow diagram from screening counts |

## Tool Integration

```
Semantic Scholar API (api.semanticscholar.org)
PubMed E-utilities (eutils.ncbi.nlm.nih.gov)
OpenAlex API (api.openalex.org)
Unpaywall API (unpaywall.org/api) — open access full text
R: metafor, robumeta, meta, ggplot2
Python: pymetaanalysis, habanero (DOI), requests
```
