<h1 align="center">TSUNAGI 繋</h1>
<p align="center"><b>An independent Cardano block producer that tells the truth about itself.</b></p>
<p align="center">Cardano <b>Preview</b> testnet · written in Zig · evidence-first operations</p>

<p align="center">
<b>STATE: STEADY</b> &nbsp;·&nbsp; Canonical <b>41</b> &nbsp;·&nbsp; Streak <b>40</b> &nbsp;·&nbsp; Longest <b>40</b> &nbsp;·&nbsp; Conversion <b>100%</b> &nbsp;·&nbsp; Panics <b>0</b>
</p>
<p align="center">
<a href="DOWNLOAD.md">Download</a> ·
<a href="INSTALL.md">Install</a> ·
<a href="COCKPIT.md">Cockpit</a> ·
<a href="JOURNEY.md">Journey</a> ·
<a href="REALITY-GAPS.md">Reality Gaps</a> ·
<a href="PUBLIC_STATUS.md">Status</a>
</p>

> **⚠️ Preview only — experimental software. Not mainnet, not production.** This binary is for
> evaluation/testing on the Cardano **Preview** testnet. **Run observe mode first**
> (`TSUNAGI_FORGE_ENABLE=0`, see Quickstart). **Do not use real/mainnet keys** with it unless you
> know exactly what you are doing — block production is opt-in and requires your own Preview keys.

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

Most node projects tell you what they *should* do. TSUNAGI tells you what it has *actually
proven* — and, just as loudly, what it has **not**. Every claim in this repository links to
evidence you can verify yourself on-chain.

TSUNAGI is not a fork of `cardano-node`. It is an independent implementation of the producing
path — election, forge, propagation, acceptance — written from scratch in Zig, and proven in
production on the Preview testnet.

But the node is only half of it. The other half is an operational philosophy:

> **Reality over assumptions. Evidence over confidence. Memory over mythology.**

---

## What has it proven?

*(Live numbers in [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md); all verifiable on Koios/any Preview explorer.)*

- **41 canonical blocks** produced and confirmed on-chain.
- **Current streak 40 · longest streak 40** — consecutive elected slots converted to canonical blocks.
- **100% supervised conversion** — all forges → canonical, **0 panics**, since the SUP-001 supervisor cutover.
- **Self-recovery proven** — the Guardian supervisor detected a killed node and recovered it in **3.8 s** with no human; the recovered node kept producing.
- **Supervised by `systemd → guardiand → node`** (SUP-001) — verified kill→respawn in ~7 s.

## What has it NOT proven?

We document uncertainty instead of hiding it (see [`REALITY-GAPS.md`](REALITY-GAPS.md)):

- ◯ **Spontaneous failure recovery** — only a *controlled* rehearsal so far; a real unplanned failure hasn't happened yet.
- ◯ **Crash-loop breaker activation** · ◯ **KES rotation** · ◯ **Identity recovery drill**.

This honesty *is* the product.

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

## Quickstart (Preview)

```
# 1. Download the binary + SHA256SUMS from the latest Release, then verify:
sha256sum -c SHA256SUMS
# 2. Run OBSERVE-ONLY on Preview (safe for evaluation — will not forge or broadcast):
TSUNAGI_FORGE_ENABLE=0 ./tsunagi-node-v2026.06.18-preview-linux-x86_64 run --net preview
# 3. Watch it (read-only, zero install):
cockpit
```
> ⚠️ Include `TSUNAGI_FORGE_ENABLE=0` for evaluation. With no `forge.env` the node defaults to
> live/forge mode (it still cannot forge without your own keys, but observe mode is the intended
> first run). Only enable forging once you supply your own keys — see [`INSTALL.md`](INSTALL.md).

Full guide: [`DOWNLOAD.md`](DOWNLOAD.md) · [`INSTALL.md`](INSTALL.md) · [`COCKPIT.md`](COCKPIT.md).
*(Block production requires your own keys — see `INSTALL.md` / `SECURITY.md`.)*

## Start here

1. **Understand it** → [`WHY-TSUNAGI.md`](WHY-TSUNAGI.md)
2. **Install & run** → [`INSTALL.md`](INSTALL.md) *(target: running in under 5 minutes)*
3. **Watch it** → [`COCKPIT.md`](COCKPIT.md) — run `cockpit` and read the organism in 5 seconds
4. **Verify the claims** → [`JOURNEY.md`](JOURNEY.md) · [`REALITY-GAPS.md`](REALITY-GAPS.md) · [`SURVIVAL.md`](SURVIVAL.md)
5. **Report findings** → open an issue (see [`FAQ.md`](FAQ.md) and [`SECURITY.md`](SECURITY.md))

---

## Screenshots

Three screens tell the whole story (see [`screenshots/`](screenshots/)):

1. **[Home](screenshots/cockpit-home.txt)** — what TSUNAGI is doing right now (state, production, guardian, reality proofs, footprint).
2. **[Production](screenshots/cockpit-production.txt)** — block production detail (KPIs, rates, forge pipeline, last-20 blocks).
3. **[Reality](screenshots/cockpit-reality.txt)** — what it has proven and what it hasn't (mission progress + ranked gaps).

---

<p align="center"><i>The node makes blocks. Guardian protects it. KINTSUGI remembers. Cockpit reveals it. Reality decides what comes next.</i></p>
