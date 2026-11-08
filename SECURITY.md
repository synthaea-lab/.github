# Security Policy

This is the default security policy for every public repository of the Synthaea organization
that does not carry its own `SECURITY.md`. Repositories that do (such as
[agent](https://github.com/synthaea-lab/agent/blob/main/SECURITY.md)) take precedence for their
scope and what to expect.

Synthaea is security software. A vulnerability here is not an inconvenience: it is a foothold on
every endpoint running the agent, at the highest privilege level on the machine. We treat reports
accordingly.

> [!IMPORTANT]
> **Being set up.** The contact address and PGP key below are not yet provisioned, and GitHub
> Private Vulnerability Reporting is being enabled on each public repository.
>
> - [ ] Provision `security@<domain>` and route it to a monitored, access-controlled inbox
> - [ ] Publish a PGP key and record its fingerprint here
> - [ ] Enable GitHub Private Vulnerability Reporting on every public repository
> - [ ] Register for CVE assignment (GitHub is a CNA and can issue CVEs for these repositories)

## Reporting a vulnerability

**Do not open a public issue, pull request or discussion.**

Use **GitHub Private Vulnerability Reporting** on the repository the vulnerable code lives in:
its *Security* tab, then *Report a vulnerability*. It is private, threaded, and gives a path to
a CVE.

- [agent](https://github.com/synthaea-lab/agent/security) for the agent, driver and probes, and
  when you are not sure or the issue spans components;
- [server](https://github.com/synthaea-lab/server/security) for the control plane;
- [ml](https://github.com/synthaea-lab/ml/security) for the models and the training pipeline;
- [rules](https://github.com/synthaea-lab/rules/security) for detection content;
- [scenarios](https://github.com/synthaea-lab/scenarios/security) for the attack scenarios and
  their expected detections.

Until the *Report a vulnerability* button appears on a repository, open an issue on
[agent](https://github.com/synthaea-lab/agent/issues) titled "Security contact request", with
**no details** of the finding, and a maintainer will reach out privately.

Alternative, once provisioned: email **security@\<domain\>**, encrypted with our PGP key
(fingerprint: *TBD*) if the report contains exploit detail.

Please include, to whatever extent you have it:

- Component and version (agent, driver, control plane, ML pipeline, detection content)
- Platform and OS build
- Impact: what an attacker gains
- Reproduction steps or a proof of concept
- Whether the finding is already public or shared with third parties

## What to expect

| Stage | Target |
| --- | --- |
| Acknowledgement of receipt | 48 hours |
| Initial assessment and severity | 5 business days |
| Fix or documented mitigation | 90 days, or sooner by severity |
| Public disclosure | Coordinated with you, after a fix ships |

We follow coordinated disclosure and will credit you by name unless you would rather we did not.

## Safe harbor

We will not pursue or support legal action against researchers who act in good faith: who report
promptly and privately, who avoid privacy violations and service degradation, who do not
exfiltrate data beyond what is needed to demonstrate impact, and who give us reasonable time to
fix before disclosing. If you are unsure whether something crosses a line, ask us first.
