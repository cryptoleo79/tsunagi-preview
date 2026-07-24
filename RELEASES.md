# Releases

Binaries are attached to GitHub Releases. Each release is a snapshot of evidence, not just code.

## Current recommended download

`v2026.07.24-preview-portable`:

- `tsunagi-preview-linux-x86_64-portable`
- SHA-256: `4fb4015f61783930637e43d4d8603b207381479c735cc0170b6272b3fda10a69`
- Baseline x86-64 / SSE2, glibc >= 2.34, `libsodium.so.23`, `liblmdb.so.0`

The generic x86-64 binary from `v2026.06.18-preview` is preserved for provenance but is
**SUPERSEDED - host-native AVX-512 build**.

AVX2 remains optional and unpublished pending verification. aarch64 remains HOLD. Static musl
packaging is a separate future release-engineering milestone.

## What every release contains

- **Binary** (`tsunagi-node`) for Linux x86-64
- **SHA256** checksum (verify before running — see [`SECURITY.md`](SECURITY.md))
- **Cockpit** (`cockpit`, single stdlib-Python file)
- **Release notes** including:
  - canonical count, current streak, longest streak
  - supervised conversion + panics
  - evidence updates since the last release
  - reality-gap movements (PROVEN/PARTIAL/UNPROVEN changes)
  - a sample environment template (no secrets)

## Release notes template

```
TSUNAGI <version> (Preview)

binary:        tsunagi-node
sha256:        <checksum>
cockpit:       cockpit (stdlib python, zero install)

canonical:     <n>      streak: <n>   longest: <n>
conversion:    <l→f→c = %>            panics: <n>
supervisor:    systemd → guardiand → node

evidence updates:
  - <...>
reality-gap movements:
  - <gap>: <was> → <now>
```

## Verify

```
sha256sum tsunagi-node      # compare against the release's published SHA256
```

## Current status

See [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) and [`CHANGELOG.md`](CHANGELOG.md).
