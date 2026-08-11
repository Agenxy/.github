## Agenxy

**Agency**: the ability to make decisions and act independently. That is what the
name is for, and it is the thing every project here is built toward.

Software should hand you the information and the controls, then get out of the
way. It should not decide on your behalf what you are allowed to want, obscure
what it is doing, report on you to somebody else, or stop working because a
licence server had an opinion. Those are not separate complaints. They are all
the same one: someone else holding a decision that was yours.

So everything here is Apache 2.0 and works completely, offline, with no trial, no
licence key and no telemetry. We do not log what you do with our software. If one
of our servers were breached tomorrow, nobody should need to change a password,
because there is nothing held about you to find. Those follow from the first
paragraph rather than sitting beside it.

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

More is on the way, and it will show up here when it is ready rather than when it
is announced.

### How we work

- **[Charter](https://github.com/agenxy/.github/blob/main/CHARTER.md)**: what we
  will and will not build, and what we owe the people who use it.
- **[Engineering standards](https://github.com/agenxy/.github/blob/main/ENGINEERING.md)**:
  latest versions, warnings as errors, native over shell, and how we write.
- **[Contributing](https://github.com/agenxy/.github/blob/main/CONTRIBUTING.md)**:
  what we are glad to receive and what gets checked.

We would rather shut a project down than harm, betray, exploit or mislead the
people who use it. That is the decision procedure, not a slogan.
