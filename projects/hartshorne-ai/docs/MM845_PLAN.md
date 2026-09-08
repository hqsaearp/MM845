# MM845 project-plan outline and deliverables

Working title: **Learning splitting of rank-two vector bundles: low-dimensional benchmarks and certified higher-dimensional search**.

Owner: Henrique Nogueira de Sá Earp. Course: MM845 — Tópicos de Geometria III: AI for Geometry, IMECC–Unicamp, second semester 2026. This is an individual project.

## Submission requirements supplied by the user

The assignment announcement by Edward George Hirst specifies a single PDF with a two-page body: approximately one page on the mathematical problem, stated clearly with suitable references, and approximately one page on the AI setup, explaining the data, generation, method, and goal. References may appear on a third page, but body text may not. Deadline: **13 September 2026, 23:59**, interpreted in the course's São Paulo time zone.

The working brief additionally specifies a public project repository expected in week 7, a five-page final report, and a ten-minute final-week presentation. Final dates and any report bibliography allowance must be checked against the actual course announcement; do not infer them. This dedicated directory is an initial public versioned home, not yet a standalone mini-project repository.

## Two-page body: proposed allocation

### Page 1 — Mathematics (roughly 450–550 words plus equations)

1. State Hartshorne's rank-two conjecture over complex projective space with the threshold n >= 7. Separate the long-term counterexample ambition from the course-sized experimental question.
2. Introduce algebraic transition presentations on standard affine charts and algebraic frame changes. Explain why different presentations can represent the same bundle.
3. Explain the P1 warm-up: splitting is guaranteed, but the unordered degrees need to be recovered from an obscured presentation. On P2, include genuine indecomposables.
4. State the Chern-root baseline a+b=s, ab=p and why it is insufficient for classification. Give the syzygy family as an equivalence testbed, and the Chern-matched Serre family as the essential nontrivial splitting control. Keep construction details concise and point to the repository for derivations.
5. State the fixed-linear-plane splitting equivalence for already verified bundles on P^N. Explain that this reduces detection, not the problem of extending a plane bundle.

End with a concrete research question: can ML recover splitting information across gauge changes and held-out classes/families, and can a plane-based detector transfer to actual restrictions of higher-dimensional bundles?

### Page 2 — AI and reproducibility (roughly 450–550 words)

1. **Data:** exact rational presentations with replayable certificates; P1 degree pairs and gauges, P2 syzygy equivalence examples, and balanced Chern-matched split/nonsplit controls. No dataset already exists at the time of this reconstruction.
2. **Inputs/targets:** lossless bounded polynomial encodings; unordered degree regression on split inputs; a separate splitting classifier and optional equivalence model. Generator labels, gauge witnesses, and class IDs are excluded from predictors.
3. **Method:** a small neural baseline (initial P1 MLP), compared with linear/tree and exact-invariant baselines. Defer larger architectures until sample complexity and representation justify them. Distinguish feature-based learning from presentation-level learning.
4. **Evaluation:** group by isomorphism class; hold out degree pairs, harder gauges, whole Chern bins, and construction families in separate tests. Use exact degree accuracy, balanced classification metrics, gauge consistency, and resource cost. Include Chern-only and section-count ablations.
5. **Work plan and success:** exact P1 generator/verifier, first learner, P2 equivalence and matched controls, then optional P3 transfer. P7 search is explicitly stretch scope. A reproducible and well-diagnosed negative experiment counts as a valid outcome.
6. **Reproducibility:** Python/Macaulay2, pinned tested versions, fixed seeds, manifests/hashes, independent review of AI-generated code, public Git history, and invalid/split/nonsplit/unresolved outcomes.

Word allocations are layout targets, not proof that the plan fits. The actual PDF must be compiled and visually checked. This file is an outline, not the finished submission.

### Optional page 3 — References only

Select approximately four to six essential references from [REFERENCES.md](REFERENCES.md): conjecture statement, splitting/Horrocks, Hartshorne–Serre, and algebraic computational foundations as space permits. Include no extra body discussion on this page.

## Later deliverables

Five-page report structure (provisional allocation): problem and exact foundations (1 page); data and certification (1); representations/methods/partitions (1); actual results and costs (1); limitations, reproducibility, and next directions (1). Replace these allocations if course instructions differ. Report unsuccessful constructions and unresolved checks honestly.

Ten-minute presentation: 2 minutes mathematical target and plane reduction; 2 minutes certified data and shortcut controls; 3 minutes experiments/results actually completed; 2 minutes interpretation and limitations; 1 minute reproducibility and outlook. Do not use the presentation to imply a high-dimensional construction that has not been certified.

## Working arrangement

- ChatGPT/cloud task: research discussion, sources, decisions, and draft prose.
- GitHub: canonical versioned documents, code, data manifests, configurations, certificates, and results. Record substantive discussion here after each session.
- VSCode + Python + Macaulay2: implementation and actual execution, not merely prompting.
- Overleaf: optional plan/report/presentation editing; synchronise reviewed source back to GitHub. No Overleaf project has been created or linked by this initial publication.
