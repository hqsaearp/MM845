# Canonical research context

Last reconstructed: 2026-09-08. Owner: Henrique Nogueira de Sá Earp.

## Provenance and limits

The authoritative inputs are (1) the user's full cloud handoff, preserved in [archive/USER_BRIEF.md](archive/USER_BRIEF.md); (2) the clarification that the central project is predicting splitting degrees, learning split/indecomposable distinctions at low dimension, and transferring upwards, potentially through a fixed plane; and (3) the MM845 assignment requirements provided in project context. Mathematical explanations in the accompanying documents are a reconstruction with explicit arguments, not evidence that these arguments were proved in the inaccessible conversation.

The user described a substantially matured local discussion. Its full transcript is unavailable here. Do not say it has been imported, recovered, deleted, or reconstructed verbatim. Nothing in this archive establishes its deletion. Do not fill gaps with unrelated research correspondence. In particular, the previous detour through email and adjacent gauge-theory projects was rejected by the user and is excluded from this project.

The following is complete relative to the available handoff, not a guarantee about unseen local material. New defaults (pilot sizes, seed, model architecture, resource caps, and milestone subdivision) are explicitly proposals, not recovered historical decisions.

## Scientific question

Hartshorne's rank-two vector-bundle conjecture predicts that every rank-two algebraic/holomorphic bundle on complex $\mathbf P^n$, $n\ge7$, is $\mathcal O(a)\oplus\mathcal O(b)$. The ambition is a counterexample search with exact mathematical certification. The achievable MM845 objective is a reproducible study of learning bundle invariants and splitting, with honest negative or inconclusive findings.

ML remains central. Symbolic algebra supplies labels, baselines, and certificates; it is not a reason to quietly replace the learning project by a purely symbolic classification exercise. Conversely, a neural prediction is not a proof or a bundle construction.

## Six distinct tasks

1. **Invariant recovery:** predict unordered integer splitting degrees when a bundle is split. On $\mathbf P^1$, all bundles split, so this is the warm-up. For $n\ge2$, exact $c_1,c_2$ determine the only possible split pair; predicting those roots alone is not evidence of deeper learnt geometry.
2. **Splitting classification:** distinguish split from indecomposable rank-two bundles on $\mathbf P^2$, including Chern-matched controls and presentation changes.
3. **Equivalence screening:** recognise multiple presentations of the same bundle. Start with a syzygy family that admits an exact identifier; later compare with the complete global-Hom determinant test.
4. **Transfer across families:** test whether learning persists when the bundle construction changes, not just its coefficients or presentation.
5. **Transfer across dimensions:** classify restrictions of globally certified higher-dimensional bundles. A distribution of arbitrary plane bundles is not automatically a distribution of such restrictions.
6. **AI-guided search:** prioritise a bounded, audited candidate space against random search, while exact algebra establishes all claimed mathematical properties.

## Mathematical commitments

- Use the $n+1$ standard affine charts, regular transition entries, overlap units as determinants, and genuine algebraic frame changes. No stereographic-chart terminology or arbitrary rational matrices.
- GAGA and Quillen–Suslin justify algebraic bundles and algebraic triviality on each affine chart, respectively. They do not make construction or trivialisation computationally cheap.
- On $\mathbf P^1$, gauge-obscured split bundles provide integer degree labels. Hold out whole degree pairs, as well as more difficult gauges.
- On $\mathbf P^2$, basepoint-free triples of degree-$d$ forms give nonsplit syzygy bundles. Their generator row space is a family-specific identifier over a fixed base, not a general invariant for all bundles and not a splitting benchmark by itself.
- Chern-matched Serre extensions supply nonsplit controls for split $\mathcal O(a)\oplus\mathcal O(b)$. Their section count exposes the limitation of a Chern-only classifier.
- A verified vector bundle on $\mathbf P^N$, $N\ge3$, splits if and only if its restriction to any fixed linear $\mathbf P^2$ splits. The same degrees lift. This detects splitting; it does not solve the extension problem from the plane.
- Every mathematical label is one of invalid, certified split, certified nonsplit, or unresolved, with a separate record of whether validity itself was certified. Failed bounded searches do not certify nonsplitting.

## Experimental commitments

Use exact rational coefficients initially, with an explicit base-change interpretation over $\mathbf C$. Keep construction/gauge witnesses and exact labels separate from model inputs. Every equivalent presentation belongs to one partition, including restrictions and other derived records that could leak the same parent object. Hold out whole Chern bins for Chern-matched generalisation tests. Balance split/nonsplit labels within matched bins. Report group-level rather than presentation-count-only uncertainty.

Compare ML against Chern/discriminant, section-count, exact symbolic, and random-search baselines as appropriate to each task. Log costs, failures, timeouts, and unresolved cases. No claim of counterexample, generalisation, model success, or absence of counterexamples follows from a pilot that has not been run.

## Course commitments

Individual MM845 project; two-page project-plan body due 13 September 2026 at 23:59 (course time, São Paulo), approximately one page mathematics and one page AI. References may occupy a third page only. The user also supplied: public repository expected in week 7, five-page final report, and ten-minute final-week presentation. No final-report calendar date is inferred. The week-7 standalone-repository expectation still needs attention if this directory remains inside the course fork.

## State and next action

At initial publication only the documentation and proposed pilot configuration exist. Dataset: none supplied. Model: none supplied. Bundle implementation: not yet built. Certificates/results: none supplied. Environment: not pinned or validated for this project; Macaulay2 was not available in the reconstruction runtime. No experiment was executed.

The next technical milestone is the small exact $\mathbf P^1$ generator/verifier described in [docs/ROADMAP.md](docs/ROADMAP.md), followed by the $\mathbf P^2$ equivalence and Chern-matched controls. The immediate course-writing action is to turn [docs/MM845_PLAN.md](docs/MM845_PLAN.md) into the required PDF; this archive is not that submission.

## Resume instruction

Read this file, the session log, decisions, and roadmap before work. Check the remote revision and local changes. Preserve manual edits. Do not restart the email/history search, manufacture missing context, conflate plans with results, or advance to $\mathbf P^7$ before the lower-dimensional gates pass. End substantive sessions by recording what changed, what was checked, remaining blockers, and the next executable action, then commit and verify the remote.
