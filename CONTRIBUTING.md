# Contributing to Synthaea

This is the default contributing guide for every public repository of the Synthaea organization
that does not carry its own `CONTRIBUTING.md`. It states the rules that hold everywhere; the
repository you are working in explains how to build, test and submit changes to it.

## Start with the repository's own guide

Each component has its own setup, conventions and quality gates. Read the `README.md` (and the
`CONTRIBUTING.md`, when there is one) of the repository you are changing before you start:

| Repository | Where to start |
| --- | --- |
| [agent](https://github.com/synthaea-lab/agent) | [CONTRIBUTING.md](https://github.com/synthaea-lab/agent/blob/main/CONTRIBUTING.md) |
| [server](https://github.com/synthaea-lab/server) | [README.md](https://github.com/synthaea-lab/server#readme) |
| [ml](https://github.com/synthaea-lab/ml) | [README.md](https://github.com/synthaea-lab/ml#readme) |
| [rules](https://github.com/synthaea-lab/rules) | [README.md](https://github.com/synthaea-lab/rules#readme) |
| [scenarios](https://github.com/synthaea-lab/scenarios) | [README.md](https://github.com/synthaea-lab/scenarios#readme) |

The [contributing guide](https://synthaea.com/en/docs/contributing) on the project site covers
the whole project.

## Issues

- Open an issue on the repository of the component it concerns; when in doubt, use
  [agent](https://github.com/synthaea-lab/agent/issues).
- **Never report a vulnerability in a public issue.** Read [SECURITY.md](SECURITY.md) and use
  the private channel. A way to blind, crash, bypass or subvert the agent is a security report,
  not a bug report.
- A well-argued objection to a design decision is a welcome contribution. Engage with the
  recorded reasoning and say what your alternative costs.

## Developer Certificate of Origin

There is **no CLA and no rights assignment**: you keep your copyright. Every commit carries a
[Developer Certificate of Origin](https://developercertificate.org/) sign-off with your real
name:

```bash
git commit -s -m "docs: correct the BPF LSM kernel requirement"
```

which adds:

```
Signed-off-by: Your Name <your.email@example.com>
```

By signing off, you certify that you wrote the contribution or otherwise have the right to
submit it under the project's license. Pull requests with unsigned commits are not merged. To sign
off commits you already made, run `git rebase --signoff main` and force-push your branch.

## License of your contribution

Contributions are accepted under **Apache-2.0**, except contributions to the Linux eBPF probes,
which are dual-licensed **GPL-2.0-only OR MIT** because the kernel verifier requires a
GPL-compatible license. Each repository's `LICENSE` (and `NOTICE`, when present) is
authoritative.

Because there is no CLA, the project cannot relicense your contribution without your consent,
so these license boundaries are effectively permanent. Make sure you are comfortable with them
before submitting.

## The clean-code bar

Every change is held to a strict clean-code bar and leaves the code cleaner than it found it.
Reviews reject changes that do not meet it:

- **Names** reveal intent: no abbreviations, encodings or noise words.
- **Functions** are small, do one thing at one level of abstraction, take few arguments and
  have no hidden side effects.
- **Comments** say only what code cannot (why, invariants, the incident behind a threshold); no
  commented-out code, no restating the next line.
- **Errors** are explicit and typed; no swallowed failures, no panicking shortcuts outside
  tests.
- **Modules** are small and cohesive, with a minimal public surface.
- **Tests** are fast, independent and named after the behavior they check; a bug fix lands with
  the test that would have caught it.
- **No duplication**, and the simplest design that passes the tests.
- **English only** in identifiers, comments, docs and commits.

Each repository's linters and CI make these rules concrete, with warnings treated as errors.

## Pull requests

- Keep a pull request small and about one concern; link the issue it addresses.
- Write commit messages that say what changed and why.
- Run the repository's checks locally before pushing; the pull request template lists what
  reviewers look for.
- Participation is governed by the [Code of Conduct](CODE_OF_CONDUCT.md).
