# Survival

TSUNAGI doesn't just ask "does it make blocks?" It asks "if everything went wrong, what
survives, and what proves it?" This is the public summary of the Survival Dossier.

## The question

Recovering TSUNAGI means re-operating *the same pool* so its block history continues under the
same identity. Producing *a* block with *a* new pool is not recovery.

## Survival scorecard

| event | status | why |
|---|---|---|
| Node crash | **PROVEN** | Guardian detected a kill and recovered the node in 3.8 s, no human |
| Host crash (process level) | **PARTIAL** | supervisor respawn proven (~7 s); a full host reboot hasn't been exercised |
| Operator absence | **PARTIAL** | auto-recovery proven; there is no push alerting yet |
| Evidence corruption | **PARTIAL** | records are recomputable and cross-checkable against the chain |
| Total rebuild | **PARTIAL** | the rebuild sequence is documented and deterministic; never run end-to-end |
| Key loss | **PARTIAL** | the cold key exists and is verified to match the pool; a restore drill is pending |
| Disk / VPS loss | **UNPROVEN** | operational keys' off-box redundancy not yet verified |
| KES expiry | **UNPROVEN** | key rotation has never been performed |

## What can be rebuilt vs what cannot

- **Rebuildable from source + chain:** the node binary, the supervisor, the public surfaces, and
  the operational intelligence — all deterministic.
- **Irreplaceable:** the pool identity (cold key). It exists and is cryptographically verified to
  match the on-chain pool; the remaining work is a documented restore *drill*.

## The honest line

Block production is proven. Self-recovery from a crash is proven. End-to-end *continuity* — disk
loss, host loss, KES rotation — is documented but not yet exercised. We say so plainly, and we'll
record each proof when reality provides it.
