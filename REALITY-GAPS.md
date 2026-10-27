# Reality Gaps

**Most projects hide what they haven't proven. TSUNAGI ranks it and publishes it.**

Every operational capability is classified:

- **PROVEN** — demonstrated on Preview, or by a recorded controlled rehearsal.
- **PARTIAL** — the mechanism exists and works, but the specific case hasn't been exercised.
- **UNPROVEN** — no qualifying Preview evidence in the dated record.

A capability is never promoted because it "should work." It is promoted only when evidence
exists — and the evidence is cited.

## Proven (13) in the June 2026 Preview record

The 31-block count below reflects the **2026-06-17** [`CHANGELOG.md`](CHANGELOG.md) snapshot. The
later **2026-06-18** [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) snapshot reports 41. This edit preserves
both historical rows; it did not independently query Koios or verify the underlying block receipts.

| capability | evidence |
|---|---|
| Canonical Production | 31 Preview blocks reported as Koios-confirmed in the 2026-06-17 snapshot |
| Full Propagation Mechanism | park → walk → push → serve, end-to-end |
| Epoch-Boundary Production | first block of a new epoch produced cleanly |
| Forge Gates | every block passed era / sigma / nonce / parent / opcert / self-verify |
| Guardian L1 Crash Detection | killed node detected instantly |
| Recovery Rehearsal | 3.8 s recovery, no human; recovered node kept producing |
| Supervisor Chain (SUP-001) | `systemd → guardiand → node`; kill→respawn ~7 s |
| Verified Rollback Chain | used across binary upgrades |
| Incident Catalogue + Signatures | every past failure catalogued with a fix + regression test |
| Operational Intelligence Loop | read-only, deterministic, recomputable |
| Public Evidence Exposure | this repository + the dated public status records |
| Acceptance Tracker | internal verdict cross-checked against the chain per block |
| Identity Existence | pool cold key verified to match the on-chain pool identity |

## Partial in the 2026-06-18 Preview record

| capability | why not yet proven |
|---|---|
| Identity Recovery | the cold key was reported to exist and match the pool; no restore-from-loss **drill** was recorded by 2026-06-18 |
| Host / operator-absence / total-rebuild survival | mechanisms were documented; no end-to-end exercise was recorded by 2026-06-18 |

## Unproven — ranked by risk (top open gaps)

This ranking reflects the **2026-06-18 Preview record**. It does not assert that the same gaps
remain open today.

| # | gap | why it matters |
|---|---|---|
| 1 | **Spontaneous failure recovery** | only a *controlled* rehearsal was recorded; no unplanned failure recovery was documented by 2026-06-18. This was the keystone open proof. |
| 2 | **KES rotation** | no key-evolution rotation was recorded by 2026-06-18. |
| 3 | **Crash-loop breaker activation** | no Preview activation was recorded by 2026-06-18. |
| 4 | **Identity recovery drill** | no restore of the reported cold key into a recovered environment was recorded by 2026-06-18. |
| 5 | **Detector-triggered intervention** | only a synthetic liveness-detector test was recorded by 2026-06-18. |

We do not simulate these to "close" them. We wait for reality, and record the proof when it
arrives.

## Movement (changes over time)

- **SUP-001** — "supervisor has no supervisor of itself" : UNPROVEN → **PROVEN** in the June 2026 record (`systemd` supervised Guardian at that snapshot).
- **Identity evidence** : UNPROVEN → **PARTIAL** in the 2026-06-17 identity update (cold key reported located and cryptographically verified to match the pool; restore drill and off-box redundancy were not verified at the snapshot).
