# Synthaea

Synthaea is an open-source, multi-platform EDR/XDR for Linux, Windows and macOS. Detection runs
on the endpoint: behavioral rules, Sigma, YARA, IOC matching, on-device ML models and a
correlator. A control plane you host yourself collects detections from your fleet. There is no
Synthaea cloud, and the agent sends no telemetry to us.

**Status: public beta.** Linux is the most mature platform, Windows and macOS sensors are in
progress, and the control plane is a development stack, not production-ready. Run it on lab and
test machines, not on endpoints you depend on. The [progress page](https://synthaea.com/en/progress)
shows what works today and what blocks each milestone.

## Public repositories

| Repository | What it holds |
| --- | --- |
| [agent](https://github.com/synthaea-lab/agent) | The endpoint agent (Rust): sensors, detection engines, response, transport and packaging |
| [server](https://github.com/synthaea-lab/server) | The self-hostable control plane (Next.js, PostgreSQL) |
| [ml](https://github.com/synthaea-lab/ml) | The ML pipeline: datasets, training, calibration, evaluation and the model registry |
| [rules](https://github.com/synthaea-lab/rules) | Detection content: Sigma, YARA and IOC feeds |
| [scenarios](https://github.com/synthaea-lab/scenarios) | Benign attack scenarios and the detections each one must trigger, to validate the agent end to end |

## Links

- [synthaea.com](https://synthaea.com): the project site
- [Documentation](https://synthaea.com/en/docs): install, configure and run the agent and the control plane
- [Download](https://synthaea.com/en/download): the latest pre-release packages, with checksums
- [Progress](https://synthaea.com/en/progress): what works today, the beta blockers and recent activity

## Contributing

- **Issues** go to the repository of the component they concern; when in doubt, use
  [agent](https://github.com/synthaea-lab/agent/issues). Each repository's `CONTRIBUTING.md` and
  the [contributing guide](https://synthaea.com/en/docs/contributing) explain how to get set up.
- **No CLA.** Every commit carries a [Developer Certificate of Origin](https://developercertificate.org/)
  sign-off with your real name: `git commit -s`. You keep your copyright.
- **License:** Apache-2.0, except the Linux eBPF probes, which are dual-licensed
  GPL-2.0-only OR MIT because the kernel verifier requires a GPL-compatible license.

## Security

Never report a vulnerability in a public issue. Use GitHub private vulnerability reporting on the
affected repository (its *Security* tab, then *Report a vulnerability*); it is being enabled on
every public repository. See [SECURITY.md](https://github.com/synthaea-lab/.github/blob/main/SECURITY.md)
for the full policy. A dedicated contact address (`security@<domain>`) and PGP key are not yet
provisioned.
