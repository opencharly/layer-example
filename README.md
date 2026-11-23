# layer-example

The example candy the OpenCharly documentation imports.

[GRIEVANCES.md](https://github.com/opencharly/opencharly/blob/main/GRIEVANCES.md) shows how
a box reuses a candy instead of repeating its package list. Its examples import this
repository, so the candy they name is a real, released one rather than an illustration.

## What it provides

| Candy | Packages | Service, file, user |
|---|---|---|
| `search-tools` | `ripgrep`, `jq` | none |

## How to use it

Import the repository and require the candy:

```yaml
import:
    layer-example:
        repo: opencharly/layer-example
        release: <a release of this repository>
        digest: <its digest>

my-box:
    description: A CachyOS box with the example search tools.
    from: distro-cachyos.cachyos
    require:
        - layer-example.search-tools
```

## Layout

- `charly.yml`: the `search-tools` candy, with its package list and the checks that show
  both tools work.
- `.github/workflows/tag-on-merge.yml`: the CalVer tag and `CHANGELOG/` on merge.
- `README.md`: this overview.

## Related

- [`opencharly/opencharly`](https://github.com/opencharly/opencharly): the umbrella, whose
  `GRIEVANCES.md` uses this candy.
- [`opencharly/charly`](https://github.com/opencharly/charly): the charly CLI and image builder.
