# releases/

Binary releases are attached to GitHub Releases (not committed to the repo tree).

Each release provides:
- `tsunagi-node` (Linux x86-64) + its **SHA256**
- `cockpit` (single stdlib-Python file, zero install)
- a sample environment template (no secrets)
- release notes (canonical count, streaks, conversion, evidence + reality-gap movements)

Verify every download:

```
sha256sum tsunagi-node    # must match the published checksum
```

See [`../RELEASES.md`](../RELEASES.md) and [`../SECURITY.md`](../SECURITY.md).
