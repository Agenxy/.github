## Agenxy

Agenxy cultivates independent software. Every project runs on your own
machine, with no account, no external service, and no telemetry.

**[agenxy.org](https://agenxy.org)**

---

### [Dibs](https://github.com/Agenxy/dibs) &nbsp;·&nbsp; Go

Keeps your agents in the loop about each other, and out of each other's way.
They register, declare what they are working on, and read what others have
declared; Dibs reports overlapping work and directory contention.

It reports and never acts. Claims are advisory, so nothing prevents writing to
a claimed directory, and Dibs cannot assign work, schedule it, spawn it, or
drive an agent. State is an append-only hash-chained ledger, encrypted at rest,
so the board rebuilds exactly from its own history and a crash can neither
invent coordination state nor lose it. The daemon runs locally.

Released — v0.0.5 · [Tutorial](https://github.com/Agenxy/dibs/blob/main/docs/TUTORIAL.md) · [Philosophy](https://github.com/Agenxy/dibs/blob/main/PHILOSOPHY.md)

### [Remap](https://github.com/Agenxy/remap) &nbsp;·&nbsp; Rust

Name override and service routing. Maps a hostname to a network-accessible
address or service, and applies that mapping on enrolled devices. It does not
reserve a suffix, and it does not prevent shadowing public names.

Certificate, origin, redirect and content-security-policy failures stay
visible. Remap provides routing; it does not pretend web applications are
relocatable.

0.1.0 is the foundation release: domain model, exact and wildcard matching,
immutable registry snapshots, and an offline validation CLI. It does not yet
alter DNS, install a daemon, bind privileged ports, or modify trust. Those are
later milestones.

Released — v0.1.0 · [Milestones](https://github.com/Agenxy/remap/blob/main/docs/roadmap/MILESTONES.md)

### [Supgang](https://github.com/Agenxy/supgang) &nbsp;·&nbsp; Rust

Keeps track of your computers' changing public IP addresses without a
third-party service. Each computer gets a stable cryptographic identity, and
authorised members exchange freshly signed network addresses when those
addresses move.

No account, no public discovery service, no vendor relay, no required server.
Direct peer connections work today on macOS and Linux; automatic LAN
rendezvous, NAT traversal and user-owned relay mode are later milestones, so a
peer currently needs a reachable address.

Testing across networks · [Threat model](https://github.com/Agenxy/supgang/blob/main/docs/security/threat-model.md)

### [Quarters](https://github.com/Agenxy/quarters) &nbsp;·&nbsp; Rust

Gives a shell its own configuration, history and credentials, on the same
account. A space is a private folder; a process launched into it reads and
writes its configuration there while running as the same user, with the same
UID, groups and access to the filesystem.

It is not a VM, a container, an alternate Unix user, or a security boundary.
Filesystem confinement is not implemented, `sudo` escapes the space, and an
absolute path into your real home still reaches it. `doctor` reports Seatbelt
and Landlock as gaps rather than claiming protection that is not there.

Alpha — v0.1.0-alpha.2 · [Privacy](https://github.com/Agenxy/quarters/blob/main/PRIVACY.md)

---

Apache 2.0. Everything works offline. No account, no licence key, no telemetry.

[Values](https://github.com/Agenxy/.github/blob/main/VALUES.md) ·
[Engineering standards](https://github.com/Agenxy/.github/blob/main/ENGINEERING.md) ·
[Contributing](https://github.com/Agenxy/.github/blob/main/CONTRIBUTING.md) ·
[Writing](https://agenxy.org/writing/)
