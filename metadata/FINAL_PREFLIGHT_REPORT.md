# SER Release 001 — Final Preflight Review

**Decision:** CONDITIONALLY READY for a public *research milestone*, NOT ready to claim validated scientific novelty.

## Completed checks
- Manuscript author and affiliation present.
- Explicit preliminary / not peer-reviewed status, limitations, and AI assistance disclosure present.
- Manuscript includes experiments, methods, CAP, open questions, and references.
- Original 33-file research archive retained intact as supplementary archive.
- CAP v0.2 specification supplied separately.
- PDF generated from final Markdown and inspected programmatically for page count and text extraction.
- ZIP structure and checksums verified locally.

## Required author approvals before uploading
1. Confirm spelling and preferred romanization of author name, and whether to include ORCID and contact email.
2. Confirm permission and licensing for all archived scripts, text, and dependencies. Recommended: CC BY 4.0 for manuscript; MIT for original code, only after reviewing all files. No license has been granted automatically.
3. Independently verify every bibliographic reference, including DOI, publication year and bibliographic metadata. **Not independently verified in this preflight.**
4. Review manuscript line by line, including all quantitative claims against source experiments. **No new independent numerical audit performed in this pass.**
5. Decide whether all historical experiment archives should be public; remove any private information or inappropriate content before deposit.
6. Approve GitHub repository description and Zenodo metadata, then upload and obtain actual URLs and DOI.

## Known methodological limitations
- CAP's 18/18 diagnostic result is an in-sample sanity check with authored labels and rules; no external validation.
- H4-017 compares functions under input noise, not physical device reliability.
- H4-018 is a small XOR toy comparison, not a physical cross-substrate experiment.
- H4-015 search/reconfiguration costs are stipulated, not measured.
- Re-execution of code does not establish independent correctness.

## Decision scope
Public GitHub/Zenodo release can be made **after** author approvals above, with explicit 'preliminary research milestone' wording. A peer-reviewed-paper claim or claims of a new physical-computation invariant would be premature.
