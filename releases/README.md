# releases/

Binary releases are attached to GitHub Releases (not committed to the repo tree).

Each release provides:
- `tsunagi-preview-linux-x86_64-portable` (baseline x86-64 / SSE2) + its **SHA256**
- `cockpit` (single stdlib-Python file, zero install)
- a sample environment template (no secrets)
- release notes (canonical count, streaks, conversion, evidence + reality-gap movements)

Verify every download:

```
sha256sum -c tsunagi-preview-linux-x86_64-portable.sha256
```

See [`../RELEASES.md`](../RELEASES.md) and [`../SECURITY.md`](../SECURITY.md).
