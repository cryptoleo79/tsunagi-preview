# FAQ

**What is TSUNAGI?**
An independent Cardano block producer written in Zig, running on the Preview testnet — plus a
supervisor (Guardian), a memory of every failure (KINTSUGI), and a read-only operator console
(Cockpit). It is built around evidence: it documents what it has proven and what it hasn't.

**Is it open source?**
This is the public **testing/release** repository — documentation, evidence, and binaries for
evaluation on Preview. It is not the private development source tree. Licensing: see
[`LICENSE`](LICENSE).

**Is it production-ready?**
It is proven on **Preview**: 41 canonical blocks, 100% supervised conversion, 0 panics. It is
**not** presented as mainnet-ready. Several survivability behaviors are still UNPROVEN — see
[`REALITY-GAPS.md`](REALITY-GAPS.md). We'd rather you know that than not.

**How many blocks has it produced?**
41 canonical blocks (current streak 40, longest 40) as of the latest status. Live figures:
[`PUBLIC_STATUS.md`](PUBLIC_STATUS.md). All verifiable on Koios / any Preview explorer.

**What is Guardian?**
An external supervisor for the node. It detects crashes, captures an evidence package, and
restarts the node — recovery rehearsed at 3.8 s with no human. It is itself supervised by systemd
(SUP-001). It only supervises and recovers; it never acts beyond that mandate.

**What is KINTSUGI?**
The system's memory. Every failure TSUNAGI has had is catalogued with a root cause, a fix, and a
regression test. Named for the art of repairing pottery with gold — the breakage becomes part of
the recorded history, not something hidden.

**What is Cockpit?**
A read-only, zero-dependency terminal console (stdlib Python). Run `cockpit` and understand the
whole system in ~5 seconds: production, leader schedule, Guardian, reality proofs, KES, events.
It observes; it never acts. See [`COCKPIT.md`](COCKPIT.md).

**What is a Reality Gap?**
A capability that isn't yet proven by evidence. TSUNAGI ranks its gaps by risk and publishes
them, instead of hiding uncertainty. See [`REALITY-GAPS.md`](REALITY-GAPS.md).

**Why Zig?**
Control and simplicity: explicit memory behavior, small static binaries, no heavy runtime. But
the language isn't the point — the evidence discipline is. (See [`WHY-TSUNAGI.md`](WHY-TSUNAGI.md).)

**How do I report a finding?**
Open an issue with what you ran, what you observed, a `cockpit --once` snapshot, and any block
hashes. Security-sensitive reports: see [`SECURITY.md`](SECURITY.md).
