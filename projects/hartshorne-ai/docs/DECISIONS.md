# Decision register, risks, and open questions

Initial date: 2026-09-08. Append entries when choices change; preserve their rationale and provenance. “Accepted” below means stated by the user or established in the supplied corrected brief, not a recovered transcript of the unavailable chat.

## Accepted scope and corrections

| ID | Decision | Reason/provenance |
|---|---|---|
| D01 | ML degree recovery and splitting classification are central; P7 counterexample search is the long-term ambition | User's clarification and original brief |
| D02 | Start with P1, then P2, with audited P3 and bounded P7 only later | Practical scope and mathematical availability of examples |
| D03 | Use standard affine charts and algebraic gauges | Corrected mathematical setup |
| D04 | Treat Chern-root recovery as an exact baseline for n >= 2 | It is algebra, not independent evidence of learnt geometry |
| D05 | Use plane syzygies for equivalence; not alone for splitting classification | Their discriminant already forces nonsplitting |
| D06 | Include locally free Chern-matched Serre controls | Prevent success based solely on Chern classes |
| D07 | A fixed P2 restriction detects splitting of a verified global bundle | Hyperplane lifting theorem; no assumption of automatic extension |
| D08 | Only exact verification yields mathematical labels | ML confidence and failed bounded searches are not proofs |
| D09 | Keep all equivalent presentations in one partition; hold out Chern bins | Avoid leakage and memorisation claims |
| D10 | Preserve context in GitHub and work in an executable Python/Macaulay2 workflow | User's request for durable continuity and course reproducibility |
| D11 | Exclude mail and unrelated research strands | User explicitly rejected that retrieval tangent |

## Operational choices made in this reconstruction

| ID | New choice | Status |
|---|---|---|
| P01 | Store the project under `hqsaearp/MM845/projects/hartshorne-ai/` | Initial GitHub home; connector cannot create a new repository |
| P02 | Use the proposed seed, sizes, and gauge ranges in `configs/pilot.json` | Unexecuted defaults; may change before data freeze |
| P03 | Begin with a small P1 degree-regression MLP and simple baselines | Proposed, not trained or benchmarked |
| P04 | Record full available handoff, canonical context, decisions, and session log | Documentation supplied now |
| P05 | No automatic synchronisation/backup service is configured | Manual/session-driven commit-and-verify protocol only |

## Risk register

| Risk | Consequence | Required mitigation |
|---|---|---|
| Missing original transcript | Lost decisions may be replaced by invented history | Preserve supplied text; distinguish proposals; accept future exports as new provenance |
| Invalid transitions or rank drops | A sheaf is mistaken for a bundle/counterexample | Exact local-ring identities and global bad-locus saturation |
| Naive three-form high-dimensional construction | Common zeros destroy the intended surjection | Keep it on P2; require a separate higher-dimensional ansatz |
| Restrictive monad or equivariant ansatz | Entire search space is already forced to split | Audit cohomological and symmetry constraints before search |
| Plane detector confused with extension | A P2 example is misreported on P7 | Certify a parent bundle and its actual restriction |
| Chern/presentation shortcut | High accuracy without the intended learnt geometry | Matched bins, feature ablations, format audits, family holdouts |
| Gauge/class leakage | Inflated generalisation metrics | Partition by proven classes before augmentation/pair formation |
| Many gauges, few independent bundles | Misleading data size and uncertainty | Count classes/bins; group-level uncertainty estimates |
| Missing complete Hom or all-twist bounds | A bounded failure is called nonsplitting/splitting | Record completeness or return unresolved |
| Exact algebra too expensive | Course scope overruns | Tiny fixtures, profiling, timeouts, staged gates |
| Positive-characteristic artefacts | Irrelevant apparent complex counterexample | Exact characteristic-zero verification/base-change argument |
| Transfer to extendable plane bundles fails | Low-dimensional training does not serve higher dimension | Evaluate real P3 restrictions and report distribution shift |
| Degree and class targets conflated | Nonsplit bundles get fictional splitting labels | Separate candidate roots, certified pairs, and masked degree loss |
| Uncommitted/unsynchronised work | GitHub does not contain current progress | Session updates, commit/push verification, independent clone |

## Open choices: do not pretend these are resolved

- Exact rational-generation distribution and RNG algorithm/version.
- Common P2 presentation encoding and the computational cost of chart trivialisation.
- Robust graded Hom/cohomology implementation and independently checked completeness conditions.
- Number and spread of Chern bins after timing Serre-extension fixtures.
- Architecture and training hyperparameters selected without test contamination.
- Approved P3 constructions; any admissible P7 candidate ansatz.
- A standalone repository name and migration procedure before the week-7 deliverable, if required.
- Tested dependency versions, actual available Macaulay2 environment, compute budget, and independent reviewer.
- Overleaf project/source arrangement and actual final-report/presentation dates.

Do not list P7 candidates, successful models, complete data, a proved counterexample, or a fully recovered conversation under “completed” until corresponding evidence exists.
