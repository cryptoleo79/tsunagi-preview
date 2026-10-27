# Download TSUNAGI (Preview)

> **Read [Before you download](#before-you-download) first.** TSUNAGI runs on the Cardano
> **Preview** testnet and is **experimental** software — not for mainnet.

---

## GitHub Latest at the 2026-10-27 check: October portable follower

The [October 2026 Preview release](https://github.com/cryptoleo79/tsunagi-preview/releases/tag/v2026.10.05-preview-portable-x86_64)
was marked **Latest** when this page was revised. Its executable is a **follower**, not a
block-producer qualification. It is a dynamically linked Linux x86-64 build requiring glibc 2.34
or newer, `liblmdb.so.0`, and `libsodium.so.23`. Check the release page for later versions and
its exact qualification boundary.

| | |
|---|---|
| **Tag** | `v2026.10.05-preview-portable-x86_64` |
| **Binary** | `tsunagi-preview-v2026.10.05-linux-x86_64` |
| **Binary SHA-256** | `4919985711adbf8f59b07839752e605ac3d98d1df35a42f5f93ab2ff3985e08e` |
| **Companion assets** | `SHA256SUMS`, `PROVENANCE-MANIFEST.md`, release-specific `INSTALL.md` |

Download all files from the **same October release**, then verify with
`sha256sum --check SHA256SUMS` and follow that release's attached `INSTALL.md`. The June producer
command below does **not** apply to the October follower.

## Historical June 2026 Preview producer release

The following binary, checksum, Cockpit asset, and instructions belong only to the
[`v2026.06.18-preview` release](https://github.com/cryptoleo79/tsunagi-preview/releases/tag/v2026.06.18-preview).
They describe the 2026-06-18 evidence snapshot and are not the GitHub Latest download.

| | |
|---|---|
| **Version** | `v2026.06.18-preview` |
| **Status snapshot / tag date** | 2026-06-18 |
| **GitHub release published (UTC)** | 2026-06-19 01:19:50 |
| **Binary** | `tsunagi-node-v2026.06.18-preview-linux-x86_64` (≈ 22.6 MB) |
| **SHA256** | `b93a60fe731cc381633fc1b8170b66da9e03032a0ca71569ecf2bdb8e2047dd9` |
| **Cockpit** | `cockpit` (single stdlib-Python file, zero install) |
| **Toolchain** | Zig 0.16.0 ReleaseSafe |

**Historical download:** the June release attaches the binary, `cockpit`, `forge.env.sample`, and
`SHA256SUMS`. Its checksum file lists **all three** non-checksum assets. Download every listed file
from that same tag before running the full checksum check below. If you only need to verify the
binary, use the single-file hash comparison shown first.

### Verify the June binary before you run

```
sha256sum tsunagi-node-v2026.06.18-preview-linux-x86_64
# must print exactly:
# b93a60fe731cc381633fc1b8170b66da9e03032a0ca71569ecf2bdb8e2047dd9
```
To check the **whole June manifest**, first place the June binary, `cockpit`, and
`forge.env.sample` beside the June `SHA256SUMS`, then run:
```
sha256sum -c SHA256SUMS
```

### June producer binary: observe-only example

The June release instructions describe this as observe-only. This example is **not** an October
follower command:

```
chmod +x tsunagi-node-v2026.06.18-preview-linux-x86_64
TSUNAGI_FORGE_ENABLE=0 ./tsunagi-node-v2026.06.18-preview-linux-x86_64 run --net preview
```

> ⚠️ Always include `TSUNAGI_FORGE_ENABLE=0` for evaluation. With no `forge.env` the node defaults
> to live/forge mode (it still cannot forge without your own keys). Only omit it once you supply your
> own keys and intend to produce — see [`INSTALL.md`](INSTALL.md).

---

## Reported Preview state at the 2026-06-18 status snapshot

| metric | value |
|---|---|
| Canonical blocks | **41** |
| Streak at release | **40** |
| Longest streak | **40** |
| Panics | **0** |
| Guardian at release | **ACTIVE** (`systemd → guardiand → node`) |
| Network | Cardano **Preview** testnet |

These are historical status figures from [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md), not live
telemetry. Check the cited records and current Preview chain data before describing present
operation.

---

## Before you download

- **Preview network only.** This is the Cardano Preview *testnet*. It is **not** for mainnet.
- **Experimental software.** TSUNAGI is an independent, from-scratch block producer. Run it to
  evaluate and report findings, not to secure value.
- **Not production-qualified.** The October release explicitly excludes production-grade use;
  the June record lists survivability gaps open at its 2026-06-18 snapshot (below).
- **June producer keys are yours.** The June release ships no keys. If evaluating its producer
  path, generate your own Preview pool keys and keep the cold key offline. The October follower
  release is not qualified for block production. See [`SECURITY.md`](SECURITY.md).

### What the 2026-06-18 release records as proven on Preview
✓ Canonical block production (41 blocks) · ✓ the full propagation mechanism · ✓ epoch-boundary
production · ✓ in-node forge gates · ✓ Guardian crash recovery (rehearsal, 3.8 s) · ✓ the SUP-001
supervisor chain (respawn 7.08 s) · ✓ operational intelligence · ✓ public evidence exposure.

### Open gaps reported at the 2026-06-18 snapshot
◯ **Spontaneous failure recovery** (only a controlled rehearsal was recorded by that date) ·
◯ crash-loop breaker activation · ◯ KES rotation · ◯ identity recovery drill. This is a historical
ranking; later status requires later evidence. Full dated record:
[`REALITY-GAPS.md`](REALITY-GAPS.md).

**Open question in the June release record:** a ~26 h Preview block-production gap on 2026-06-17
(**INC-014**) was classified **RECOVERED (pending root cause)**. That release reported that its
investigation ruled out the forward-schedule stall and sigma drift, and considered a sparse
election window the most evidence-consistent explanation. This page does not establish any later
root-cause resolution.

---

## Next steps for the historical June release

1. **Verify** the SHA256 (above).
2. **Read the June example** → [`INSTALL.md`](INSTALL.md); use the October release's attached
   `INSTALL.md` for the October follower.
3. **Watch it** → run `cockpit` → [`COCKPIT.md`](COCKPIT.md). See [`screenshots/`](screenshots/).
4. **Report findings** → open an issue ([`FAQ.md`](FAQ.md) · [`SECURITY.md`](SECURITY.md)).
