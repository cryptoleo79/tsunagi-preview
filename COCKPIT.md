# Cockpit — the operator console

Cockpit is a **read-only** full-screen terminal console. It aggregates the node's existing
telemetry and evidence into one screen so an operator can understand TSUNAGI in ~5 seconds.

> **Cockpit observes. It never acts.** No controls, no restart buttons, no writes, no
> remediation. It is an instrument panel, not an autopilot.

Zero dependencies: a single Python file using only the standard library (`curses`). Nothing to
install.

```
cockpit            # full-screen TUI
cockpit --once     # one plain-text snapshot (non-TTY / scripts)
```

## The persistent status bar

Always visible at the top, on every page:

```
[HOME] [STEADY]   Canonical 41 · Streak 40 · KES 30d · Guardian ACTIVE      UTC  preview-host
```

`[PAGE]` shows where you are; `[STATE]` is STEADY / WARN / CRITICAL.

## Pages

| key | page | shows |
|---|---|---|
| `h` / `0` | **Home** | executive summary: state, canonical, streaks, conversion, next leader, guardian, reality-proofs progress, top open gaps, latest events |
| `1` | **Production** | KPIs, forge pipeline, sparklines (canonical growth, blocks/day, inter-block gap, acceptance %), last 20 blocks |
| `2` | **Guardian** | supervisor tree, state, L2, incident history |
| `3` | **KINTSUGI** | incident / signature / replay counts, latest classification, intelligence scorecard |
| `4` | **Reality** | mission progress bar + every proof (✓/◯) + the ranked gap tracker |
| `5` | **Acceptance** | every canonical block: height, slot, hash, binary, supervisor state |
| `6` | **Timeline** | chronological milestones |
| `7` | **KES** | countdown, progress bar, thresholds, rotation status |
| `8` | **Survivability** | identity / knowledge / host / operator / rebuild status lights |

## Keyboard shortcuts

```
h / 0   Home              e   jump: Events
1       Production         l   jump: Leader
2       Guardian          p   jump: Proofs
3       KINTSUGI          t   jump: Timeline
4       Reality           F   Forge history
5       Acceptance        G   Guardian history
6       Timeline          K   KES history
7       KES               r   Refresh now
8       Survivability     q / ESC  Quit
?       Help
```

## Forge pipeline

The pipeline panel shows the last result as a chain:

```
✓ Leader → ✓ Forge → ✓ Promote → ✓ Canonical
```

If a stage fails, its mark turns to `✗` so you see *exactly* where it broke.

## Sparklines

Terminal-native ASCII (`▁▂▃▄▅▆▇█`), 40–60 columns: canonical growth, blocks/day, inter-block gap,
acceptance %.

## Screenshots

See [`screenshots/`](screenshots/): Home, Production, Guardian, Acceptance, Timeline, Reality.

---

*Graceful by design: any panel whose feed is missing on a given host shows `—` rather than
failing. Cockpit runs identically on a producer and on an observer host.*
