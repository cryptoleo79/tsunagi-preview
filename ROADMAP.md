# Roadmap

The **2026-06-18 Preview status snapshot** classified TSUNAGI as **STEADY**. This roadmap records
proofs still open at that snapshot. Later operational state requires later evidence.

## The roadmap is the Reality Gap list

At that date, the next milestones were the open gaps in [`REALITY-GAPS.md`](REALITY-GAPS.md), in
risk order:

1. **Spontaneous failure recovery** — a real, unplanned failure handled autonomously by Guardian. The keystone proof. (Only a controlled rehearsal was recorded as of 2026-06-18.)
2. **KES rotation** — perform the first key-evolution rotation.
3. **Crash-loop breaker activation** — observe the runaway-restart safety trip in Preview operation.
4. **Identity recovery drill** — restore the verified cold key into a recovered environment.
5. **Detector-triggered intervention** — the liveness detector firing on a real anomaly.

Plus: **long-duration uptime** — each additional period of `systemd → guardiand → node` without
incident strengthens the supervision evidence.

## What is deliberately NOT on the roadmap

No consensus/forge/networking changes. No new autonomy layers. No protocol expansion. The
architecture is ahead of the evidence; the work is to *earn the evidence*, not to widen the
architecture.

When a gap closes, it moves to PROVEN in [`REALITY-GAPS.md`](REALITY-GAPS.md) with its evidence —
and the roadmap gets shorter.
