# Download TSUNAGI (Preview)

> **Read [Before you download](#before-you-download) first.** TSUNAGI runs on the Cardano
> **Preview** testnet and is **experimental** software — not for mainnet.

---

## TSUNAGI Preview - Portable Linux x86-64

| | |
|---|---|
| **Version** | `v2026.07.24-preview-portable` |
| **Release date** | 2026-07-24 |
| **Binary** | `tsunagi-preview-linux-x86_64-portable` |
| **SHA256** | `4fb4015f61783930637e43d4d8603b207381479c735cc0170b6272b3fda10a69` |
| **Source** | `c8082152fe837e6dde045086631b09aa0058d788` |
| **Toolchain** | Zig 0.16.0 ReleaseSafe, baseline x86-64 / SSE2 |
| **Runtime** | glibc >= 2.34, `libsodium.so.23`, `liblmdb.so.0` |

This is the **recommended/default** download. The old
`tsunagi-node-v2026.06.18-preview-linux-x86_64` artifact is preserved but marked
**SUPERSEDED - host-native AVX-512 build**.

### Verify before you run

```
sha256sum tsunagi-preview-linux-x86_64-portable
# must print exactly:
# 4fb4015f61783930637e43d4d8603b207381479c735cc0170b6272b3fda10a69
```
or, with the published checksum file:
```
sha256sum -c tsunagi-preview-linux-x86_64-portable.sha256
```

### Run — observe-only (the safe first run)

Will not forge or broadcast. Recommended for evaluation:

```
chmod +x tsunagi-preview-linux-x86_64-portable
TSUNAGI_HOME="$HOME/tsunagi-home-preview" \
TSUNAGI_FORGE_ENABLE=0 \
./tsunagi-preview-linux-x86_64-portable run --net preview --lang en
```

> ⚠️ Always include `TSUNAGI_FORGE_ENABLE=0` for evaluation. With no `forge.env` the node defaults
> to live/forge mode (it still cannot forge without your own keys). Only omit it once you supply your
> own keys and intend to produce — see [`INSTALL.md`](INSTALL.md).

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
