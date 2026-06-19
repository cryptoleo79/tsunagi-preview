# Roadmap

TSUNAGI is in **steady state**. The roadmap is not a feature list — it is a list of proofs
reality has yet to provide. We do not manufacture these events; we wait for them and record the
evidence when they happen.

## The roadmap is the Reality Gap list

The next milestones are exactly the open gaps in [`REALITY-GAPS.md`](REALITY-GAPS.md), in risk
order:

1. **Spontaneous failure recovery** — a real, unplanned failure handled autonomously by Guardian. The keystone proof. (Only a controlled rehearsal exists today.)
2. **KES rotation** — perform the first key-evolution rotation.
3. **Crash-loop breaker activation** — observe the runaway-restart safety trip in production.
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
