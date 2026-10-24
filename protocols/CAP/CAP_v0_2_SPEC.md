# CAP v0.2 — provisional specification

For every computation-attribution claim, record:
1. Task definition and evaluation distribution.
2. Physical/logical system graph, explicit attribution boundary.
3. Encoder, decoder, program, controller, measurement, and their configuration freedom.
4. Evidence: preregistered, held-out, counterfactual; applicability limits.
5. Resources as vector (memory, logic, latency, energy, configuration/search) with missing fields identified.
6. Representation and boundary sensitivity analysis.
7. Perturbation location, channel, distribution, error metric.
8. Matched controls, including interface-only and constrained-core baselines.
9. Provenance: code, data, environment, seeds, version, negative results.

Each field receives `provided`, `absent`, or `not_applicable`, plus evidence status `direct`, `simulated`, `stipulated`, or `conceptual`. Flag diagnostic concerns; do not calculate a universal computation score or claim that compliance proves physical computation.

## Evaluation plan
Freeze specification and benchmark protocol before independent case collection. Sample actual published claims, anonymize origin when possible, ask at least two evaluators to classify cases with CAP and a literature-grounded comparator, adjudicate reference labels separately, report disagreement, accuracy by failure mode, false positives, time burden, and sensitivity to ambiguous cases. Preregister primary outcomes.
