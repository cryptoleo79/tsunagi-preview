# The TSUNAGI Journey

Historical Preview milestones recorded through the 2026-06-18 release. Block-production
observations and operational rehearsals have different evidence scopes; see the dated
[`CHANGELOG.md`](CHANGELOG.md) and [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) records. This page does not
establish current operation or Mainnet readiness.

| phase | what happened |
|---|---|
| **First forge attempts** | Early forged blocks reached the network but were orphaned. Each orphan was root-caused and pinned with a regression test — the beginning of the incident catalogue. |
| **First canonical block** | The acceptance-blocking root causes were closed and TSUNAGI produced its first canonical Preview block, confirmed on-chain. |
| **Full mechanism proven** | First block through the complete designed path (park → contiguous walk → push → serve), then the first block of a new epoch — proving the epoch boundary live. |
| **P5 streak** | A run of consecutive elected slots, every one converted to a canonical block. |
| **P6 stabilization** | A subtle integer-overflow in the mux layer was fixed; the June 2026 record reported zero panics after the fix through its snapshot. |
| **Guardian** | An external supervisor introduced: crash detection, evidence capture, bounded auto-restart, a crash-loop breaker, and rollback *recommendation* — recommend-only, never acting beyond its mandate. |
| **Recovery rehearsal** | A controlled kill of the live node → detected → recovered in **3.8 s** with no human → the recovered node kept producing. Recovery proven end-to-end. |
| **SUP-001** | The June 2026 record reports `systemd → guardiand → node`, a verified kill→respawn in ~7 s, and Preview blocks produced after the cutover. |
| **Cockpit** | A read-only terminal NOC console: the whole organism on one screen, in ~5 seconds. |
| **Survival Dossier** | A continuity record answering "if everything vanished, what brings TSUNAGI back?" — identity, knowledge, rebuild, existential risks, survival scorecard. |
| **Identity verified** | The pool's cold key located and **cryptographically verified** to match the on-chain pool identity; identity recovery moved UNPROVEN → PARTIAL. |
| **2026-06-18 status snapshot** | 41 canonical Preview blocks · streak 40 · 100% supervised conversion · 0 panics · STEADY, as reported in [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md). |

See the dated record in [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) and the open list in
[`REALITY-GAPS.md`](REALITY-GAPS.md).
