# Reality Gaps

**Most projects hide what they haven't proven. TSUNAGI ranks it and publishes it.**

Every operational capability is classified:

- **PROVEN** — demonstrated in production, or by a verified controlled rehearsal.
- **PARTIAL** — the mechanism exists and works, but the specific case hasn't been exercised.
- **UNPROVEN** — no production evidence yet.

A capability is never promoted because it "should work." It is promoted only when evidence
exists — and the evidence is cited.

## Proven (13)

| capability | evidence |
|---|---|
| Canonical Production | 31 Koios-confirmed blocks |
| Full Propagation Mechanism | park → walk → push → serve, end-to-end |
| Epoch-Boundary Production | first block of a new epoch produced cleanly |
| Forge Gates | every block passed era / sigma / nonce / parent / opcert / self-verify |
| Guardian L1 Crash Detection | killed node detected instantly |
| Recovery Rehearsal | 3.8 s recovery, no human; recovered node kept producing |
| Supervisor Chain (SUP-001) | `systemd → guardiand → node`; kill→respawn ~7 s |
| Verified Rollback Chain | used across binary upgrades |
| Incident Catalogue + Signatures | every past failure catalogued with a fix + regression test |
| Operational Intelligence Loop | read-only, deterministic, recomputable |
| Public Evidence Exposure | this repository + the live status surfaces |
| Acceptance Tracker | internal verdict cross-checked against the chain per block |
| Identity Existence | pool cold key verified to match the on-chain pool identity |

## Partial

| capability | why not yet proven |
|---|---|
| Identity Recovery | the cold key exists and is verified; a restore-from-loss **drill** hasn't been performed |
| Host / operator-absence / total-rebuild survival | mechanisms documented; not yet exercised end-to-end |

## Unproven — ranked by risk (top open gaps)

| # | gap | why it matters |
|---|---|---|
| 1 | **Spontaneous failure recovery** | only a *controlled* rehearsal exists; a real unplanned failure hasn't occurred. This is the keystone proof. |
| 2 | **KES rotation** | the key-evolution rotation has never been performed; first one is ahead. |
| 3 | **Crash-loop breaker activation** | the runaway-restart safety has never tripped in production. |
| 4 | **Identity recovery drill** | restoring the verified cold key into a recovered environment hasn't been exercised. |
| 5 | **Detector-triggered intervention** | the liveness detector has fired only on a synthetic test. |

We do not simulate these to "close" them. We wait for reality, and record the proof when it
arrives.

## Movement (changes over time)

- **SUP-001** — "supervisor has no supervisor of itself" : UNPROVEN → **PROVEN** (systemd now supervises Guardian).
- **Identity off-box backup** : UNPROVEN → **PARTIAL** (cold key located and cryptographically verified to match the pool; restore drill still pending).
