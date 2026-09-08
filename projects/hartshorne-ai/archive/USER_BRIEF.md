# Preserved user-supplied cloud handoff

Archived during reconstruction on 2026-09-08. The text between the separators is the handoff supplied in this conversation. It is not the missing local-chat transcript. Later clarifications follow after the second separator. Do not silently replace this source with revised project prose.

---

I am moving an ongoing AI & Geometry research project into this cloud task. Treat the following as its working brief.

The project investigates Hartshorne’s rank-two vector-bundle conjecture: every holomorphic/algebraic rank-two vector bundle E on complex projective space P^n should split as O(a) ⊕ O(b) when n ≥ 7. The ambition is an AI-guided, mathematically certified search for a counterexample, while the realistic course outcome is a reproducible experimental study even if no counterexample is found.

Mathematical setup and corrections:
- Use the n+1 standard affine charts U_i={x_i≠0}, not “stereographic charts.” A bundle can be represented by g_ij∈GL_2(O(U_i∩U_j)) satisfying cocycle identities. A splitting is induced by chartwise algebraic frame changes h_i, with g'_ij=h_i g_ij h_j^{-1} diagonal.
- GAGA algebraizes holomorphic bundles on P^n, and restrictions to affine charts are algebraically trivial. Arbitrary rational matrices are not allowed: entries must be regular and determinants invertible on each overlap.
- For n≥2, c_1(E)=sH and c_2(E)=pH^2 determine the only possible split target: a+b=s and ab=p. This is an exact baseline, not evidence of learned geometry.
- All bundles split on P^1, but indecomposable rank-two bundles already occur on P^2. For a verified bundle on P^N, N≥3, splitting is detected by restriction to a fixed linear P^2 via successive hyperplane restrictions. An arbitrary plane bundle does not automatically extend to P^7.

Research programme:
1. P^1 warm-up: generate O(a)⊕O(b), obscure transition matrices by algebraic frame changes, and predict the unordered pair {a,b}. Hold out entire degree pairs and harder gauge changes.
2. P^2 equivalence benchmark: for d≥2, choose a basepoint-free three-dimensional space W=⟨f_1,f_2,f_3⟩⊂C[x,y,z]_d and define 0→E_W→O^3→O(d)→0. These are rank-two syzygy bundles. H^1_*(E_W)≅(S/(f_1,f_2,f_3))(d), so the generator row space is an exact family-specific identifier. Use this to validate generation, deduplication, and presentation invariance. This family is all nonsplit with an easy Chern/discriminant obstruction; do not use it alone for splitting classification.
3. P^2 Chern-matched controls: for split O(a)⊕O(b), choose k>max(a,b), a reduced finite Z of length (k-a)(k-b), and a locally free Serre extension 0→O(k)→E_Z→I_Z(a+b-k)→0. It has the same c_1,c_2 as the split bundle but is nonsplit; h^0(E_Z(-k))=1 distinguishes it. This prevents a classifier from succeeding solely through Chern classes.
4. Exact verification layer: certify local freeness globally using rank/minor and saturation conditions; classify an example as invalid, certified split, certified nonsplit, or unresolved. For general valid rank-two bundles E,F with the same determinant, compute global Hom(E,F); determinant of a linear combination of a Hom basis gives a scalar quadratic, nonzero exactly when E≅F. A failed bounded gauge search is only unresolved.
5. ML experiments: distinguish recovery of invariants, splitting classification, equivalence screening, transfer across construction families/dimensions, and AI-guided search. Keep all equivalent presentations in one train/validation/test partition. Hold out whole Chern bins for Chern-matched tests. Compare with Chern/discriminant, section-count, symbolic, and random-search baselines.
6. Only after the lower-dimensional core works, add audited P^3 constructions and a bounded P^7 search. The model may rank candidates; exact algebra must establish defining identities, rank two, local freeness, and nonsplitting. Do not transplant the three-form P^2 syzygy ansatz to higher P^n: three positive-degree forms then have a common projective zero. Do not use an overly restrictive short monad built only from line bundles if known cohomological constraints preclude a counterexample.

Course framing:
This should be shaped for MM845 — Tópicos de Geometria III: AI for Geometry. The required deliverables are an individual project, a two-page project plan by the end of week 5, a five-page final report, a 10-minute final-week presentation, and a public project repository expected in week 7. The course emphasizes reproducibility, version control, fixed seeds, tests, code review, and independent verification of AI-generated code.

The best working arrangement should be a hybrid:
- this cloud task / ChatGPT project for research discussion, sources, decisions, and drafting;
- a GitHub repository as the public, reproducible record of code, data manifests, configurations, exact certificates, and results;
- VSCode plus Python and Macaulay2 for executing the experiment, not merely prompting;
- Overleaf for the two-page plan, final report, and presentation if useful.
Do not claim that a dataset, a model, or an implementation already exists. A detailed local research programme was drafted but is not automatically available in the cloud; the contents above supersede it.

First task: turn this brief into a concise MM845-ready project specification with a concrete first implementation milestone, a minimal repository structure, and a two-page-plan outline. Identify any mathematical or experimental risks before proposing code.

---

## Subsequent project clarification, verbatim excerpt

> The main elements were about predicting the splitting degrees a and b, training for low N to distinguish decomposable and indecomposable bundles with various criteria but ultimately ML, with a view to generalising to higher N. we also noticed that it might suffice to study splitting over some P^2 inside P^n

The user also explicitly instructed the assistant not to continue searching mail and unrelated research. That exclusion applies to this reconstruction.

## Additional MM845 assignment requirements supplied in project context

The project-plan announcement specifies one PDF, two pages of body text: approximately one page mathematical problem and approximately one page AI setup (data, generation, method, goal). References may occupy a following third page, but no body text may. Deadline given: 13 September 2026, 23:59. These requirements refine the earlier week-5 description.

## Preservation request

> reconstruct my project completely and create a github place for it in my account so we don't ever lose info again

This archive fulfils the available-context preservation part of that request. Git history and independent backups reduce loss risk; no system guarantees preservation of future unsaved conversations.
