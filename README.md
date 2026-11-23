# layer-example

The example candies the OpenCharly documentation imports.

[GRIEVANCES.md](https://github.com/opencharly/opencharly/blob/main/GRIEVANCES.md) builds one
project step by step, and every candy it uses comes from this repository, so the candies it
names are real, released ones rather than illustrations.

## What it provides

| Candy | Packages | Service, file, user |
|---|---|---|
| `search-tools` | `ripgrep`, `jq` | none |
| `python-gobject` | the GObject bindings for the system Python, named per distribution family | none |
| `agent-tools` | `podman`, `qemu-base`, `libvirt` (Arch family) | none |
| `hello-web` | the system Python | two files under `/srv/hello`, served by the `hello-web` service on port 8080 |

## How to use it

`hello-web` runs a service, so a container needs its init. Until
[opencharly/charly#764](https://github.com/opencharly/charly/issues/764) makes charly fetch that
init by itself, a box composing `hello-web` also composes
`@github.com/opencharly/layer-supervisord`.

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

- `charly.yml`: the four candies (`search-tools`, `python-gobject`, `agent-tools` and
  `hello-web`), each with the checks that show it works.
- `.github/workflows/tag-on-merge.yml`: the CalVer tag and `CHANGELOG/` on merge.
- `README.md`: this overview.

## Related

- [`opencharly/opencharly`](https://github.com/opencharly/opencharly): the umbrella, whose
  `GRIEVANCES.md` uses these candies.
- [`opencharly/charly`](https://github.com/opencharly/charly): the charly CLI and image builder.
