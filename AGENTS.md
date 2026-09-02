# Research Intelligence Systems — Agent Instructions

## Repository role

This repository is the domain-pack layer for scientific and reproducible research workflows, including neuroscience, psychology, learning science, cognitive science, behavioral science, and consciousness studies.

## Ownership boundary

- Owns: domain packs, agents, skills, evidence schemas, claim graphs, and reproducibility workflows.
- Consumes by reference: literature, datasets, historical documents, and other governed source corpora.
- Does not own: the FrankX historical sacred-text corpus, Sacred Visions, source editions or translations governed elsewhere, or fictional Arcanea canon.
- The `consciousness-studies` name describes a research domain; it is not authority for a sacred-text archive.

## Required preflight

Before adding a corpus, collection, product surface, or new repository boundary, load reviewed `frankxai/agentic-ops/registry/manifest.yaml`, record its commit SHA, check `exclusions.yaml`, and resolve `repositories.yaml` plus `artifact_authorities.yaml`. If no authority exists, stop at a proposal.

This boundary was clarified against Registry commit `81765d65fde9ed8692787425cfd1381a4f6dc40a`; always use the latest reviewed Registry commit.

## Work pattern

1. Read `README.md`, `researchpack.yaml`, and the relevant pack contracts before editing.
2. Keep research claims evidence-bound and preserve provenance and reproducibility metadata.
3. Never fabricate citations, datasets, standards compliance, or source content.
4. Validate the smallest affected schema, pack, or workflow before handoff.
