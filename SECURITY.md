# Security

## Scope

TSUNAGI runs on the Cardano **Preview** testnet and is evaluation software. Run it on Preview.

## Keys are yours, and only yours

- TSUNAGI **never ships keys** of any kind. You generate and supply your own pool keys
  (cold / VRF / KES) and operational certificate.
- **Never commit keys, certificates, counters, or seed material** to any repository.
- The cold signing key should be kept **offline / air-gapped**, not on the producing host.
- Treat your environment/config files as secret — they reference key paths.

## Public-content boundary

This public repository is intended to contain documentation, evidence, and release material,
without private source, infrastructure details, credentials, keys, operational certificates, or
deployment specifics. Do not publish those materials. This documentation correction did not
independently audit all history or release assets for secrets.

## Reporting a vulnerability

If you find a security issue, please report it privately first rather than opening a public
issue. Include reproduction steps and impact. We'll acknowledge and work with you on disclosure
timing.

## Verifying a download

Download `SHA256SUMS` and **every file it lists** from the **same release tag** before using the
whole-manifest check. The October 2026 checksum file lists its follower executable only. The June
2026 checksum file lists its producer executable, `cockpit`, and `forge.env.sample`; all three
must be present for the command below to pass. The releases have different filenames, checksums,
and qualification scopes; see [`RELEASES.md`](RELEASES.md). Verify before running:

```
sha256sum --check SHA256SUMS
```

If you downloaded **only the executable**, run `sha256sum` on that exact filename and compare the
printed digest with the binary SHA-256 shown on its release page or in [`RELEASES.md`](RELEASES.md).
The whole-manifest command will report missing-file failures until every listed asset is present.
