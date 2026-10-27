<h1 align="center">TSUNAGI 繋</h1>
<p align="center"><b>An independent Cardano block producer that tells the truth about itself.</b></p>
<p align="center">Cardano <b>Preview</b> testnet · written in Zig · evidence-first operations</p>

<p align="center">
Historical Preview snapshot (2026-06-18) &nbsp;·&nbsp; Canonical <b>41</b> &nbsp;·&nbsp; Streak <b>40</b> &nbsp;·&nbsp; Longest <b>40</b> &nbsp;·&nbsp; Supervised conversion <b>100%</b> &nbsp;·&nbsp; Panics <b>0</b>
</p>
<p align="center">
<a href="DOWNLOAD.md">Download</a> ·
<a href="INSTALL.md">Install</a> ·
<a href="COCKPIT.md">Cockpit</a> ·
<a href="JOURNEY.md">Journey</a> ·
<a href="REALITY-GAPS.md">Reality Gaps</a> ·
<a href="PUBLIC_STATUS.md">Status</a>
</p>

> **⚠️ Preview only — experimental software. Not Mainnet or production.** The June producer and
> October follower are different executables with different instructions. For the historical
> June producer, use observe mode first (`TSUNAGI_FORGE_ENABLE=0`). The October follower is not
> qualified for block production. Never use Mainnet keys with either Preview release.

The following Cockpit transcript is a historical illustration, not live telemetry.

```
[HOME] [STEADY]   Canonical 41 · Streak 40 · KES 30d · Guardian ACTIVE        UTC  preview-host
── EXECUTIVE SUMMARY ───────────────────────────────────────────────────────────────────────
  CANONICAL  41       streak  40        longest  40       conversion  100%
  latest #4395367  slot 115153960  ep 1332  8859b6eb7b0382d6                         panics 0
── NEXT LEADER ─────────────────────────────────────────────────────────────────────────────
  none in current window · epoch 1332 · slots left in epoch
── GUARDIAN ────────────────────────────────────────────────────────────────────────────────
  ACTIVE    systemd → guardiand → node
── REALITY PROOFS ──────────────────────────────────────────────────────────────────────────
  [███████████████████████████████░░░░░░░░░░░░░] 13 / 18 proven
── TOP OPEN ITEMS ──────────────────────────────────────────────────────────────────────────
  1. Spontaneous Failure Recovery   2. Crash-Loop Breaker   3. KES Rotation
```
<p align="center"><i>Cockpit — the read-only operator console. More: <a href="COCKPIT.md">COCKPIT.md</a> · <a href="screenshots/">screenshots/</a></i></p>

---

## Truth first. Evidence first. Reality first.

The documentation records dated Preview observations and open gaps. Block-production claims and
operational rehearsals have different evidence sources; verify the underlying receipts and
current Preview chain data before treating historical claims as present state.

TSUNAGI is not a fork of `cardano-node`. It is an independent implementation of the producing
path — election, forge, propagation, acceptance — written from scratch in Zig, with
dated Preview testnet block-production evidence.

But the node is only half of it. The other half is an operational philosophy:

> **Reality over assumptions. Evidence over confidence. Memory over mythology.**

---

## What has it proven?

*The figures below are historical Preview observations reported in [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) for 2026-06-18. Check the cited receipts and current on-chain data before describing present operation.*

- **41 canonical blocks** produced and confirmed on-chain.
- **Streak 40 · longest streak 40 at that snapshot** — consecutive elected slots converted to canonical blocks.
- **100% supervised conversion** — all forges → canonical, **0 panics**, since the SUP-001 supervisor cutover.
- **Self-recovery proven** — the Guardian supervisor detected a killed node and recovered it in **3.8 s** with no human; the recovered node kept producing.
- **Supervised by `systemd → guardiand → node`** (SUP-001) — verified kill→respawn in ~7 s.

[`REALITY-GAPS.md`](REALITY-GAPS.md) contains a 31-block canonical production row that differs from the 41-block status snapshot. Keep both records visible; reconcile their dates and scopes from underlying receipts before asserting a chronology.

## What remained unproven in the 2026-06-18 record?

The dated [`REALITY-GAPS.md`](REALITY-GAPS.md) record listed these open Preview proofs. It does
not establish their status after 2026-06-18:

- ◯ **Spontaneous failure recovery** — a controlled rehearsal was recorded, but no unplanned
  failure recovery was documented by 2026-06-18.
- ◯ **Crash-loop breaker activation** · ◯ **KES rotation** · ◯ **Identity recovery drill** —
  listed as open at that snapshot.

Check later evidence before describing present gap status.

---

## Why is it different?

It isn't "because Zig." It's the whole organism:

| | |
|---|---|
| **Node** | makes blocks |
| **Guardian** | keeps it alive (supervises, recovers, never acts beyond its mandate) |
| **KINTSUGI** | remembers every failure as a catalogued, fixed, regression-tested incident |
| **Evidence** | every capability is classified PROVEN / PARTIAL / UNPROVEN |
| **Reality Gaps** | the unproven list is public and ranked by risk |
| **Cockpit** | a read-only terminal console that reveals all of it in one screen |

---

## Choose a Preview release

As checked on **2026-10-27**, GitHub marked the
[`v2026.10.05-preview-portable-x86_64` release](https://github.com/cryptoleo79/tsunagi-preview/releases/tag/v2026.10.05-preview-portable-x86_64)
as **Latest**. Its binary is `tsunagi-preview-v2026.10.05-linux-x86_64`, a portable Preview
**follower** qualified for the functions stated in that release. It is **not qualified there for
block production**. Download its `SHA256SUMS` and release-specific `INSTALL.md`; verify the binary
and follow those instructions. Recheck GitHub Releases for later versions.

```
# After downloading the October follower binary and its SHA256SUMS from that same release:
sha256sum -c SHA256SUMS
```

The **June 2026** producer binary and Cockpit transcript on this page are historical. Its
observe-only example uses a *different* executable and applies only to that June release; see
[`DOWNLOAD.md`](DOWNLOAD.md) and [`INSTALL.md`](INSTALL.md). Do not use the June command or
block-production claims as qualification for the October follower.

Full guide: [`DOWNLOAD.md`](DOWNLOAD.md) · [`INSTALL.md`](INSTALL.md) · [`COCKPIT.md`](COCKPIT.md).
*(Any block-production evaluation requires your own Preview keys — see `SECURITY.md`.)*

## Start here

1. **Understand it** → [`WHY-TSUNAGI.md`](WHY-TSUNAGI.md)
2. **Select a release** → [`DOWNLOAD.md`](DOWNLOAD.md) · [`RELEASES.md`](RELEASES.md)
3. **Read release-specific installation guidance** → [`INSTALL.md`](INSTALL.md)
4. **Explore the historical Cockpit** → [`COCKPIT.md`](COCKPIT.md)
5. **Verify the claims** → [`JOURNEY.md`](JOURNEY.md) · [`REALITY-GAPS.md`](REALITY-GAPS.md) · [`SURVIVAL.md`](SURVIVAL.md)
6. **Report findings** → open an issue (see [`FAQ.md`](FAQ.md) and [`SECURITY.md`](SECURITY.md))

---

## Screenshots

Three captured screens illustrate that historical state (see [`screenshots/`](screenshots/)):

1. **[Home](screenshots/cockpit-home.txt)** — what the Cockpit showed at the captured snapshot (state, production, guardian, reality proofs, footprint).
2. **[Production](screenshots/cockpit-production.txt)** — block production detail (KPIs, rates, forge pipeline, last-20 blocks).
3. **[Reality](screenshots/cockpit-reality.txt)** — what it has proven and what it hasn't (mission progress + ranked gaps).

---

<p align="center"><i>The node makes blocks. Guardian protects it. KINTSUGI remembers. Cockpit reveals it. Reality decides what comes next.</i></p>
