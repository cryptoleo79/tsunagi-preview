# FAQ

**What is TSUNAGI?**
An experimental independent Cardano Preview testnet block producer written in Zig — plus a
supervisor (Guardian), a memory of every failure (KINTSUGI), and a read-only operator console
(Cockpit). It is built around evidence: it documents what it has proven and what it hasn't.

**Is it open source?**
This is the public **testing/release** repository — documentation, evidence, and binaries for
evaluation on Preview. It is not the private development source tree. Licensing: see
[`LICENSE`](LICENSE).

**Is it production-ready?**
The **2026-06-18 Preview snapshot** reports 41 canonical blocks, 100% supervised conversion,
and 0 panics in its stated scope. It does not establish current operation, full node validation,
or Mainnet readiness. Several survivability behaviors were still UNPROVEN — see
[`REALITY-GAPS.md`](REALITY-GAPS.md). We'd rather you know that than not.

**How many blocks has it produced?**
The [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) snapshot dated **2026-06-18** reports 41 canonical
Preview blocks (streak 40, longest 40 at that snapshot). The earlier
[`CHANGELOG.md`](CHANGELOG.md) records 31 on 2026-06-17. These historical records do not report
the current chain state; check underlying receipts and current Preview chain data for updates.

**What is Guardian?**
An external supervisor for the node. It detects crashes, captures an evidence package, and
restarts the node — recovery rehearsed at 3.8 s with no human. It is itself supervised by systemd
(SUP-001). It only supervises and recovers; it never acts beyond that mandate.

**What is KINTSUGI?**
The system's memory. Every failure TSUNAGI has had is catalogued with a root cause, a fix, and a
regression test. Named for the art of repairing pottery with gold — the breakage becomes part of
the recorded history, not something hidden.

**What is Cockpit?**
The June 2026 producer release included a read-only, stdlib-Python terminal console for its
historical production, leader, Guardian, reality-proof, KES, and event records. It observes; it
never acts. The October 2026 follower release did not list Cockpit as an asset. See
[`COCKPIT.md`](COCKPIT.md).

**What is a Reality Gap?**
A capability that isn't yet proven by evidence. TSUNAGI ranks its gaps by risk and publishes
them, instead of hiding uncertainty. See [`REALITY-GAPS.md`](REALITY-GAPS.md).

**Why Zig?**
Control and simplicity: explicit memory behavior, small static binaries, no heavy runtime. But
the language isn't the point — the evidence discipline is. (See [`WHY-TSUNAGI.md`](WHY-TSUNAGI.md).)

**How do I report a finding?**
Open an issue with what you ran, what you observed, and any block hashes. If you used the June
producer and its Cockpit asset, a `cockpit --once` snapshot may help. Security-sensitive reports:
see [`SECURITY.md`](SECURITY.md).
