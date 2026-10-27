# Survival

TSUNAGI doesn't just ask "does it make blocks?" It asks "if everything went wrong, what
survives, and what proves it?" This is a historical public summary of the Survival Dossier,
published in the [`CHANGELOG.md`](CHANGELOG.md) on 2026-06-16. The scorecard below reflects the
June 2026 Preview record through the 2026-06-18 release, including the 2026-06-17 identity update.
It does not describe current key custody, backup state, or operational readiness.

## The question

Recovering TSUNAGI means re-operating *the same pool* so its block history continues under the
same identity. Producing *a* block with *a* new pool is not recovery.

## Survival scorecard

Statuses are the recorded **2026-06-18 Preview snapshot** classifications. They are not a fresh
recovery drill or an independent check of off-box evidence custody.

| event | status | why |
|---|---|---|
| Node crash | **PROVEN** | Guardian detected a kill and recovered the node in 3.8 s, no human |
| Host crash (process level) | **PARTIAL** | supervisor respawn recorded (~7 s); no full host reboot recorded by 2026-06-18 |
| Operator absence | **PARTIAL** | auto-recovery recorded; push alerting was not documented at the snapshot |
| Evidence corruption | **PARTIAL** | records are recomputable and cross-checkable against the chain |
| Total rebuild | **PARTIAL** | rebuild sequence documented; no end-to-end run recorded by 2026-06-18 |
| Key loss | **PARTIAL** | cold key reported verified to match the pool; no restore drill recorded by 2026-06-18 |
| Disk / VPS loss | **UNPROVEN** | off-box redundancy of operational keys was not verified in the June record |
| KES expiry | **UNPROVEN** | no key rotation recorded by 2026-06-18 |

## What can be rebuilt vs what cannot

- **Classified as rebuildable in the June 2026 record:** the node binary, the supervisor, the
  public surfaces, and the operational intelligence. An end-to-end rebuild was not demonstrated.
- **Irreplaceable:** the pool identity (cold key). The 2026-06-17 identity record reported that
  the key existed and matched the on-chain pool identity; a restore-from-loss *drill* was pending.
  This page does not verify current custody or off-box redundancy.

## The honest line

The June 2026 record reports Preview block production and a controlled crash-recovery rehearsal.
End-to-end *continuity* after disk loss, host loss, or KES rotation was not demonstrated at the
2026-06-18 snapshot. Later state requires later evidence.
