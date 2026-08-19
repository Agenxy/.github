# Security

This is the default policy for Agenxy repositories. A repository with its own
`SECURITY.md` supersedes it, and the larger projects have one because their
threat models differ.

## Reporting a vulnerability

**Privately, through the repository's Security tab: "Report a vulnerability".**
That form is a private channel between you and the maintainers, and it stays
private until an advisory is published. Private vulnerability reporting is
enabled on every Agenxy repository.

**Or email security@agenxy.org**, which reaches a maintainer whatever the
project is. Use it when you are unsure which repository is affected, when the
issue spans more than one, or when you would rather not open a GitHub account
to tell us something. The advisory form is still better once the project is
known, because the report becomes the published advisory with your credit on
it.

Both routes are listed in
[agenxy.org/.well-known/security.txt](https://agenxy.org/.well-known/security.txt).

Do not open a public issue for a vulnerability. There is no bug bounty.

Useful things to include, none of them required: what you did, what happened,
what you expected, the version, and the platform. A report that only says
something looks wrong is still worth sending.

## What to expect

A response within a week. If the report is valid we will tell you what we
intend to do and roughly when. If we disagree that it is a vulnerability we
will say so and explain why, rather than leaving it unanswered.

Credit goes to the reporter in the advisory unless you ask otherwise.

## Scope

These projects run on your own machine. There is no Agenxy server, no account,
and no telemetry, so there is no hosted surface to attack and nothing of yours
on our infrastructure to breach. The interesting surface is local: what a
process on the same machine can reach, what a malicious peer can send, what an
installer touches, and what a supply-chain compromise of a dependency would
reach.

Reports about a dependency belong upstream first. Tell us anyway if an Agenxy
project is what exposes it.

## Supported versions

The latest release of each project. These are young projects on a small team;
backporting to older tags is not something we can honestly promise.
