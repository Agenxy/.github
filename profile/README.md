## Agenxy

**Agency**: the ability to make decisions and act independently. That is the
thing every project here is built toward, whatever else they have in common,
which is often very little.

Software should hand you the information and the controls, then get out of the
way. It should not decide on your behalf what you are allowed to want, obscure
what it is doing, report on you to somebody else, or stop working because a
licence server had an opinion. Those are not separate complaints. They are all
the same one: someone else holding a decision that was yours.

The practical form of it is **sovereignty**. Your machine is yours and our
software runs there as a guest: no account, no licence server, works with the
network unplugged, data on your disk in a form you can read without us, and
**nothing we can change from our side after you install it.** No forced update,
no remote kill switch, no phone-home. An update happens because you chose it.

Lanes is the worked example. Its ledger is append-only JSONL you can read in any
text editor; the only encrypted parts are private message bodies, under a key
that lives beside them and never leaves the machine. Every network call it makes
goes to 127.0.0.1.

Everything here is Apache 2.0, and we do not log what you do with it. If one of
our servers were breached tomorrow, nobody should need to change a password,
because there is nothing held about you to find.

### [Lanes](https://github.com/agenxy/lanes)

The first one. Coordination and situational awareness for the AI agents
running on your machine, across whatever projects they have open. Each agent
registers a lane, declares what it is pursuing, and is told immediately if
someone else is already pursuing it. Agents exchange typed mail with receipts and
deadlines, and place advisory claims on the few things that genuinely need
exclusivity.

Lanes reports; it never acts. No agent can act on another through it, and the
worst message you can receive is one you may decline. An agent gets the facts
and decides for itself, which is the same principle applied one level down.

```sh
brew install agenxy/lanes/lanes
```

Two static binaries, no database, no runtime dependencies. Agents connect over
MCP. [Fifteen-minute tutorial](https://github.com/agenxy/lanes/blob/main/docs/TUTORIAL.md).

More is on the way, with less in common with Lanes than you might expect. It will
show up here when it is ready rather than when it is announced.

### The name

Agents. Agency, in the sense above. An agency, as in a firm. `xy`, which looks
like coordinates and reads like the start of a list that keeps going. It is a
good name that happens to fit several things we care about. We are not going to
pretend it was a deduction.

### How we work

- **[Charter](https://github.com/agenxy/.github/blob/main/CHARTER.md)**: what we
  will and will not build, and what we owe the people who use it.
- **[Engineering standards](https://github.com/agenxy/.github/blob/main/ENGINEERING.md)**:
  latest versions, warnings as errors, native over shell, and how we write.
- **[Contributing](https://github.com/agenxy/.github/blob/main/CONTRIBUTING.md)**:
  what we are glad to receive and what gets checked.

We would rather shut a project down than harm, betray, exploit or mislead the
people who use it. That is the decision procedure, not a slogan.
