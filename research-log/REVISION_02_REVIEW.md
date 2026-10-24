# SER Publication Revision 02 — Internal methodological review
Date: 2026-10-22

## Decision: MAJOR REVISION; ready for transparent research-log release, not a validated-method paper.

### Completed
- Inspected Working Paper 01 v0.1 and CAP v0.2 proposal.
- Created and ran an 18-case deterministic synthetic diagnostic benchmark.
- All 18 CAP classifications agree with labels stipulated by the same case author; limited baseline 9/18.
- Results are reproducible by `python benchmark.py` (Python standard library).

### Critical validity caveat
This is **not** evidence that CAP outperforms real-world peer review or published physical-computation attribution frameworks. The case author selected the categories, labels, and detection rules; CAP was intentionally designed to cover those categories. There are no blinded reviewers, independently adjudicated labels, ambiguous real claims, time-on-task observations, or inter-rater reliability measurements. A narrower baseline was constructed for demonstration, not sampled from the literature. Do not present 18/18 vs 9/18 as an empirical performance claim.

### Paper claim audit
1. Attribution depends on system boundaries: valid as a demonstrated logical bookkeeping issue; not a new theorem.
2. Resource vectors matter: a justified reporting principle; physical energy/latency not measured.
3. Representation dependence: known results in Boolean function representations and BDD theory; cite foundational sources and avoid novelty claims.
4. CAP is a useful checklist: plausible, **not externally validated**.
5. Medium-independent physical invariant: **not established**.

### Publication gates
- G1: Full literature review with verified bibliographic entries and novelty matrix — OPEN.
- G2: Independent benchmark labels and at least two blinded evaluators — OPEN.
- G3: Comparison with strong baselines derived from literature, not a deliberately narrow straw baseline — OPEN.
- G4: Validation on at least one real physical or empirically sourced computing system — OPEN (optional for a clearly labeled methodological working note, required for broad physical efficacy claims).
- G5: Artifact manifest, version pins, hashes, licenses, AI disclosure — PARTIAL.
- G6: Re-run earlier H1–H3 and H4-001–007 with independent assertions — OPEN; archives exist in local workspace but not yet audited in this revision.

### Recommended release
Publish a v0.2 *working research note* with explicit synthetic-only evidence and open issues after source and citation checks. Do not advertise CAP as a validated standard or superior diagnostic protocol.
