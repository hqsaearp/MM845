# Exact verification and data contract

No verifier or certificates are implemented in this initial documentation commit. This document specifies their contract. A certificate means replayable exact algebra plus its stated mathematical justification, not a proof-assistant formalisation.

## Outcomes

| Status | Meaning | Required evidence |
|---|---|---|
| `invalid` | The proposed presentation fails a required bundle condition | Exact failed identity, nonunit, wrong rank, or nonempty bad locus |
| `certified_split` | Globally valid rank-two bundle with a proved splitting | Validity certificate plus invertible global map or equivalent complete argument |
| `certified_nonsplit` | Globally valid rank-two bundle with proved nonsplitting | Validity certificate plus exact obstruction, section discrepancy, or complete Hom/cohomology test |
| `unresolved` | Available computation establishes neither of the preceding conclusions | Completed checks, outstanding checks, and bounds/timeouts |

Maintain `validity_status` separately (`certified_valid`, `certified_invalid`, or `unresolved`). A timeout during validity does not mean that a valid bundle exists. A valid bundle with an incomplete splitting check remains `unresolved`. ML predictions never modify a certificate status.

## Validity before classification

For chart presentations, verify every matrix entry in its intended localised ring, determinant units, inverse identities, and all triple-overlap cocycles. Store the coordinate substitutions and denominators inverted on each intersection. A nonzero determinant in a fraction field is insufficient.

For kernels, cokernels, or monad cohomology, specify the graded ring, modules, shifts, maps, and sheafification. Verify composition-zero identities; certify the ranks required by the construction everywhere, not only generically. For a monad $A\to B\to C$, include bundle injectivity/surjectivity conditions and the resulting cohomology rank. Appropriate determinantal/Fitting ideals describe bad-rank loci; prove their projective emptiness by saturation with respect to the irrelevant ideal. A single unsaturated minor calculation does not suffice. The exact criterion depends on the presentation and must be documented by each generator.

For syzygies of three forms on P2, certify that the common-zero locus is empty, equivalently that the saturation of their ideal is the whole ring. For Serre controls, certify length, reducedness and local-complete-intersection properties of Z as required, the extension class, and local freeness of the middle term. The zero extension class is an intentional invalid-control test when its middle term is not locally free.

All primary arithmetic is exact. A certificate over Q must establish the corresponding result after extension to C. Finite-field computations may be exploratory or modular aids only; a characteristic-p example alone is not a complex counterexample. Numerical sampling can catch bugs, not certify global rank or nonvanishing.

## Splitting and equivalence certificates

- Compute Chern data from the verified presentation, independently of generator labels where feasible.
- If no integer split pair exists, record that obstruction. Otherwise retain the candidate pair separately from a proved pair.
- A constructive certificate records a global map from the proposed split bundle, checks its compatibility with all presentations/charts, and verifies its nonzero constant determinant.
- A nonsplitting section certificate gives an exact twist and a section dimension different from the only possible split target.
- On P2, a nonzero graded piece of H1 proves nonsplitting. Vanishing over an arbitrary finite twist window does not prove splitting; supply a complete finite-length-module calculation or justified bounds for all remaining twists.
- For general equivalence/splitting via Hom, compute the full sheaf Hom space, not just a guessed finite-degree set of polynomial maps. Explain saturation, grading, and why the space is complete. Expand the determinant quadratic exactly; store a nonzero coefficient and a successful evaluation for isomorphism, or the complete zero polynomial and completeness evidence for nonisomorphism.
- If the fixed-plane theorem is used, store the parent validity certificate and the exact linear embedding/restriction. A nonsplit plane bundle unconnected to a valid parent is not a high-dimensional certificate.

## Proposed record contract

One manifest entry per presentation; exact polynomials and certificates may live in referenced files. JSON/JSONL is proposed. No sample records in this archive represent generated data.

| Field | Required content |
|---|---|
| `schema_version`, `record_id` | Version and unique presentation identifier |
| `base_field`, `ambient_dimension`, `rank` | Exact coefficient field, geometry, and claimed/verified rank |
| `construction_family`, `parameters` | Generator and parameters, kept out of ordinary model inputs |
| `polynomial_encoding` | Variable order, grading, monomial order, exponent tuples, rational numerator/denominator pairs, chart localisations |
| `presentation_path`, `presentation_sha256` | Exact input and content hash |
| `bundle_group_id`, `group_basis` | Isomorphism-class grouping and its proof/method, not a byte hash masquerading as an invariant |
| `parent_bundle_id`, `restriction_map` | Parent and exact plane map if applicable; otherwise null |
| `seed`, `generator_version`, `source_commit` | Reproducible generation provenance |
| `gauge_witness_path`, `witness_sha256` | Protected label-side witness; never an input feature |
| `chern`, `chern_bin`, `normalised_chern_bin` | Exact invariants and grouping keys where defined |
| `candidate_split_degrees`, `certified_split_degrees` | Potential roots versus a proved splitting; null when inapplicable |
| `validity_status`, `certificate_status` | Independent validity and four-way mathematical outcome |
| `certificate_paths`, `certificate_hashes` | Replayable exact evidence |
| `partition`, `partition_policy_version` | Train/validation/test assignment fixed at group level |
| `checks`, `timings`, `resource_limits`, `failure_reason` | Completed/pending checks, cost, limits, and failures |
| `review_status`, `review_notes` | Independent review of code/proof assumptions |

Run records additionally include dependency versions, OS/architecture, random seeds for all libraries, data/partition hashes, model and preprocessing configuration, training logs, checkpoint hash if any, metrics by independent group, and all excluded examples with reasons. Keep certificate computation and prediction outputs in distinct fields/files.

## Independent checking and preservation

The generator and verifier should not merely call the same helper and compare its output with itself. Use hand-computable fixtures, an independent section/Hom computation, and deliberate invalid cases. Review AI-generated code and the assumptions connecting algebraic computations to geometry. A second human/CAS check is desirable; no such review is claimed in this initial commit.

Future generated data belong in `data/` with committed manifests; exact certificates in `certificates/`; configurations in `configs/`; summarised runs in `results/`. Large reconstructible data and model weights need an explicit size/storage policy before upload. Never put credentials, private mail, or unrelated personal context in the public repository. Store no browser/session secrets in a recovery archive.
