# Roadmap and first executable milestone

All stages below are planned. Only the documentation-preservation stage is supplied by the initial publication. Numerical choices are provisional defaults, not recovered decisions from the missing chat.

## M0 — Preserve and stabilise the specification

- [x] Reconstruct the available brief and its central splitting/ML direction.
- [x] Separate established mathematics, experimental proposals, and unknown history.
- [x] Define exact-label, leakage, and acceptance contracts.
- [ ] Produce and visually verify the actual two-page project-plan PDF.
- [ ] Decide whether to migrate this directory into a standalone project repository before week 7.

## M1 — Exact P1 data round-trip, before training

Goal: a small deterministic generator and independent verifier that produce legitimate transition data with recoverable degree labels.

Proposed pilot: 55 unordered pairs $-4\le a\le b\le5$, with 12 ordinary gauge presentations per pair (660 presentations). Shuffle the pair list using the declared RNG algorithm and seed 20260908, then assign 39 pairs to training, 8 to validation, and 8 to test. Add 12 harder-gauge presentations for each of the same 8 held-out test pairs (96 additional presentations); these remain in the test partition. These numbers are specified in [pilot.json](../configs/pilot.json), which is not an executed dataset manifest.

Ordinary gauges: short products of upper/lower elementary polynomial shears on each affine chart, proposed degree at most 2 and at most 4 factors. Hard test: proposed degree at most 5 and at most 10 factors. Use integer coefficients in [-3,3], exact rational arithmetic, and explicit inverses. Include identity and constant-gauge fixtures. Zero polynomials/factors are permitted only as deliberate fixtures or under a documented sampling rule.

Deliverables to implement:

1. Pure generation of exact Laurent matrices, with the chart/sign convention in MATHEMATICS.md and serialised inverse-gauge witnesses.
2. Deterministic export/import with content hashes and exact polynomial round-trip.
3. Verification of Laurent regularity, units, inverse identities, determinant exponent a+b, and recovery of the original diagonal transition via the stored gauge.
4. Independent degree/section check on a subset, not just re-reading the generator parameters. Possible route: exact linear equations for compatible polynomial sections with proved degree bounds; the gauge witness gives safe bounds for transformed split sections in this pilot. Test h0 against the known formula over a twist range that contains both breakpoints.
5. Group-level partitioning before augmentation, plus automated no-overlap checks.
6. Tests deliberately rejecting a nonunit overlap determinant such as t-1, wrong inverse, wrong sign, malformed coefficient encoding, and a noninvertible chart gauge.
7. Pinned Python dependencies, a documented Macaulay2 version/install route for later stages, and a reproducible command interface. Pin only versions actually installed/tested; do not invent a lock file.

Acceptance gate: all exact fixtures pass; all deliberate invalids are caught; the same seed produces byte-identical canonical manifests; no degree-pair leakage; a fresh environment can reproduce the pilot; an independent reviewer can inspect the certificate logic. Only then train the first small model. The command names and code layout are not yet implemented.

## M1b — First ML experiment

Train the small degree-regression model and simple baselines on the M1 split. Report exact pair accuracy and errors on unseen pairs and harder gauges, with a clear distinction between determinant-degree recovery and full pair recovery. A small extrapolation set outside the training degree interval can be a separately declared test. Do not tune against the hard test repeatedly.

## M2 — P2 family-specific equivalence

Implement the syzygy generator for d=2,3, saturation-based basepoint checks, exact Chern data, row-space IDs, and a comparison of the full graded H1 module with S/I(d). Start with the three hand fixtures in MATHEMATICS.md before random samples. Equivalent changes of generators must preserve labels, while distinct canonical row spaces must be distinguished. Pairwise datasets are formed after grouping/partitioning bundles. Benchmark the model against exact row-space comparison.

## M3 — Genuine Chern-matched classification

Construct and verify the one-point Serre fixture first, then modest families of reduced rational points and extension classes. Confirm both local freeness and h0(E(-k))=1 independently. Include zero/locally vanishing extension classes as invalid tests. Only after successful fixtures generate balanced split/nonsplit Chern bins. Determine pilot size from measured saturation/Hom costs rather than promising a large dataset. Implement the common input-format audit and Chern-only/section-count/ML comparisons.

## M4 — Broader exact equivalence and transfer

Implement complete global Hom and its determinant polynomial. Validate it against syzygy IDs, split bundles, and Chern-matched controls. Add audited P3 bundles with explicit valid constructions and compute their actual fixed-plane restrictions. A null-correlation/instanton-family pilot is a candidate to investigate, not an approved or implemented generator. Test family and dimension transfer without turning unproved P2 extensions into P3 data.

## M5 — Bounded high-dimensional search, optional

Approve an ansatz only after a literature/cohomology audit shows that its constraints do not automatically force splitting or invalidity. No P7 ansatz has yet passed this gate. Set finite degree/coefficient/size bounds and an exact compute budget, then compare AI ranking with random search. Log every status and certificate. Escalate any apparent valid nonsplit P7 example to independent exact verification before making a mathematical claim.

## Minimal layout as implementation grows

The current files are documentation plus the proposed pilot configuration. Add only when implemented:

| Path | Responsibility |
|---|---|
| `src/` | Python generation, encodings, partitions, ML, orchestration |
| `m2/` | Macaulay2 exact construction and verification routines |
| `tests/` | Hand fixtures, invalids, invariance, leakage, replay |
| `configs/` | Versioned generation/training/verification configurations |
| `data/` | Small manifests and fixtures; documented storage for larger data |
| `certificates/` | Exact replayable algebra and hashes |
| `results/` | Run summaries, costs, metrics, and limitations |
| `reports/` | Plan/report/presentation sources and reviewed deliverables |

Do not create empty placeholder datasets or logs that could be mistaken for results. Proposed development acceptance target: two documented actions to set up and reproduce the smallest experiment, after dependencies are genuinely tested.

## Resource and scope controls

Proposed first pilot runs on CPU. Start exact P2 jobs with a 60-second per-example cap and record memory; reassess after smoke tests. A timeout is unresolved. Do not interpret the cap as a theorem-level bound. Fix the larger-run budget only after profiling. If time is short, prioritise M1–M3 and a rigorous report over P7. If Serre construction is not working, report the reduced scope rather than substitute the easy syzygy discriminator and claim the Chern-matched question was answered.
