# Applied AI safety research

Study how useful agents preserve a person's authority while remembering, delegating and recovering work. The first proposed study is **authority continuity**: can a resumed or delegated workflow change what a person actually approved?

## Current evidence

[SIS Proving Ground PR #520](https://github.com/frankxai/Starlight-Intelligence-System/pull/520) contains an offline synthetic contract replay: seven paired scenarios, fourteen authored action traces, three mock controls and seventeen passing local checks. No LLM was evaluated. No production enforcement or independent replication is established.

The executable evaluation remains in SIS. This pack owns the domain study and interpretation; it does not fork an enforcement runtime or evaluation framework. Research workflow methods remain in [Research Intelligence OS](https://github.com/frankxai/research-intelligence-os).

## Study contract

[study.json](study.json) records the question, hypothesis, comparators, measurements, current evidence and remaining gates. Its status is PROPOSED_NOT_PREREGISTERED. Existing [preregistration](../../workflows/preregistration.md), [literature review](../../workflows/literature-review.md) and [reproducibility review](../../workflows/reproducibility-review.md) workflows supply the process. A saved plan is not a registered experiment.

Use matched benign and disturbed workflows for memory poisoning, handoff approval claims, revocation, approval substitution, recovery, tenant boundaries and expiry. Give the ordinary scoped baseline real expiry/revocation checks. Freeze the attacker control surface and scorer before a held-out evaluation. Score actual effect state, useful completion, unnecessary interventions and all-attempt cost separately.

A possible later matrix is thirty held-out scenario pairs, three providers, three configurations and three repeats: 1,620 runs. This is an unadmitted planning envelope. Measure usage with a small pilot and resolve budget/terms before dispatch. Repeats do not add independent scenarios; preserve scenario-level uncertainty and negative outcomes.

## Research cycle

1. Identify a concrete user workflow and serious alternative.
2. Inspect prior work; distinguish its established contribution from our proposed extension.
3. Reproduce or characterize the relevant baseline and freeze a falsifiable comparison.
4. Run isolated experiments with versioned source, data, scorer, model and configuration.
5. Analyze failures, utility loss, recovery, costs and limits; retain null results.
6. Seek independent reproduction and review before integrating a product change.
7. Measure the resulting user outcome after release; keep benchmark and customer evidence distinct.

AgentDojo already evaluates tool-agent prompt injections; CaMeL already studies capability enforcement and control/data separation; Inspect supplies evaluation components. The current scope review inspected their documentation and the CaMeL abstract. It does not establish novelty or a full reproduction.

## Contributing

Contribute one sourced comparison, realistic lawful fixture, reproducibility attempt or failure analysis. State what was inspected or executed and what remains unknown. Synthetic data must be labelled. Personal/customer data and credentials do not enter this public pack. Real model access follows each provider's applicable policy; privileged cyber access is not passed through to customer traffic.

The new files in this folder are MIT-licensed; this does not relicense unrelated repository content. No institution or frontier lab is represented as a partner without actual agreement. Integration is pending review.
