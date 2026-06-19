# Changelog

All notable, evidence-backed changes. Newest first. Figures verifiable on Koios / Preview explorers.

## 2026-06-18 — Preview release v2026.06.18-preview
- First public Preview release: binary + cockpit + SHA256, download page, clean-room install validated.
- Status: 41 canonical · streak 40 · longest 40 · conversion 100% · 0 panics.
- INC-014 (2026-06-17 drought) RECOVERED (pending root cause); forward-scan stall and sigma drift ruled out.

## 2026-06-17 — STEADY STATE
- Cockpit v5: HOME page (default), persistent status bar, pages Home/Production/Guardian/KINTSUGI/Reality/Acceptance/Timeline/KES/Survivability, larger labeled sparklines, jump keys.
- Identity Recovery: UNPROVEN → **PARTIAL** — cold key located and cryptographically verified to match the on-chain pool identity (restore drill still pending).
- Status: 31 canonical · streak 30 · longest 30 · conversion 100% · 0 panics.

## 2026-06-16 — Survivability + SUP-001
- SUP-001: supervisor chain hardened to `systemd → guardiand → node`; kill→respawn ~7 s verified. Supervisor-orphan gap UNPROVEN → **PROVEN**.
- Survival Dossier published (identity, knowledge, rebuild, existential risks, survival scorecard).
- Blocks #28–#31 produced *after* the cutover = production-verified supervision.
- Cockpit (terminal NOC console) introduced.

## 2026-06-14 — Guardian
- Guardian L1 live: crash detection, evidence capture, bounded auto-restart, crash-loop breaker, rollback recommendation.
- Recovery rehearsal: 3.8 s recovery, no human; recovered node kept producing.

## 2026-06-13 — P6
- Fixed a mux integer-overflow; zero panics since.

## 2026-06-12 — P5 streak
- Consecutive elected slots all converted to canonical blocks; first block of a new epoch.

## 2026-06-09 — First canonical block
- First canonical Preview block, confirmed on-chain.
