# synthaea-lab/.github

Organization-wide defaults for the [Synthaea](https://github.com/synthaea-lab) repositories.
GitHub applies each file here to every repository of the organization that does not provide its
own.

| Path | Purpose |
| --- | --- |
| [`profile/README.md`](profile/README.md) | The organization profile shown on [github.com/synthaea-lab](https://github.com/synthaea-lab) |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Default contributing guide: issues, DCO sign-off, licensing and review standards |
| [`SECURITY.md`](SECURITY.md) | Default security policy and how to report a vulnerability privately |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | Contributor Covenant 2.1 |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE) | Bug report and feature request forms |
| [`.github/pull_request_template.md`](.github/pull_request_template.md) | Default pull request template |
| [`.github/workflows/dco.yml`](.github/workflows/dco.yml) | Reusable Developer Certificate of Origin check |

## DCO check

Every commit in a pull request must carry a `Signed-off-by:` line whose email matches the commit
author. Merge commits and bot commits are exempt. A repository enables the check with its own
`.github/workflows/dco.yml`:

```yaml
name: DCO

on:
  pull_request:

permissions:
  contents: read

jobs:
  dco:
    uses: synthaea-lab/.github/.github/workflows/dco.yml@main
```

## Contributing

Changes to these defaults follow the [contributing guide](CONTRIBUTING.md). Commits are signed
off with `git commit -s`.
