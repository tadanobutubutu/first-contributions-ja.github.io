---
name: merge-main-into-feature-branch
description: Workflow command scaffold for merge-main-into-feature-branch in first-contributions-ja.github.io.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /merge-main-into-feature-branch

Use this workflow when working on **merge-main-into-feature-branch** in `first-contributions-ja.github.io`.

## Goal

Merges the latest changes from main into a feature or topic branch, resolving conflicts if necessary.

## Common Files

- `package-lock.json`
- `package.json`
- `.github/workflows/jaipilot-generate.yml`
- `Contributors.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Merge main into the feature branch
- Resolve any conflicts
- Commit the merge, updating files as needed

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.