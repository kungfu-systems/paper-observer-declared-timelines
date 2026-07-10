# Observer-Declared Timelines

This repository tracks the LaTeX source for a research paper on
observer-declared timelines for real-world agent work.

Working title:

```text
Observer-Declared Timelines for Real-World Agent Work
```

The paper studies a design rule behind KFD-4: timeline views in multi-machine,
multi-agent, mixed-source systems should declare their observer, accepted
facts, projection policy, causal constraints, and degraded evidence state
instead of presenting a view from nowhere.

Publisher: Kungfu Origin Technology Limited.
Contact: Keren Dong <keren.dong@kungfu.link>.

## Repository Naming

This repository introduces the `paper-*` prefix for Kungfu research artifacts.
Use `paper-<short-subject>` for one paper or tightly scoped paper series. The
prefix names the role of the repository, not the current toolchain; LaTeX is an
implementation detail.

See [`docs/repository-naming.md`](docs/repository-naming.md).

## Layout

- [`paper/main.tex`](paper/main.tex): LaTeX entrypoint.
- [`paper/sections/`](paper/sections/): paper sections.
- [`paper/references.bib`](paper/references.bib): bibliography.
- [`docs/MAP.md`](docs/MAP.md): repository map.

## Build

CI builds the PDF through Buildchain's pinned LaTeX Docker toolchain declared
in [`.buildchain/buildchain.toml`](.buildchain/buildchain.toml). Buildchain also
writes the publication manifest, passport, archive registry, and source bundle.
On alpha and release channels, the dedicated paper release preset synthesizes
and publishes the npm package, records release evidence, and creates the GitHub
Release.

The package coordinate is:

```text
@kungfu-tech/paper-observer-declared-timelines
```

npm Trusted Publishing must be configured against this repository and
`.github/workflows/paper-release.yml`. The repository does not carry local
package-generation or publication transaction scripts; those mechanics remain
owned by Buildchain.

If a TeX toolchain is installed:

```sh
make pdf
```

Source-only checks:

```sh
make check
```

## Status

This is an initial draft repository. The argument is intentionally framed as a
design paper with an implementation and evaluation plan. Empirical claims must
be backed by future Kungfu implementation evidence before submission.
