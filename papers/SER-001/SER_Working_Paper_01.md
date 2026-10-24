# Computational Attribution in Physical Systems: Interface Dependence, Resource Accounting, and an Auditable Research Checklist

**SER Working Paper 01 — Public Research Milestone v1.0-rc1 | 24 October 2026**  
**Author:** Dastan Arakeev Mederbekovich  
**Affiliation:** Independent Researcher, Kyrgyzstan  
**Research program:** State Evolution Research (SER)  
**Status:** Public research milestone / preliminary working paper; not peer reviewed; not independently validated.  
**Publication:** Prepared for GitHub and Zenodo; not deposited; no repository URL or DOI assigned.

## Abstract

Attributing computational capabilities to a physical subsystem requires specifying how tasks, encoders, controllers, decoders, and measurement apparatus contribute to the observed input–output relation. We synthesize a series of reproducible finite-model and Boolean-function demonstrations illustrating failure modes in post-hoc interpretation, interface outsourcing, system-boundary selection, resource accounting, representation dependence, configuration overhead, and perturbation analysis. We propose the Computational Attribution Protocol (CAP v0.2), a structured reporting checklist for making attribution claims easier to inspect and challenge. An 18-case synthetic diagnostic exercise confirms that CAP's predefined flags can be applied to deliberately constructed examples; because labels and rules were authored together, it does not establish external validity or superiority over existing frameworks. Our evidence does not establish a new physical-computation invariant, physical efficiency measurements, or a novel complexity theorem. We outline the independent evaluation required before CAP could be advanced as a validated assessment method.

**Keywords:** physical computation; computational attribution; representation; interfaces; counterfactual validation; reproducibility; unconventional computing.

## 1. Research question and scope

The broader State Evolution Research (SER) program asks which structural properties of computation, if any, remain meaningful across physical media and architectures. This paper addresses a narrower, operational question: **Under what declared interface, task, intervention, and resource constraints may a computational capability be attributed to a specified subsystem rather than to its surrounding apparatus?**

We distinguish *functional coverage* (what a complete system can compute) from *substrate attribution* (which subsystem implements the relevant transformations), and from *efficiency* (what resources the complete realization consumes).

## 2. Related work and novelty boundary

Horsman et al. (2014) explicitly address when physical systems compute and formalize the relationship between abstract and physical evolution, representation, and encoding/decoding. Piccinini (2015) develops a mechanistic account of physical computation and critiques simple mapping accounts. Horsman (2015) further develops abstraction/representation theory for heterogeneous physical computing. Established BDD literature analyzes representation size and variable-order sensitivity, including exponential separations. Consequently, none of these underlying observations should be claimed as SER discoveries. The proposed contribution is a practical, transparent bundle of tests and reporting requirements. Its distinctness and usefulness require external evaluation.

## 3. System model

Let a declared computational arrangement be

    C = (X, E, S, U, Phi, M, Y, F, epsilon, T, B, R)

where X is the task input domain; E is encoding; S the state space; U task-independent or explicitly programmable control; Phi the state transition or evolution; M measurement/decoding (possibly invasive); Y the output space; F the preregistered task; epsilon the permitted error; T the observation horizon; B the attribution boundary; and R the resource-accounting convention. This is a **working notation**, not a proved complete ontology. Report whether each map is fixed across tasks, learned, or reconfigured; include the costs of all auxiliary mechanisms.

For non-invasive, deterministic toy cases, a functional claim is evaluated by

    M(Phi_T(U(E(x)))) = F(x)

on a specified test set. Real systems require stochastic/error-aware and potentially measurement-backaction-aware variants.

## 4. Experimental synthesis

| Group | Tested issue | Supported conclusion | Boundary of evidence |
|---|---|---|---|
| H4-001–003 | Post-hoc decoders, holdouts and interventions | Post-hoc fitting can overfit; independent counterfactual tests distinguish arbitrary matching from validated discovered mappings | Restricted toy systems; post-hoc discovery can also be valid |
| H4-004–008 | Multiple interpretations, task-specific interfaces and programmability | Composite functional coverage alone cannot locate where computation occurs | Fixed and programmable Boolean constructions, not physical universality |
| H4-009–011 | Interface accounting, compact circuits and lookup | Resource rankings depend on implementation and cost assumptions | Constructive upper bounds and stipulated weights, not measured physical costs |
| H4-012–014 | ANF/SOP/ROBDD and variable order | Representation and interface configuration can strongly change apparent size | Different counting units; no universal optimal representation |
| H4-015 | Adaptation overhead | In the chosen model, configuration cost can be amortized after sufficient reuse | Search and switching costs stipulated, not measured |
| H4-016 | Boundary relocation | A fixed composite circuit can yield different core/decoder attribution under different bookkeeping cuts | Logical example, not a hardware equivalence result |
| H4-017 | Perturbation channel | XOR5 and Majority5 have different sensitivities to independent input flips | Compares functions, not hardware fault tolerance |
| H4-018 | Architecture controls | Built-in XOR logic succeeds; raw linear threshold readout cannot implement XOR; nonlinear feature engineering shifts work into interface | Minimal control, not broad physical cross-architecture validation |

### Selected quantitative examples

- H4-014: for equality of two four-bit strings, ROBDD size varies from **12** nodes (interleaved variable order) to **45** nodes (blocked order); all 8-input variable orders were enumerated.
- H4-015: under the stipulated model `fixed=45Q`, `adaptive=500+20S+12Q`, and `S=0`, the tuned representation is cheaper from **Q=16** evaluations onward (assuming one initial configuration, no further switching, and the stipulated search cost).
- H4-016: an XOR-then-NOT composite circuit implements XNOR for all four two-bit inputs regardless of whether zero, one, or two abstract operations are counted inside the declared core.
- H4-017: with independent 10% input-bit flip probability, XOR on five bits has **0.33616** average disagreement; five-bit Majority has approximately **0.15571**, in the specified input distribution.
- H4-018: XOR gate and explicitly programmed finite-state transition both implement XOR2 (4/4); a linear threshold function on raw inputs cannot realize XOR2, whereas augmenting the readout with the nonlinear feature `ab` can.

These are **demonstrations of methodological vulnerabilities and controls**, not evidence that a new physical computational law has been established.

## 5. Proposed Computational Attribution Protocol (CAP v0.2)

**CAP-1 Task registration.** Declare input distribution, target function, success threshold, horizon and evaluation set before fitting the interpretation.

**CAP-2 Boundary declaration.** Draw the full system boundary; identify the core, encoder, controller/program, decoder and measurement apparatus.

**CAP-3 Interface disclosure.** Specify which maps are fixed, task-specific, trained or reconfigured. Retain versions and seeds.

**CAP-4 Holdout and counterfactual validation.** Evaluate on withheld inputs and interventions that challenge accidental correspondence; explain which interventions are physically feasible.

**CAP-5 Full-stack resource ledger.** Record core and interface memory, computation, configuration/search, latency, energy where measurable, and amortization assumptions. Do not combine incomparable units without declared weights.

**CAP-6 Representation sensitivity.** Compare relevant encodings, variable orders or implementations; avoid treating one representation's size as intrinsic function complexity.

**CAP-7 Robustness protocol.** Specify whether noise enters inputs, internal dynamics, measurements or outputs; report error versus perturbation level.

**CAP-8 Architecture controls.** Include at least one deliberately limited control and one alternative architecture; account for any nonlinear feature construction or hidden preprocessing.

**CAP-9 Reproduction and negative results.** Release executable scripts, seeds, environment, raw outputs, failed tests and revision history.

A CAP-compliant report does not automatically prove physical computation or novelty; it makes a particular attribution claim easier to scrutinize and falsify.

## 6. Open problems

1. Is there a useful *boundary-robust* attribution metric after charging for all auxiliary resources?
2. How should reconfiguration, interface learning and program synthesis be accounted for in realistic hardware?
3. Can CAP distinguish nontrivial substrate contribution from externally implemented computation across analog, optical, reservoir and other non-Boolean systems?
4. What properties of computation remain invariant under justified changes in representation and resource model?
5. What independent benchmarks would demonstrate CAP's practical utility over existing frameworks?

## 7. Limitations and publication conditions

The present evidence relies largely on exact finite enumerations and toy models. Several experimental quantities are stipulations (e.g. cost weights and tuning overhead). The experiments do not measure energy, transistor count, physical latency or laboratory substrate behavior. A complete independent reproduction of the full H1–H4 record and comprehensive literature search remain outstanding. Numerical findings should be checked against the archived scripts and independently validated before claims are strengthened.

## 8. Conclusion

SER's H4 sequence supports a modest methodological position: computational attribution claims are incomplete unless task, representation, system boundary, interface freedoms, interventions and resource assumptions are explicitly specified. CAP v0.2 organizes these requirements into an auditable reporting workflow; independent validation is outstanding. Its value should be assessed by independent reproduction, comparison with prior frameworks, and application to genuinely distinct physical computing substrates.

## References (bibliographic verification pending)

1. Horsman, C., Stepney, S., Wagner, R. C., & Kendon, V. (2014). *When does a physical system compute?* Proceedings of the Royal Society A, 470, 20140182. https://doi.org/10.1098/rspa.2014.0182
2. Piccinini, G. (2015). *Physical Computation: A Mechanistic Account*. Oxford University Press. https://doi.org/10.1093/acprof:oso/9780199658855.001.0001
3. Horsman, D. C. (2015). *Abstraction/Representation Theory for heterotic physical computing*. Philosophical Transactions of the Royal Society A, 373, 20140224. https://doi.org/10.1098/rsta.2014.0224
4. Bryant, R. E. *Binary Decision Diagrams* (survey; variable ordering section). https://www.cs.cmu.edu/~bryant/pubdir/hmc-bdd18.pdf
5. Friedman, S. J., & Supowit, K. J. (1986). *Finding the Optimal Variable Ordering for Binary Decision Diagrams*. Princeton technical report TR-058-86. https://www.cs.princeton.edu/research/techreps/586


## 9. CAP v0.2 reporting and diagnostic status

CAP v0.2 requires nine disclosures: (1) task and distribution, (2) system graph and attribution boundary, (3) interface freedoms, (4) preregistered/holdout/counterfactual evidence, (5) separate resource vector, (6) representation and boundary sensitivity, (7) perturbation channel and metric, (8) matched controls, and (9) provenance and negative results. Each is coded as `provided`, `absent`, or `not_applicable`; evidence is distinguished as `direct`, `simulated`, `stipulated`, or `conceptual`. These labels flag missing evidence; they are not a universal score of computation.

An internally constructed diagnostic set of 18 examples was classified 18/18 by CAP and 9/18 by a deliberately narrower baseline. The cases, labels, and CAP rules were developed together. **This is an implementation sanity check, not independent evidence of predictive performance or superiority over established methodologies.** Independent cases, blinded raters, literature-grounded comparators, disagreement analysis, and predeclared evaluation criteria are necessary.

## 10. Research record and availability

The companion supplementary archive includes the previous SER Research Release 001 research materials and a SHA-256 manifest. Earlier H1–H3 materials and H4 experiments have heterogeneous reproducibility status; successful re-execution of scripts should not be confused with independent validation of the models. The public repository and Zenodo record will be linked only after actual deposit. The author should confirm distribution rights for every included file before upload.

## AI assistance disclosure

GPT-6 (OpenAI) assisted with research structuring, mathematical and experimental formulations, Python code and documentation drafting, synthesis of results, critical review, and manuscript preparation. This assistance does not constitute independent scientific validation. The human author, Dastan Arakeev Mederbekovich, is responsible for evaluating, verifying, approving, and publishing the scientific content. The specific model designation should be checked against the final submission environment and disclosure rules of the receiving platform.

## Publication ethics and research status

This is a dated research milestone and an invitation to replication and criticism. It is not a claim of a discovered universal invariant, independently validated methodology, or peer-reviewed result. No external laboratory experiments were performed. Prior research must be credited; the novelty of CAP remains to be assessed by independent comparison. No DOI, public repository URL, or external endorsement is asserted.

## Release statement

This document reports an ongoing research program and provisional methodological proposals. It is not peer reviewed. It makes no claim of discovering a new universal computational invariant or demonstrating physical-computing performance. Comments, replications, counterexamples, and critical review are welcome.


## License and reuse

Copyright © 2026 Dastan Arakeev Mederbekovich. This original manuscript and original author-owned research illustrations are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Original author-owned experimental source code is separately released under the [MIT License](LICENSE). Third-party materials, if any, are excluded from this grant and retain their original terms. See `LICENSE-CONTENT.md` and `LICENSE_SCOPE.md`.
