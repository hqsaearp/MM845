# Learning splitting of rank-two bundles

Henrique Nogueira de Sá Earp · MM845 — Tópicos de Geometria III: AI for Geometry · IMECC–Unicamp · 2026

The project studies whether machine learning can recover splitting degrees and distinguish split from indecomposable rank-two vector bundles, first in low dimensions and then on restrictions of genuine higher-dimensional bundles. Its long-term ambition is an AI-guided, exactly certified search for a counterexample to Hartshorne's rank-two conjecture on complex projective space. A reproducible experimental study is the course deliverable; a counterexample is not an expected or promised outcome.

## Start here

- [CONTEXT.md](CONTEXT.md): canonical handoff, scope, current state, and what was not recovered.
- [Mathematical foundations](docs/MATHEMATICS.md): chart conventions, splitting tests, the fixed-plane reduction, and construction families with derivations.
- [Experiments](docs/EXPERIMENTS.md): distinct learning tasks, data representations, leakage controls, baselines, metrics, and transfer.
- [Exact verification and data contract](docs/VERIFICATION.md): certificate requirements and machine-readable record design.
- [Roadmap and first milestone](docs/ROADMAP.md): concrete acceptance tests and proposed pilot sizes.
- [MM845 plan outline](docs/MM845_PLAN.md): assignment requirements and the two-page body structure.
- [Decisions and risks](docs/DECISIONS.md): accepted corrections, rejected shortcuts, and unresolved choices.
- [Sources](docs/REFERENCES.md): claim-to-source map and bibliography.
- [Preserved user brief](archive/USER_BRIEF.md): the supplied handoff text, not an export of the missing local chat.
- [Session log](SESSION_LOG.md) and [working rules](AGENTS.md): continuity and preservation protocol.

## Current status: specification, not implementation

Initial reconstruction: 8 September 2026. No generated research dataset, trained model, executable bundle-construction pipeline, Macaulay2 certificates, or numerical results are supplied by this initial documentation commit. The configuration in [configs/pilot.json](configs/pilot.json) is a proposed, unexecuted pilot. Source code, tests, and environment locks are the next milestone.

The missing local conversation has **not** been recovered. This reconstruction preserves the complete research content available in the supplied brief and the user's subsequent clarification, while explicitly marking new implementation proposals. It does not claim to reproduce unseen arguments or decisions.

The organising idea is:

1. Recover the unordered pair $\{a,b\}$ from algebraically gauge-obscured presentations on $\mathbf P^1$.
2. On $\mathbf P^2$, learn splitting versus indecomposability using exactly labelled examples, including split/nonsplit examples with identical Chern classes.
3. For a verified bundle $E$ on $\mathbf P^N$, test its restriction to a fixed linear plane. Splitting of that restriction is equivalent to splitting of $E$, but constructing a bundle on the plane does not establish that it extends.
4. Only after these stages work, use ML to prioritise audited higher-dimensional candidates for exact verification.

## Location and preservation

This is a dedicated project directory in [hqsaearp/MM845](https://github.com/hqsaearp/MM845), not a separate repository. It was chosen because the available GitHub connection can add files and commits but cannot create repositories. Existing course files are left unchanged. A standalone public project repository can be created later and this directory migrated with its history; do not delete this copy until the new remote is verified.

Git history makes committed work recoverable; it cannot guarantee against account deletion or preserve uncommitted conversations. At each substantive session, update the canonical documents and session log, commit, push, and verify the remote commit. Keep an independent local clone or backup as well. This initial publication does not configure an automatic backup or background synchronisation service.

For a new clone:

```sh
git clone https://github.com/hqsaearp/MM845.git
cd MM845/projects/hartshorne-ai
```

ChatGPT is for discussion and drafting; GitHub is the versioned record; VSCode with Python and Macaulay2 is for running experiments; Overleaf is an optional writing interface. The course repository's existing licence remains unchanged.
