## Agenxy

Sovereign open-source software. Every project runs on your own machine, with no
account, no external service, and no telemetry — no trusted third party, not
even us.

**[agenxy.org](https://agenxy.org)**

---

### [Dibs](https://github.com/Agenxy/dibs) &nbsp;·&nbsp; Go

Coordination for fleets of AI agents. Agents register, declare what they are
working on, and read what others have declared. Dibs reports overlapping work
and directory contention.

It does not assign, schedule, or spawn work, and it cannot drive an agent.
Claims are advisory: nothing prevents writing to a claimed directory. State is
an append-only hash-chained ledger, encrypted at rest, and the daemon runs
locally.

Released — v0.0.5 · [Tutorial](https://github.com/Agenxy/dibs/blob/main/docs/TUTORIAL.md) · [Philosophy](https://github.com/Agenxy/dibs/blob/main/PHILOSOPHY.md)

### [Remap](https://github.com/Agenxy/remap) &nbsp;·&nbsp; Rust

Name override and service routing. Maps a hostname to a network-accessible
address or service, and applies that mapping on enrolled devices. It does not
reserve a suffix and does not prevent shadowing public names.

Certificate, origin, redirect and content-security-policy failures stay visible:
Remap provides routing and does not pretend web applications are relocatable.

In progress — milestone M0

---

Apache 2.0. Works offline. No account, no licence key, no telemetry.

[Values](https://github.com/Agenxy/.github/blob/main/VALUES.md) ·
[Engineering standards](https://github.com/Agenxy/.github/blob/main/ENGINEERING.md) ·
[Contributing](https://github.com/Agenxy/.github/blob/main/CONTRIBUTING.md) ·
[Writing](https://agenxy.org/writing/)
