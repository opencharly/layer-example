# AGENTS.md — layer-example

The example candy that opencharly/opencharly's `GRIEVANCES.md` imports. The whole candy is
`charly.yml` at the repository root: the `search-tools` package list and its `plan:` checks.
There is no source tree, no service and no skill.

Canonical files:

- `charly.yml`: the `search-tools:` candy.
- `.github/workflows/tag-on-merge.yml`: the CalVer tag and `CHANGELOG/` on merge.
- `README.md`: the user overview only, never agent guidance.

## Load these skills first (R0)

- `/charly-image:layer`: the candy authoring reference. Load it before editing any field or
  plan step.

## Build, validate, test

- Run `charly box validate` at the repository root. The manifest must parse and validate at
  the installed charly.
- The merge gate is the org-wide `charly/pr-validator` (required check `validate / validate`).

## Modify this repo

- This candy is quoted by `GRIEVANCES.md` §1 in opencharly/opencharly. A change to its name or
  its package list changes that document's example. Land the change here first, then update
  the document and its `import:` release and digest.

## Landing

- PR-only, through the org-required `charly/pr-validator`. History lives in `CHANGELOG/`.
- The authoritative rulebook is the umbrella `AGENTS.md` in `opencharly/opencharly`. Do not
  restate its rules here.
