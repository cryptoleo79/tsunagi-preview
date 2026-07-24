# Install TSUNAGI (Preview)

**Goal: a running binary in under 5 minutes.** No Docker. No Kubernetes. No enterprise setup.

> TSUNAGI runs on the Cardano **Preview** testnet. It is evaluation software — run it on Preview,
> not mainnet.

## Requirements

- Linux x86-64 with baseline SSE2 support.
- glibc 2.34 or newer.
- `libsodium.so.23` and `liblmdb.so.0` (`libsodium23` and `liblmdb0` on Debian/Ubuntu).
- A reachable Cardano Preview relay/network connection.
- ~A few GB of disk for chain state.
- (For Cockpit) Python 3.8+ — standard library only, **nothing to pip install**.

## 1. Download

Grab `tsunagi-preview-linux-x86_64-portable` and its `.sha256` file from the latest
[Release](RELEASES.md). The older generic x86-64 artifact is preserved for provenance but is
**SUPERSEDED - host-native AVX-512 build**.

```
sha256sum -c tsunagi-preview-linux-x86_64-portable.sha256
```

## 2. Configure

- **Home directory:** TSUNAGI uses `TSUNAGI_HOME` (default `$HOME/tsunagi-home`) for state, logs,
  and config. It is created on first run.
- **Config file:** the node reads `$TSUNAGI_HOME/forge.env` (e.g. `~/tsunagi-home/forge.env`). If
  it is absent you'll see `CONFIG_NOT_FOUND` and the node starts with **defaults** (see the safety
  note under Run). A sample `forge.env.sample` ships with each release — copy it to
  `$TSUNAGI_HOME/forge.env` and edit.
- **Genesis:** **bundled for Preview** (magic 2) — no separate download needed.
- **Keys:** you supply your **own** pool keys (cold / VRF / KES / opcert) via `forge.env`. TSUNAGI
  ships **no** keys; never commit keys anywhere. Block *production* requires them; you can run
  without them to **observe/sync** (it just won't forge valid blocks). See [`SECURITY.md`](SECURITY.md).

## 3. Run

**Observe-only — the safe first run** (recommended for evaluation; will not forge or broadcast):

```
TSUNAGI_HOME="$HOME/tsunagi-home-preview" \
TSUNAGI_FORGE_ENABLE=0 \
./tsunagi-preview-linux-x86_64-portable run --net preview --lang en
```

> **Note on `--help`:** the binary's built-in `--help` shows `zig build run …` examples (the
> developer invocation). **Ignore those** — with the downloaded binary use the command above.

> ⚠️ **Default mode is "live".** With no `forge.env` the node defaults to `MODE=live` /
> `FORGE=enabled` / broadcast on (it still cannot forge without your own keys). For evaluation,
> **always include `TSUNAGI_FORGE_ENABLE=0`** as above. Only run the bare
> `./tsunagi-node run --net preview` (live/forge mode) once you have supplied your own keys and
> intend to **produce** — that is the advanced/producer path, not the first run.

For supervised operation (recommended for producers), run it under the Guardian supervisor
described in [`docs/`](docs/) — `systemd → guardiand → node`. Guardian detects a crash, captures
evidence, and restarts the node automatically.

## 4. Watch it

```
cockpit                   # full-screen read-only NOC console
cockpit --once            # one-shot plain text snapshot (for scripts / no TTY)
```

Cockpit is a single stdlib-Python file — copy it anywhere and run it. No install. See
[`COCKPIT.md`](COCKPIT.md).

## 5. Report findings

Open an issue with: what you ran, what you observed, the relevant Cockpit snapshot
(`cockpit --once`), and any block hashes. See [`FAQ.md`](FAQ.md).

---

*If anything here takes longer than 5 minutes, that's a bug in this guide — please report it.*
