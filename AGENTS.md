# AGENTS.md — layer-example

The example candies that opencharly/opencharly's `GRIEVANCES.md` imports. Everything is
`charly.yml` at the repository root: four candies and their `plan:` checks. There is no source
tree and no skill.

Canonical files:

- `charly.yml`: the `search-tools:`, `python-gobject:`, `agent-tools:` and `hello-web:`
  candies.
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

- These candies are quoted by `GRIEVANCES.md` in opencharly/opencharly. A change to a name,
  a package list, a file, a service or a check changes that document's examples. Land the change here first, then update
  the document and its `import:` release and digest.

## Landing

- PR-only, through the org-required `charly/pr-validator`. History lives in `CHANGELOG/`.
- The authoritative rulebook is the umbrella `AGENTS.md` in `opencharly/opencharly`. Do not
  restate its rules here.
