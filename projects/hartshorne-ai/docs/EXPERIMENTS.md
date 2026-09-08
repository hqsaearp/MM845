# Experimental programme

This is an experimental design, not a record of completed runs. Architectural choices and numerical budgets below are new proposals for making the reconstructed programme executable.

## Questions and claims must stay separate

| Task | Input and target | Exact comparator | What a successful test would establish |
|---|---|---|---|
| P1 degree recovery | Gauge-obscured Laurent transition matrix; unordered integer pair | Constructive splitting witness and section counts | Recovery across unseen degree pairs and harder presentations |
| P2 splitting | Common representation of certified split/nonsplit bundles | Chern obstruction, sections, full Hom or cohomology | Classification beyond Chern-only information within stated distributions |
| P2 equivalence | Two obscured presentations | Canonical syzygy row space; later full Hom | Screening independent of presentation in a controlled family |
| Construction-family transfer | Held-out bundle construction | Same independent certificate protocol | Transfer beyond generator-specific patterns |
| Dimension transfer | Actual restrictions of certified P3 or higher bundles | Exact restriction and fixed-plane theorem | Performance on higher-dimensional-origin inputs, not automatic extension |
| Guided search | Candidate parameters and a ranking score | Exact verifier; budget-matched random ranking | Improved discovery or verification efficiency in the declared bounded space |

## Stage A: splitting degrees on P1

Generate $\mathcal O(a)\oplus\mathcal O(b)$, $a\le b$, obscure its standard transition by polynomial chart gauges, and store the presentation independently from its witness. Include diagonal/constant-gauge sanity checks and products of elementary shears with varied polynomial degree, length, and coefficient size.

For a bounded pilot, encode a Laurent matrix by its four coefficient arrays over a declared exponent interval, with a mask or explicit exponent coordinates. Do not truncate nonzero coefficients to fit an array: enlarge the representation or reject the sample with a logged reason. A small multilayer perceptron (proposed initial architecture: two 64-unit hidden layers) can regress $(a,b)$, sorting its outputs, or regress sum and nonnegative gap with a documented integer decoding rule. Closed-set classification over training degree pairs would make unseen-pair prediction impossible and is not the proposed task.

Report exact unordered-pair accuracy, integer-decoded pair error, pre-decoding absolute error, consistency of the predicted sum, and variation across equivalent gauges. Include the determinant exponent as a baseline for $a+b$; it does not determine $a,b$ separately. Compare with an independently computed section-count profile, and report its cost. Degree recovery from a known constructive witness is a label, not a learned result.

## Stage B: equivalence on P2

Start with the basepoint-free degree-$d$ syzygy family, initially $d=2,3$. Exact reduced row-echelon form in a fixed monomial order identifies $W$. Generate changes of the generator basis and, when implemented, equivalent graded-module or chart presentations.

For pairwise equivalence classification, partition underlying bundle classes **before** forming pairs. Form positive and negative pairs inside each partition; no bundle may occur in both training and test pairs, even as the second element of a negative pair. Use matching degrees/Chern values for nonisomorphic pairs. Canonical row-space comparison is a perfect family-specific symbolic baseline, not evidence of universal ML equivalence recognition. Base automorphisms are not automatically gauge equivalences.

## Stage C: splitting on P2 with matched controls

Within each Chern bin $(s,p)=(a+b,ab)$, compare the split bundle with locally free Serre-extension controls. Verify each extension and its section count before giving it a supervised label. Include syzygy nonsplit examples as an auxiliary family, but report results on the Chern-matched subset separately. A Chern-only classifier cannot discriminate balanced labels at the same input $(s,p)$.

Model-input variants must be named explicitly:

1. **Invariant-feature task:** Chern classes and a bounded section/cohomology profile. This is useful but may simply recover a known section-count test; label it accordingly.
2. **Presentation task:** transition matrices or a common graded-presentation encoding, with grading and polynomial coefficients but without construction names, witnesses, labels, row-space IDs, or record paths. The initial model can be a small MLP for fixed-size bounded inputs; a term/set encoder with pooled embeddings is a later proposal for variable-size presentations.
3. **Equivalence task:** paired encodings, separate from the binary splitting classifier and conditional degree predictor.

Never present construction-specific matrix sizes or padding patterns as a neutral input protocol. Split and Serre examples with visibly different presentation formats may be classified by format alone. Before claiming presentation-level success, audit source/target ranks, resolution lengths, masks, coefficient ranges, and gauge complexity. Use compatible encodings and nuisance randomisation where justified, then add leave-one-construction-out tests. If common chart conversion is too costly, explicitly limit the experiment to feature-based learning and discuss that limitation. Merely calling a representation “common” does not remove its shortcuts.

For nonsplit inputs the splitting-degree target is undefined. Store it as null, not as the roots of the Chern polynomial; store those roots separately as the **candidate** split target when they exist. A joint model must mask degree loss on nonsplit samples.

## Partition and leakage rules

- All equivalent presentations occupy one partition. On P1 the unordered degree pair is the isomorphism class, so every presentation of that pair is grouped.
- For Chern-matched generalisation, hold out entire Chern bins, with both classes present in each bin. Because a split pair gives only one split isomorphism class per bin, repeated gauges are not independent positive bundles.
- Add a stricter holdout by normalised Chern data/twist orbits. Otherwise twisting near-identical geometry can create misleading extrapolation results.
- Keep a parent bundle and all restrictions, gauges, twists, and other related records together whenever they are included in the same benchmark and might leak information. State the exact grouping policy for each experiment.
- Degree-pair, Chern-bin, construction-family, and dimension holdouts are different tests; do not conflate them into one random split.
- Fit normalisers on training data only. Freeze test data, partitions, architecture-selection rules, and resource budget before evaluation.
- Use certificate-derived IDs for classes where available; broader deduplication is unresolved until exact equivalence has been checked. A hash of presentation bytes is only a presentation ID.

## Metrics and baselines

For splitting report balanced accuracy, per-class precision/recall, confusion matrix, and probability calibration if probabilities drive screening. Report the false-nonsplit rate among certified split inputs: these are false counterexample alarms. For equivalence report false-match and missed-match rates. For every task report presentation-consistency under gauge changes.

Bootstrap uncertainty over independent bundle groups or Chern bins, not individual gauge replicas. Report raw group counts, label balance, run seeds, training and inference costs, certificate runtimes, memory, and timeout counts. Repeat final comparisons with multiple seeds after the single-seed pilot. Small numbers of distinct classes must be visible even when presentation counts look large.

Baselines: constant/majority prediction; exact Chern/discriminant logic; bounded section counts with their mathematical limitations; complete symbolic certification when feasible; simple linear or tree models alongside the neural model; random candidate ranking for search. Run ablations with and without Chern inputs and cohomology features. Beating a numerical baseline on a family already solved by an exact test is an engineering result, not new geometry.

## Transfer and AI-guided search

The P2 detector can be applied to the restriction of a verified higher-dimensional bundle. This avoids demanding that one network accept arbitrary numbers of ambient variables. It does not remove distribution shift: extendable plane bundles may be atypical, and a classifier trained on arbitrary plane constructions may fail on them. Evaluate P3-origin examples first; ensure their source bundles and exact restriction maps are stored.

There are no known positive counterexample training labels supplied for P7. Do not fabricate them, relabel invalid sheaves as bundles, or treat model confidence as evidence of existence. The eventual search is therefore a bounded candidate-ranking experiment, not ordinary supervised training on P7 counterexamples.

Any approved search must record the ansatz, parameter bounds, seed, proposals, duplicate removal, exact identities, rank/minor checks, validity outcomes, restriction, nonsplitting certificates, and all timeouts. Compare AI and random search at matched total compute, including model/training cost where relevant. Useful outcomes include lower verification cost or a better yield of valid candidates; a lack of counterexamples only describes the explored region. Learning from new verification results must not contaminate a supposedly frozen test set.
