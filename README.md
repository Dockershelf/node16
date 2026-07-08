# node16

> **⚠️ ARCHIVED: This repository has been retired**
> 
> Node.js 16 reached End of Life and is no longer receiving updates.
> 
> - **No new builds** will be published
> - **Existing packages** remain available in the APT repository
> - **Security updates** are no longer provided
> - **For current versions**, see: https://github.com/Dockershelf/dockershelf-pipeline
> 
> Retired: 2026-07-07

Debian packaging for Node.js 16: monolithic `nodejs` replacement packages used by the [Dockershelf node-pipeline](../node-pipeline).

## Supported Debian suites

- `trixie`
- `unstable`

Packaging trees live under `debiandirs/<suite>/`. Changelog tracks:

- **mainline** — `changelogs/mainline/<suite>`
- **nightly** — `changelogs/nightly/<suite>`

## Build (from workspace)

Clone or seed this repo as a sibling of `node-pipeline/`, then from `node-pipeline/`:

```bash
make materialize NODE=16 DIST=trixie
make build NODE=16
```

See the [operations manual](https://github.com/Dockershelf/node-pipeline/blob/main/docs/operations.md) for new majors, version bumps, and new suites.

## Layout

| Path | Purpose |
|------|---------|
| `node/` | Upstream Node.js git submodule (`v16.x` branch) |
| `patches/` | Quilt series (usually empty for monolithic builds) |
| `debiandirs/` | Per-suite Debian packaging (`trixie`, `unstable`) |
| `changelogs/` | `mainline` and `nightly` dch history per suite |
