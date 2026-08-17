# Contributing to an Agenxy project

This is the organisation-wide default. A repository with its own
`CONTRIBUTING.md` overrides it, and should still hold to what is below.

Two documents govern every project here:

- **[VALUES.md](VALUES.md)** is the short version of what we care about:
  licensing, privacy, and the line we do not cross.
- **[ENGINEERING.md](ENGINEERING.md)** is how we build. Versions, warnings,
  size limits, languages, security, the experience of using the thing, and how
  we write.

Read them before a first contribution. Most review comments you would otherwise
receive are already answered there.

## What we are glad to receive

Bug reports with a reproduction. Corrections to documentation, including ours
being wrong about our own behaviour. Failing tests for a bug you have not fixed,
which are genuinely useful on their own. Adversarial review: if you can make one
of our guarantees fail, that is one of the most valuable things you can send us.

Small, well-reasoned changes are easier to accept than large ones. If a change is
big, open an issue first so we can agree the shape before you spend the time.

## What will be checked

- The project's gate passes. Check its exit status; output can read clean
  while the run failed.
- New behaviour has a test that fails without the change.
- The compiler and linter are silent, with no new global suppressions.
- No `.sh` file, and no new subprocess where a call would do.
- Comments explain why, not what.
- Prose follows the writing rules in ENGINEERING.md.

## Licence and attribution

Contributions are accepted under Apache 2.0, the licence of every project here.
By opening a pull request you are offering your work under that licence.

You keep authorship. We do not squash away attribution, rewrite published history
or force-push over anybody's commits. If we ever appear to have dropped your
credit, it is a mistake and we will fix it.

## How we will treat you

Plainly and promptly, assuming you are acting in good faith. We
will tell you why if we decline something, and we will not leave a pull request
sitting without an answer.

If we get something wrong, including in how we have treated you, say so. We would
rather hear it than not.
