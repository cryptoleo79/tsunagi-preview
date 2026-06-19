# The TSUNAGI Journey

How an independent block producer became a proven, self-supervising, evidence-backed system.
Every milestone is verifiable on-chain or by recorded result.

| phase | what happened |
|---|---|
| **First forge attempts** | Early forged blocks reached the network but were orphaned. Each orphan was root-caused and pinned with a regression test — the beginning of the incident catalogue. |
| **First canonical block** | The acceptance-blocking root causes were closed and TSUNAGI produced its first canonical Preview block, confirmed on-chain. |
| **Full mechanism proven** | First block through the complete designed path (park → contiguous walk → push → serve), then the first block of a new epoch — proving the epoch boundary live. |
| **P5 streak** | A run of consecutive elected slots, every one converted to a canonical block. |
| **P6 stabilization** | A subtle integer-overflow in the mux layer was fixed; zero panics since. |
| **Guardian** | An external supervisor introduced: crash detection, evidence capture, bounded auto-restart, a crash-loop breaker, and rollback *recommendation* — recommend-only, never acting beyond its mandate. |
| **Recovery rehearsal** | A controlled kill of the live node → detected → recovered in **3.8 s** with no human → the recovered node kept producing. Recovery proven end-to-end. |
| **SUP-001** | "Who watches the watcher?" closed: the supervisor itself is now supervised — `systemd → guardiand → node`. Verified kill→respawn in ~7 s. Blocks produced *after* the cutover turned configured supervision into production-verified supervision. |
| **Cockpit** | A read-only terminal NOC console: the whole organism on one screen, in ~5 seconds. |
| **Survival Dossier** | A continuity record answering "if everything vanished, what brings TSUNAGI back?" — identity, knowledge, rebuild, existential risks, survival scorecard. |
| **Identity verified** | The pool's cold key located and **cryptographically verified** to match the on-chain pool identity; identity recovery moved UNPROVEN → PARTIAL. |
| **Today** | 41 canonical blocks · streak 40 · 100% supervised conversion · 0 panics · STEADY. |

See live numbers in [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) and the open list in
[`REALITY-GAPS.md`](REALITY-GAPS.md).
