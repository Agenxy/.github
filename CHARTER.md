# The Agenxy charter

What we will build, what we will not, and what we owe the people who use our
work. This applies to every Agenxy project. Where a repository says something
that contradicts it, this document wins and the repository is wrong.

[ENGINEERING.md](ENGINEERING.md) is the technical half: how we build. This one is
why.

## What the name is for

**Agency: the ability to make decisions and act independently.** Everything below
is downstream of it, and when two rules here appear to conflict, the one that
leaves more decisions with the user wins.

The failure we are organised against is a decision that was yours being held by
somebody else. It usually arrives wearing something reasonable. A default you
cannot see. A restriction sold as safety. A useful feature that needs to watch
you first. A tool that refuses a legitimate instruction because its author
disapproved of the instruction. A licence check between you and work you already
paid for. Those look like separate complaints and are one.

The practical form of it is **sovereignty**: your machine is yours, and our
software runs there as a guest. Concretely, and each of these is testable rather
than a sentiment:

- It runs on hardware you control, and works with the network unplugged.
- It needs no account, no licence server and nobody's permission to start.
- Its data is on your disk in a form you can read without our software, and
  deleting our software does not take your work with it. Where something must be
  encrypted at rest, the key sits beside it on the same machine and never leaves.
- You can read it, change it, fork it, and run the fork instead.
- **We cannot change what it does on your machine.** No forced update, no remote
  kill switch, no behaviour that we can alter from our side after you installed
  it. An update happens because you chose it.

This is not a preference for a category of software. It is not command-line
software, or developer tools, or any particular architecture, though ours tend to
be those things because that is where the decisions can still be handed back. It
is about who ends up holding the decision.

## Licence

**Apache 2.0. Every project, chosen at the moment the repository is created.**

Both Apache 2.0 and MIT are permissive, and Apache is the more complete of the
two. It grants patent rights from contributors explicitly where MIT is silent,
it terminates the licence of anyone who sues over the covered code, and it states
that no trademark rights come with it. Projects that expect contributions from
people with employers need that clarity before those employers allow the
contribution.

Pick it at creation rather than later. Relicensing works, because MIT permits
sublicensing, but the cost scales with the number of people you have to ask. With
one outside contributor it is a courtesy message. With fifty it is a project.

## The user is the authority

This is the previous section made operational. Our software executes what it was
asked to do. It does not reserve a namespace
for itself, refuse a technically valid instruction because it disapproves,
disguise a failure to look tidier, or invent restrictions that serve us rather
than the person running it. Power over your own machine should be legible and
reversible.

That is not licence for careless defaults. Distinguish intent from accident,
authenticate anything that mutates, keep an audit trail the user can read, and
make consequences understandable without becoming paternalistic. Say what
happened and what it means; do not decide on their behalf what they are allowed
to want.

The two projects this was written from both arrived at it independently, which is
how it earned a place here rather than in one repository: one reports on agents
and never acts on them, the other maps any name the user asks for and declines to
moralise about which names those are.

## Privacy

**We do not log what you do with our software.** Not usage, not telemetry, not
"anonymised" analytics, not crash reports containing your data. Where a feature
genuinely cannot work without collecting something, it collects the minimum, says
so plainly at the point of collection, and works in some reduced form if you
decline.

**The test we hold ourselves to: if one of our servers is breached tomorrow,
nobody should need to change a password or worry about what was exposed.** An
attacker should find nothing about our users, because there is nothing to find.
Our code is meant to be read anyway, so all they will have done is find us a
vulnerability. Design for that outcome from the start; it is not something you
retrofit.

This is a design constraint, not a promise about our diligence. Any system whose
safety depends on us being careful with data we hold is the wrong system. Keep
the data on the user's own machine, encrypt with a key that stays with them, and
prefer protocols that never need the data in the first place.

## No restrictions

No trials, no licence keys, no DRM, no feature gates, no seat counts, no
telemetry-as-a-condition-of-use. Software we publish works completely, offline,
forever, for anyone.

Nothing we build may depend on a commercial, paid, subscription or otherwise
unfree service, API or SDK. A dependency someone else can switch off is a
dependency that will eventually be switched off, and the person it fails is a
user who did nothing wrong.

## Money

We are not against being paid, and monetisation is not ruled out. When it
happens it will be obvious, stated in plain language, and never a surprise
discovered at the moment you needed the software to work. It will not be
implemented by taking something away from what already worked.

Values come first. When a commercial, political or self-interested reason
conflicts with this charter, the charter wins, and we will say publicly that it
did.

## People

We aim to be accessible, international, inclusive, open, helpful and kind. Those
are engineering requirements as much as social ones: software that assumes one
language, one keyboard, one pair of eyes or one kind of user is badly built.

We would rather shut a project down than harm, betray, exploit or mislead the
people who use it or contribute to it. That is not a rhetorical flourish; it is
the actual decision procedure, and if we ever face it we expect to be held to
it.

The point of the work is to be a net positive. If a project stops being one, the
right move is to say so and stop.

## Other projects

We support projects and organisations that share these values, including ones we
disagree with about everything else. Language choice, architecture, taste and
opinion are not the test. Whether the people involved are honest with their users
is the test.

We ignore the ones that fail it. We do not attack them.

## Legal

We ask for attribution, citation and credit, as our licence implies. Asking is
the operative word: we would rather be generous about this than litigious, and we
are not interested in policing edge cases.

We respect intellectual property, authorship, copyright, trademarks, licences and
terms of use. If we have got something wrong, tell us and we will fix it properly
rather than argue. We expect the same courtesy and will usually extend it first.

Patent trolls get nothing from us. The Apache 2.0 termination clause is one of
the reasons we chose it.

Live and let live. When it comes to it, we will defend our users, our
contributors and our work.
