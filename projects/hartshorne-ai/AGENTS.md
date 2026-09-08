# Project-specific working instructions

These instructions apply inside `projects/hartshorne-ai/`.

## Begin a session

1. Read `CONTEXT.md`, `SESSION_LOG.md`, `docs/DECISIONS.md`, and `docs/ROADMAP.md`.
2. Check the repository branch, remote HEAD, working-tree changes, and any newer user instructions. Do not overwrite manual edits. Do not modify course materials outside this project directory without an explicit request.
3. State whether the work is a proposal, implementation, executed experiment, mathematical derivation, or verified result.

## Scientific rules

- Preserve ML degree recovery, splitting classification, and higher-dimensional transfer as distinct aims.
- Use the user's corrected mathematics and the proofs in `docs/MATHEMATICS.md`; flag a discovered error explicitly instead of silently rewriting history.
- No dataset, model, code, or successful certificate exists merely because its design is documented.
- Never label a failed bounded search “nonsplit”. Never label an invalid sheaf a vector bundle. Verify global local freeness before using a plane restriction to claim anything about a parent bundle.
- Keep certificate/generator witnesses out of model inputs and all equivalent presentations in a single partition.
- Do not use mail, unrelated personal materials, or adjacent research projects to invent missing context. The original local chat is not recovered.

## Record and preserve progress

1. Update the relevant canonical document and append a dated session entry: decisions, changed files, exact commands/checks run, outcomes, limitations, and next action.
2. Preserve the original handoff under `archive/`; add corrections in the working documents and decision log. Do not rewrite that source text to make it agree with later proposals.
3. Review the diff and tests. Commit only intended project changes and push through the authorised GitHub workflow; use fast-forward updates, never force-push shared history.
4. Verify the remote commit and the relevant file contents. Report the GitHub URL/commit and state explicitly if any change remains local or unpublished. Do not claim automatic backup or synchronisation is configured when it is not.
5. Keep credentials and private correspondence out of this public project. Do not publish large datasets/weights without a storage and reproducibility plan.

For substantial milestone snapshots, recommend an independent local clone or git bundle stored outside the same remote account. A remote commit protects against loss of this chat, not every possible loss of the account. Do not claim zero risk.

No research implementation is required merely to initialise this archive. The next approved technical direction is the M1 P1 generator/verifier and its acceptance tests.
