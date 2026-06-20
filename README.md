# Research Intelligence Systems

**The portfolio layer for agentic scientific workflows across literature review, evidence synthesis, claim graphs, research design, reproducibility, and open science.**

Research Intelligence Systems provides reusable packs, agents, skills, and workflows that turn raw literature and data into structured, reproducible knowledge — grounded in the human mind model and interoperable with personal second brains.

## How It Works (Deep Architecture)

The system is organized into domain packs that map directly to cognitive modules:

- **packs/neuroscience/** — BIDS/NWB/MNE pipelines, dataset scouting, reproducibility (wired to Learning + Behavior).
- **packs/psychology/** — Construct mapping, psychometrics, qualitative analysis (Emotion + Belief).
- **packs/learning-science/**, **cognitive-science/**, **behavioral-science/**, **consciousness-studies/** — Cross-cutting evidence synthesis.

**Core Workflows**:
1. Literature ingestion → structured paper.schema.json.
2. Evidence table generation → claim.schema.json.
3. Claim graph construction → reproducibility review.
4. Agent-assisted design of experiments with preregistration templates.

**Agent Interaction Example**:
"Using the Learning and Metacognition modules, scout recent papers on [topic] with public OpenNeuro data. Build a claim graph using latest BIDS 1.10 / NWB 2.7 standards. Output evidence table and flag reproducibility gaps."

All outputs follow strict schemas and evaluation contracts from Research Intelligence OS.

## Competitor Comparison

| Aspect                    | Research Intelligence Systems                  | Elicit                          | Scite                           | Semantic Scholar + AI          | Zotero + AI plugins            |
|---------------------------|------------------------------------------------|---------------------------------|---------------------------------|--------------------------------|--------------------------------|
| **Structured Outputs**   | JSON schemas + claim graphs + evidence tables | Summaries + tables             | Smart citations                | Basic AI summaries             | Manual                         |
| **Reproducibility**      | Native prereg, BIDS/NWB, evaluation contracts | Limited                        | Limited                        | None                           | None                           |
| **Human Mind Grounding** | Explicit mapping to 12 cognitive modules      | None                           | None                           | None                           | None                           |
| **Agent/Skill Packs**    | First-class modular agents + SKILL.md         | No standard                    | No standard                    | No standard                    | Community plugins              |
| **Community & Packs**    | Shared research packs, cohorts, contribution  | Closed ecosystem               | Closed                         | Open but generic               | Strong but fragmented          |
| **Personal + Research Bridge** | Native integration with Agentic Mind OS    | None                           | None                           | None                           | Manual                         |

Research Intelligence Systems excels in structured, reproducible, cognitively-grounded research infrastructure.

## Research Agent Packs, Skill Packs & Community Workflows

**Agent Packs**:
- `agents/literature-scout.agent.md`
- `agents/claim-graph-builder.agent.md`
- `agents/reproducibility-engineer.agent.md`
- Domain-specific (neuro-literature-scout, construct-mapper, etc.)

**Skill Packs**:
- `skills/paper-ingestion/SKILL.md`
- `skills/evidence-table-builder/SKILL.md`
- `skills/systematic-review-matrix/SKILL.md`
- `skills/bids-validator/SKILL.md`
- `skills/mne-eeg-pipeline/SKILL.md`

**Community Research Workflows**:
- `workflows/literature-review.md`
- `workflows/evidence-table.md`
- `workflows/claim-graph.md`
- `workflows/reproducibility-review.md`

**Community**:
- Anyone can contribute new packs or skills via PRs.
- Shared packs enable cohort-based research (Starlight Pro).
- Integration with Awesome Mind Agent Skills for discovery.
- Use in personal canon building via Agentic Mind OS.

## Schemas & Extensibility

- `schemas/paper.schema.json`
- `schemas/claim.schema.json`
- `schemas/evidence-table.schema.json`
- `researchpack.yaml`

Fully extensible for any research domain.

## Usefulness for Community & Research

- **Researchers**: Accelerates rigorous, reproducible work with built-in standards.
- **Community**: Shared packs create collective intelligence. Contribute, fork, or join cohorts.
- **Bridge to Personal**: Research outputs feed directly into personal canon and learning.

See `researchpack.yaml`, `AGENTS.md`, `HERMES.md`, and the world-class interactive experience.

**Launch the Experience**: https://github.com/frankxai/mind-intelligence-systems/blob/main/experiences/world-class-brain-experience.html

All repos on main with this depth.