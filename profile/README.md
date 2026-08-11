## Agenxy

Local-first infrastructure for fleets of AI agents.

### [Lanes](https://github.com/agenxy/lanes)

Coordination and situational awareness for the AI agents running on your machine,
across whatever projects they have open. Each
agent registers a lane, declares what it is pursuing, and is told immediately if
someone else is already pursuing it. Agents exchange typed mail with receipts and
deadlines, and place advisory claims on the few things that genuinely need
exclusivity.

Lanes reports; it never acts. No agent can act on another through it, and the
worst message you can receive is one you may decline.

```sh
brew install agenxy/lanes/lanes
```

Two static binaries, no database, no runtime dependencies. Agents connect over
MCP. [Fifteen-minute tutorial](https://github.com/agenxy/lanes/blob/main/docs/TUTORIAL.md).
