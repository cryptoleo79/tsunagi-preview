# Install TSUNAGI (Preview): choose the release first

As checked on **2026-10-27**, GitHub's **Latest** release was the
[`v2026.10.05-preview-portable-x86_64` follower](https://github.com/cryptoleo79/tsunagi-preview/releases/tag/v2026.10.05-preview-portable-x86_64),
with executable `tsunagi-preview-v2026.10.05-linux-x86_64`. Download its own `SHA256SUMS` and
attached `INSTALL.md`, verify the binary, and follow **that release's** instructions. That
artifact is not qualified for block production. The commands on this repository page below are
historical examples for the **different June 2026 producer binary** and must not be substituted
for the October follower's instructions. See [`DOWNLOAD.md`](DOWNLOAD.md) for exact assets.

> Both releases are for Cardano **Preview** evaluation, not Mainnet or production use.

## Historical June 2026 producer example

The remaining sections describe the
[`v2026.06.18-preview` release](https://github.com/cryptoleo79/tsunagi-preview/releases/tag/v2026.06.18-preview)
and its `tsunagi-node-v2026.06.18-preview-linux-x86_64` asset. They do not establish current
producer operation or qualify the October follower for forging.

## Requirements

- Linux x86-64.
- A reachable Cardano Preview relay/network connection.
- ~A few GB of disk for chain state.
- (For Cockpit) Python 3.8+ — standard library only, **nothing to pip install**.

## 1. Download

Download the **June** binary and `SHA256SUMS` from the June tag linked above. Its binary SHA-256
is `b93a60fe731cc381633fc1b8170b66da9e03032a0ca71569ecf2bdb8e2047dd9`.

```
# verify the download against the published checksum
sha256sum tsunagi-node-v2026.06.18-preview-linux-x86_64
# compare with the June release checksum above; they must match
```

## 2. Configure

- **Home directory:** TSUNAGI uses `TSUNAGI_HOME` (default `$HOME/tsunagi-home`) for state, logs,
  and config. It is created on first run.
- **Config file:** the node reads `$TSUNAGI_HOME/forge.env` (e.g. `~/tsunagi-home/forge.env`). If
  it is absent you'll see `CONFIG_NOT_FOUND` and the node starts with **defaults** (see the safety
  note under Run). The June release includes `forge.env.sample` — copy it to
  `$TSUNAGI_HOME/forge.env` and edit.
- **Genesis:** **bundled for Preview** (magic 2) — no separate download needed.
- **Keys:** you supply your **own** pool keys (cold / VRF / KES / opcert) via `forge.env`. TSUNAGI
  ships **no** keys; never commit keys anywhere. Block *production* requires them; you can run
  without them to **observe/sync** (it just won't forge valid blocks). See [`SECURITY.md`](SECURITY.md).

## 3. Run

**Observe-only — the safe first run** (recommended for evaluation; will not forge or broadcast):

```
TSUNAGI_FORGE_ENABLE=0 ./tsunagi-node-v2026.06.18-preview-linux-x86_64 run --net preview
```

> **Note on `--help`:** the binary's built-in `--help` shows `zig build run …` examples (the
> developer invocation). **Ignore those** — with the downloaded June binary use the command above.

> ⚠️ **Default mode is "live".** With no `forge.env` the node defaults to `MODE=live` /
> `FORGE=enabled` / broadcast on (it still cannot forge without your own keys). For evaluation,
> **always include `TSUNAGI_FORGE_ENABLE=0`** as above. Only run the bare
> `./tsunagi-node-v2026.06.18-preview-linux-x86_64 run --net preview` (live/forge mode) once you have supplied your own keys and
> intend to **produce** — that is the advanced/producer path, not the first run.

The June documentation described supervised operation under the Guardian supervisor in
[`docs/`](docs/) — `systemd → guardiand → node`. That historical arrangement is not a runtime
qualification for the October follower.

## 4. Watch it

```
cockpit                   # full-screen read-only NOC console
cockpit --once            # one-shot plain text snapshot (for scripts / no TTY)
```

The June release includes Cockpit as a separate stdlib-Python asset. See
[`COCKPIT.md`](COCKPIT.md).

## 5. Report findings

Open an issue with: what you ran, what you observed, the relevant Cockpit snapshot
(`cockpit --once`), and any block hashes. See [`FAQ.md`](FAQ.md).

---

*For the October follower, use its release-specific instructions and checksum.*
