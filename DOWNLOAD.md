# Download TSUNAGI (Preview)

> **Read [Before you download](#before-you-download) first.** TSUNAGI runs on the Cardano
> **Preview** testnet and is **experimental** software — not for mainnet.

---

## ⬇️ TSUNAGI Preview · Linux x86_64

| | |
|---|---|
| **Version** | `v2026.06.18-preview` |
| **Release date** | 2026-06-18 |
| **Binary** | `tsunagi-node-v2026.06.18-preview-linux-x86_64` (≈ 22.6 MB) |
| **SHA256** | `b93a60fe731cc381633fc1b8170b66da9e03032a0ca71569ecf2bdb8e2047dd9` |
| **Cockpit** | `cockpit` (single stdlib-Python file, zero install) |
| **Toolchain** | Zig 0.16.0 ReleaseSafe |

**Download:** the binary, `cockpit`, and `SHA256SUMS` are attached to the
[GitHub Release](RELEASES.md) for `v2026.06.18-preview`.

### Verify before you run

```
sha256sum tsunagi-node-v2026.06.18-preview-linux-x86_64
# must print exactly:
# b93a60fe731cc381633fc1b8170b66da9e03032a0ca71569ecf2bdb8e2047dd9
```
or, if you grabbed `SHA256SUMS`:
```
sha256sum -c SHA256SUMS
```

---

## State at this release (verifiable on Koios)

| metric | value |
|---|---|
| Canonical blocks | **41** |
| Current streak | **40** |
| Longest streak | **40** |
| Panics | **0** |
| Guardian | **ACTIVE** (`systemd → guardiand → node`) |
| Network | Cardano **Preview** testnet |

Live status: [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md). All figures are independently checkable on any
Preview explorer.

---

## Before you download

- **Preview network only.** This is the Cardano Preview *testnet*. It is **not** for mainnet.
- **Experimental software.** TSUNAGI is an independent, from-scratch block producer. Run it to
  evaluate and report findings, not to secure value.
- **Not production-ready.** Several survivability behaviors are explicitly **unproven** (below).
- **You supply your own keys.** TSUNAGI ships **no** keys. Generate your own pool keys and keep the
  cold key offline. See [`SECURITY.md`](SECURITY.md).

### What is proven (evidence-backed)
✓ Canonical block production (41 blocks) · ✓ the full propagation mechanism · ✓ epoch-boundary
production · ✓ in-node forge gates · ✓ Guardian crash recovery (rehearsal, 3.8 s) · ✓ the SUP-001
supervisor chain (respawn 7.08 s) · ✓ operational intelligence · ✓ public evidence exposure.

### What is still being investigated / unproven (we document this openly)
◯ **Spontaneous failure recovery** (only a controlled rehearsal so far) · ◯ crash-loop breaker
activation · ◯ KES rotation · ◯ identity recovery drill. Full ranking:
[`REALITY-GAPS.md`](REALITY-GAPS.md).

**Open question (honest):** a ~26 h production gap on 2026-06-17 (**INC-014**) recovered and is
classified **RECOVERED (pending root cause)**. Investigation ruled out the forward-schedule stall
and sigma drift as causes; the most evidence-consistent explanation is a genuinely sparse election
window. We publish the uncertainty rather than hide it.

---

## Next steps

1. **Verify** the SHA256 (above).
2. **Install & run** → [`INSTALL.md`](INSTALL.md) (target: running in under 5 minutes).
3. **Watch it** → run `cockpit` → [`COCKPIT.md`](COCKPIT.md). See [`screenshots/`](screenshots/).
4. **Report findings** → open an issue ([`FAQ.md`](FAQ.md) · [`SECURITY.md`](SECURITY.md)).
