# Why TSUNAGI

*Not technical. Not protocol-focused. This is why the project exists.*

## The problem

In blockchain infrastructure, confidence is cheap and evidence is rare. Projects describe what
their software is *designed* to do. Dashboards show green. Documentation describes the happy
path. When something fails, the explanation arrives afterward — if at all.

TSUNAGI was built around the opposite instinct.

## Three principles

**Reality over assumptions.** A capability is not real because the code exists or the design is
sound. It is real when it has been *observed* working in production. Until then it is, explicitly,
unproven — and labelled as such.

**Evidence over confidence.** Every claim TSUNAGI makes is backed by something you can check: an
on-chain block hash, a confirmation count, a recorded recovery time, a kill-test result. If we
can't point to evidence, we don't claim it.

**Memory over mythology.** Every failure TSUNAGI has ever had is written down — root cause, the
fix, and a regression test that pins it so it can't silently return. The history is not folklore;
it is a catalogue.

## The organism

TSUNAGI is not just a node. It is six parts that reinforce each other:

- **Node** — an independent, from-scratch Cardano block producer (Zig). It makes blocks.
- **Guardian** — an external supervisor. It watches the node, captures evidence on failure, and
  recovers it — and it does *only* that. It never acts beyond its mandate.
- **KINTSUGI** — the memory. Named for the Japanese art of repairing pottery with gold: the
  breakage becomes part of the history, not something hidden. Every incident is catalogued with a
  detector, a recommendation, and a test.
- **Evidence** — every operational capability is classified PROVEN, PARTIAL, or UNPROVEN, with the
  reason.
- **Reality Gaps** — the unproven capabilities, ranked by risk, published openly.
- **Cockpit** — a read-only terminal console that shows the whole organism at a glance. It
  observes; it never acts.

## What makes it different

Not the language. Plenty of things are written in Zig.

What's different is that TSUNAGI **documents its own uncertainty as a feature.** Most projects
hide what they haven't proven. TSUNAGI ranks it, publishes it, and waits for reality to close
each gap — recording the proof when it arrives, and not a moment before.

The node makes blocks. Guardian protects it. KINTSUGI remembers. Cockpit reveals it.
Reality decides what comes next.
