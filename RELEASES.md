# Releases

Binaries are attached to GitHub Releases. Each release is a snapshot of evidence, not just code.

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
