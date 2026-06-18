# Research Experience in the Portfolio

## Purpose
Portfolio layer for agentic scientific workflows: literature review, evidence synthesis, claim graphs, reproducibility.

## How Researchers Experience It

1. Start in a domain pack (psychology or neuroscience).
2. Use workflows/literature-review.md to pull sources.
3. Build evidence-table.
4. Agents (via research-intelligence-os templates) generate claim-graph.
5. Reproducibility-review before publishing.

Daily/Weekly: Ingest papers → distill → evidence table → claim update.

## Agent Exploration

Agents follow researchpack.yaml.
Use schemas/paper.schema.json for structured ingestion.
Reference runtime contracts from research-intelligence-os.
Cross-link to human-mind models for psychology/neuroscience alignment.

Example: "Using psychology pack, build claim graph for belief-updating literature. Output in claim.schema.json."

## Usefulness

- Reduces time from lit review to synthesized table from days to hours.
- Reproducible by construction.
- Shared across personal OS and domain systems.
- Open science friendly (BIDS/NWB ready in neuro pack).
