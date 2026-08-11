# Agenxy engineering standards

How we build, in every repository in this organisation. [VALUES.md](VALUES.md)
is why we build it that way.

These are defaults with reasons attached, not commandments. A project may depart
from any of them, in writing, in the repository, with the reason recorded. What
is not acceptable is departing from one silently, or because it was quicker.

## Make the elite technical choice

No corners cut, no workarounds left in place, no security or performance problem
postponed. If the right approach costs a day and the workaround costs an hour,
take the day. If you genuinely cannot, write down what the real fix is and what
it will cost before shipping the other thing.

Architect for scale from the start: not premature optimisation, but the
decisions that are expensive to reverse. Where state lives, what is
authoritative, what can be rebuilt, what has to be correct under concurrency.

Aesthetics matter and yield to technical considerations when the two conflict.
They usually do not conflict.

## Versions

**Use the latest stable release of every language, tool, library and runtime.**
Verify the version at the moment you make the decision rather than trusting what
you remember, because what you remember is out of date. When a major release is
close enough to matter, say so and decide the timing deliberately.

Pin the toolchain so a fresh clone builds identically for everyone, and keep the
pins current rather than letting them rot into an accidental ancient baseline.

## Warnings are errors

Every warning the compiler, linter, type checker or analyser can produce is
turned on and is fatal to the build. A warning nobody has to fix is a warning
everybody learns to scroll past, and the one that mattered scrolls past with the
rest.

When a warning is genuinely wrong, suppress that one occurrence, narrowly, with a
comment saying why. Never disable the check globally, and never widen an
exemption to make an unrelated failure go away.

## Size limits

Files, functions, types and modules have ceilings, enforced by the linter rather
than by review. The number matters less than having one: a limit that is
occasionally annoying is doing its job, and something that has outgrown it is
usually two things that were never separated.

Current defaults, which a project may tighten:

| Bound | Default |
|---|---|
| Line length | 120 characters |
| Function length | 512 lines, 300 statements |
| Cyclomatic complexity | 15 |
| Cognitive complexity | 20 |

Exemptions are per-construct and carry a comment explaining the shape of the
code that earned them. A flat dispatch table over a hundred cases is genuinely
simple and scores badly; a function with four nested conditionals is not, and
scores the same. Say which one you have.

## Native by default

**No shell scripts**, with the narrow exceptions in the next section. Not for
builds, releases, task running, git hooks, test harnesses or application entry
points. Shell is untyped, continues past failures unless every script remembers
to ask it not to, quotes wrongly under whitespace, and cannot be tested or type
checked. A `.sh` file is unreviewable glue, and it accumulates.

| Instead of a shell script | Write |
|---|---|
| Build, install, release steps | Python, `uv` shebang, PEP 723 inline dependencies |
| An executable inside a macOS `.app` | A compiled Swift binary |
| Task running | The project's existing runner |
| A few commands in sequence | Run them; do not enshrine them in a file |

Running commands interactively is fine. Persisting them as a script is what this
forbids.

### Where shell is genuinely the only option

We live in the terminal, and a few places accept nothing else. The test is not
"shell would be easier here". It is **whether anything else can run at all**.

- **Bootstrap.** A script that obtains the toolchain cannot be written in the
  toolchain. If a user has no Python, no `uv` and no package manager entry, the
  first thing they run has to be shell. This is bootstrapping specifically, not
  installing: once a runtime exists, `task install` and its equivalents are
  ordinary programs and the exception has stopped applying.
- **Shell completions.** A zsh or bash completion is shell by definition.
  Generate it from the program rather than hand-maintaining it, so the source of
  truth stays in a typed language.
- **Shell integration.** Snippets a user adds to their profile, of the
  `eval "$(tool init zsh)"` shape. The program emits the shell; we do not keep a
  file of it.

Prefer a package manager where one exists. Homebrew, apt, winget and the
language registries are reviewed, versioned, upgradeable and revocable, and a
bootstrap script is none of those things. The script is the fallback for people
those channels do not reach, not the front door.

**A bootstrap script is held to stricter rules than ordinary code, because it
runs as the first thing on a machine we know nothing about, often piped straight
from the network into a shell.**

- Its only job is to obtain the toolchain and hand off. The moment a real
  runtime exists, control passes to a real program. Logic that accumulates here
  is logic nobody can test.
- POSIX `sh`, not bash. The machine may not have bash, and on macOS the bash
  that exists is ancient.
- `set -eu` on the first line, every expansion quoted, and no unguarded pipe
  whose failure you would not notice.
- **Verify what it downloads.** Check a signature or a pinned checksum before
  executing anything fetched. `curl | sh` is the single most attractive
  supply-chain target we could offer, and "it came from our domain over TLS" is
  not verification.
- Idempotent and safe to re-run. Refuse to run as root unless it truly needs to,
  and say what it is about to do before doing it.
- Serve it from the repository, over HTTPS, at a stable path, and keep it short
  enough that a cautious person can read the whole thing before running it.
  Someone will, and they are right to.

**No subprocesses as an architecture.** Spawning a process to do what a library
call could do is slow, hard to observe, hard to test, and turns every error into
a parsing problem.

**Native bindings over boundary chatter.** When two languages meet, bind them
directly rather than serialising across a pipe for every call. A design that
crosses constantly has put the boundary in the wrong place.

**Python is for automation**, and always through `uv` with PEP 723 inline
metadata and a `#!/usr/bin/env -S uv run --script` shebang. Never bare `python3`,
never a `requirements.txt`, never a virtualenv a person has to remember to
activate.

## Languages

Preferred: **C++, Go, Python, Rust, Swift, TypeScript.**

Avoided: **Bash and other shells, Objective-C** (write Swift), **JavaScript**
(write TypeScript), **PHP, Perl, PowerShell, BASIC.**

Avoided means avoided, not forbidden. If a platform accepts nothing else, say so
explicitly and explain why before writing it.

Use `bun` for JavaScript and TypeScript work, never `npm`.

## Security and privacy

VALUES.md states the position; this is the practice.

Threat-model before you build, not after. Assume the process is hostile, the
input is hostile, and the filesystem is shared. Validate at the boundary, and
know which side of it you are on.

Never log personal data. Never put it in a URL, a query string, an error message
or a crash report. When you must handle a secret, know its lifetime and make it
short.

Security work is never postponed to a later milestone. A known vulnerability
shipped deliberately is a decision to harm someone later, and there is no
schedule pressure that makes that acceptable.

## The experience of using it

Treat interface and developer experience as requirements, not polish applied at
the end.

**Errors are the product.** An error message should say what happened, why, and
what the reader should do next. It is written for somebody who is confused, in a
hurry, and does not know the internals. An error that says only that something
failed is a bug report we chose not to write.

**Help is the product.** Every command explains itself. Every flag says what it
does and what happens by default. Nobody should have to read the source to use
the tool.

**The terminal experience matters.** Alignment, colour that degrades gracefully
when it is not a terminal, output that is readable by a person and parseable by a
machine when asked, sensible behaviour when piped, no surprise interactivity in a
script.

## Writing

Aim for writing that is precise and easy to read. Avoid the vocabulary and shapes that read as machine-written: em dashes; delve,
leverage, foster, seamless, robust, cutting-edge, pivotal, meticulous,
intricate, paramount, tapestry, realm, landscape, beacon, journey, showcase,
underscore, unleash, empower, navigate, demystify, myriad, plethora,
comprehensive, transformative, revolutionary, game-changer; furthermore,
moreover, additionally, in conclusion; "it is not just X, it is Y"; the rule of
three used as a rhythm; hedges like "it is important to consider"; and openers
that clear the throat before saying anything.

An em dash is doing one of a few jobs, so replace it with the job rather than
with a single substitute. A colon when what follows explains what came before. A
semicolon or a full stop when both halves stand alone. Commas or parentheses for
an aside. Often the sentence is better as two. Never a hyphen, which reads as a
typo.

## Documentation

A README that respects the reader's time, a tutorial somebody has actually
followed end to end, manpages where the platform expects them, and reference
material that is generated rather than transcribed.

Documentation that has drifted from the code is worse than none, because it is
believed. Where a fact lives in two places, make one canonical and make the drift
fail the build.

## Enforcement

A standard nobody checks is a preference. Wherever a rule here can be mechanical,
it should be:

- Licence and its metadata checked at repository creation.
- Linters configured with warnings fatal and the size limits above.
- A check that no `.sh` file has entered the tree, with a small explicit
  allowlist for the bootstrap and completion cases above. An allowlist entry
  is a decision, so it is reviewed like one.
- Toolchain pins verified in CI, and dependency updates automated.
- Prose checks for the writing rules that can be tested, starting with em dashes.
- A gate whose exit status is the source of truth. Read the status, not the
  output: grepping a log for the word "failed" has already reported a red run as
  green in one of these projects.
