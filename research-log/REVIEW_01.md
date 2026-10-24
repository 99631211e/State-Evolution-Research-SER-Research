# SER Publication Review 01 — Scientific and reproducibility audit

Date: 2026-10-22. Scope: `WORKING_PAPER_DRAFT.md` v0.1 and archived H4-008 through H4-018 computational artifacts. This is an internal critical review, **not** independent peer review.

## Executive decision

**Major revision required before public working-paper deposit.** The project has a coherent methodological motivation, and available H4 scripts reproduce byte-identical CSV outputs. The central proposed contribution—CAP v0.1 as an operational protocol—has **not yet demonstrated incremental utility** relative to established physical-computation frameworks or ordinary reproducibility/reporting practice.

## Reproducibility audit

Eight archived scripts (H4-008, 009, 010, 011, 012, 013, 014, and combined H4-015–018) were extracted and executed with `python experiment.py` in their respective directories. All exited with code 0 and regenerated `results.csv` with the same SHA-256 as the archived CSV. Details in `REPRODUCTION_RESULTS.json`. This verifies deterministic re-execution, not mathematical correctness or independence: the original code and its own checks were reused. Original H1–H3 and H4-001–007 code were not in the inspected archives.

## Major issues (blocking)

1. **No empirical protocol-comparison baseline.** CAP-1–9 are sensible reporting checks but are not shown to catch errors missed by existing methods. Construct a comparative evaluation: (i) naive functional matching, (ii) a clearly operationalized prior framework, (iii) CAP, evaluated against pre-labelled valid/invalid attribution claims. Report false positives, false negatives, reviewer effort, and disagreements.
2. **Literature novelty remains unresolved.** Horsman et al. (2014) and Piccinini (2015) already discuss representation, implementation and restrictions on mapping. Cite them accurately; investigate mechanistic, causal, counterfactual, implementation and physical-computing benchmarking work more thoroughly. Do not claim the attribution problem or its ingredients as discoveries.
3. **No actual physical-substrate validation.** H4-018 is XOR implementations and a linear threshold control, not reservoir or physical cross-platform validation. Retitle as 'Minimal architecture control'. A future experiment should compare a fixed-interface dynamical reservoir with an interface-only null control under matched budgets.
4. **Cost model lacks dimensional validity.** H4-011 adds gate count, memory bits and depth under stipulated weights. This is a scenario score, not measured cost; include Pareto comparisons and sensitivity analyses, and avoid direct hardware/energy interpretations.
5. **Task/interface ambiguity.** Define whether E and U are independent maps or whether U acts on encoded states; specify fixed-vs-task-specific decoder, permitted adaptation, physical intervention set, measurement disturbance and system boundary. Separate computational success from causal attribution and efficiency.
6. **Incomplete archival provenance.** Missing inspectable original code for H1–H3 and H4-001–007 in the audited package; those should not be used as independently reproduced numerical evidence.

## Specific quantitative checks / clarifications

- H4-015: With `fixed=45Q`, `adaptive=500+20S+12Q`, adaptive wins iff `33Q>500+20S`; for S=0, minimum integer Q is 16. Search and switch costs are stipulated, not observations. Number of ROBDD nodes is a proxy, not an execution-time measure.
- H4-016: Changing the bookkeeping boundary in a fixed XOR→NOT circuit preserves 4/4 truth-table correctness; it does not demonstrate the equivalence of arbitrary physical substrates or physical boundary invariance.
- H4-017: Independent input-bit flips compare XOR5 and Majority5 as **functions**, not noisy physical implementations; Majority disagreement depends on the input distribution. Include a noise-location taxonomy.
- H4-018: A two-input XOR is not linearly separable, but becomes separable after a nonlinear feature is added; count that feature computation as interface work. The finite-state transition has XOR built in and is not emergent computation.
- H4-012–014: ANF monomials, SOP minterms, ROBDD nodes and logic gates are distinct units. Variable order is a representational/configurational parameter, not necessarily a physical wiring cost.

## Suggested contribution statement

'We propose and illustrate a versioned, operational reporting and stress-test checklist for computational attribution claims. Its present validation consists of exact finite examples; incremental diagnostic value and applicability to physical devices remain open empirical questions.'

## Recommended manuscript architecture

1. Problem and intended scope (no universal law claim).
2. Prior art and explicit novelty matrix.
3. Typed system model with boundary and resource ledger.
4. CAP v0.2 protocol with preregistered pass/fail criteria.
5. Benchmark: pre-labelled attribution claims, baselines, false-positive controls.
6. Results grouped by methodological failure mode, not experiment chronology.
7. Limitations, negative results, reproducibility and AI-use disclosure.
8. Future physical-substrate validation.

## Decision gates

- [x] Eight archived H4 scripts execute and reproduce CSV byte-for-byte.
- [ ] Independently derive/check each numerical result with distinct implementations.
- [ ] Retrieve and audit H1–H3, H4-001–007 original artifacts or remove quantitative claims.
- [ ] Perform literature and novelty matrix with accurate bibliographic verification.
- [ ] Define CAP scoring, failure criteria, and compare with an established baseline.
- [ ] Test a genuine dynamical / physical system, or explicitly limit paper to methodology with toy examples.
- [ ] Add raw outputs, environment, licenses, full version history and human sign-off.

## Sources verified during review

- Horsman, C. et al. (2014), *When does a physical system compute?* https://doi.org/10.1098/rspa.2014.0182
- Piccinini, G. (2015), *Physical Computation: A Mechanistic Account*. https://doi.org/10.1093/acprof:oso/9780199658855.001.0001

The present literature check is selective, **not** systematic or exhaustive.
