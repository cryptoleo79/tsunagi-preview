# Security

## Scope

TSUNAGI runs on the Cardano **Preview** testnet and is evaluation software. Run it on Preview.

## Keys are yours, and only yours

- TSUNAGI **never ships keys** of any kind. You generate and supply your own pool keys
  (cold / VRF / KES) and operational certificate.
- **Never commit keys, certificates, counters, or seed material** to any repository.
- The cold signing key should be kept **offline / air-gapped**, not on the producing host.
- Treat your environment/config files as secret — they reference key paths.

## This repository contains no secrets

This public repository is documentation, evidence, and binaries only. It deliberately excludes:
private source, private infrastructure details, hostnames, IP addresses, credentials, keys,
operational certificates, and deployment specifics. Every release is scrubbed before publication.

## Reporting a vulnerability

If you find a security issue, please report it privately first rather than opening a public
issue. Include reproduction steps and impact. We'll acknowledge and work with you on disclosure
timing.

## Verifying a download

Every binary release publishes a **SHA256**. Always verify before running:

```
sha256sum tsunagi-node    # must match the published checksum
```
