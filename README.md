# Research Intelligence Systems

**The portfolio layer for agentic scientific workflows across literature review, evidence synthesis, claim graphs, research design, reproducibility, and open science.**

## Purpose
Provide reusable, high-quality packs, workflows, and schemas for research intelligence that integrate with personal OS and domain systems (psychology, neuroscience). Emphasizes rigor: preregistration, Registered Reports, source-grounded claims, separation of observation/interpretation/hypothesis.

## How People Experience It
Researchers start with a question, use literature-scout agents to build evidence tables, map claims, design studies with reproducibility in mind, then execute via domain packs.

**Typical Flow**:
1. Define question in personal canon (from Agentic Mind OS).
2. Run literature-to-evidence-table workflow.
3. Use claim-graph tools.
4. Preregister (templates provided).
5. Execute in psychology or neuroscience pack.
6. Review reproducibility.

UX is structured yet flexible — Markdown + JSON for humans and agents.

## How Agents Explore It
- researchpack.yaml manifest
- packs/ (neuroscience, psychology, learning-science, cognitive-science, behavioral-science, consciousness-studies)
- workflows/ (literature-review.md, evidence-table.md, claim-graph.md, reproducibility-review.md, preregistration.md)
- schemas/ (paper.schema.json, claim.schema.json, evidence-table.schema.json)
- Integrates with Research Intelligence OS runtime and human-mind models.

**Example Prompt**:
"As literature-scout + methods-critic, using human-mind models for belief and decision-making, synthesize recent papers on [topic]. Build evidence-table.schema.json. Flag reproducibility risks per latest best practices. Reference preregistration.md."

## Usefulness
- **Humans**: Accelerates rigorous research while reducing common pitfalls. Supports open science and career advancement via prereg/Registered Reports.
- **Agents**: Clear contracts and schemas enable reliable multi-step research agents.
- **Integrations**: Personal canon → research packs → domain execution (psych/neuro) → back to canon.
- **Latest Best Tech**: BIDS 1.10, NWB 2.7, MNE-Python 1.8+, preregistration/Registered Reports, ReAct agents with structured outputs, modern psychometrics (pingouin), reproducibility tooling.

See researchpack.yaml, EXPERIENCE.md, AGENTS.md, workflows/, schemas/, and packs/.

This is the connective tissue of the research swarm.