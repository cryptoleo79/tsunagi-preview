# Install TSUNAGI (Preview)

**Goal: a running binary in under 5 minutes.** No Docker. No Kubernetes. No enterprise setup.

> TSUNAGI runs on the Cardano **Preview** testnet. It is evaluation software — run it on Preview,
> not mainnet.

## Requirements

- Linux x86-64.
- A reachable Cardano Preview relay/network connection.
- ~A few GB of disk for chain state.
- (For Cockpit) Python 3.8+ — standard library only, **nothing to pip install**.

## 1. Download

Grab the latest binary from the [Releases](RELEASES.md) page (each release lists its **SHA256**).

```
# verify the download against the published checksum
sha256sum tsunagi-node
# compare with the SHA256 in the release notes — they must match
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

```
./tsunagi-node run --net preview      # the correct command for the Preview testnet
```

> **Note on `--help`:** the binary's built-in `--help` shows `zig build run …` examples (the
> developer invocation). **Ignore those** — with the downloaded binary just run
> `./tsunagi-node run --net preview` as above.

> ⚠️ **Safety — default mode is "live".** With no `forge.env`, the node defaults to
> `MODE=live` / `FORGE=enabled` / broadcast on. Without keys it cannot forge valid blocks, but if
> you only want to **observe/evaluate**, run with forging disabled, e.g.:
> ```
> TSUNAGI_FORGE_ENABLE=0 ./tsunagi-node run --net preview
> ```
> Only enable live forging once you have supplied your own keys and intend to produce.

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
