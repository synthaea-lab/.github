# Synthaea

Synthaea is an open-source endpoint detection and response (EDR/XDR) system for Linux, Windows
and macOS. Detection runs on the endpoint: behavioral rules, Sigma, YARA-X, IOC matching,
on-device ONNX models and a correlator that combines detections into scored cases. It keeps
working when the host is offline. A control plane you host yourself collects detections from
your fleet. There is no Synthaea cloud, and the agent sends no telemetry to the project.

> [!WARNING]
> Synthaea is **alpha** software. Linux is the most complete platform, Windows follows, and
> macOS is at an early stage. The control plane is a development stack, not production-ready.
> Run Synthaea on test machines, not on endpoints you depend on. The
> [progress page](https://synthaea.com/en/progress) shows what works today and what is next.

## Repositories

| Repository | Contents |
| --- | --- |
| [agent](https://github.com/synthaea-lab/agent) | The endpoint agent, in Rust: sensors, detection engines, correlator, response, transport and packaging |
| [server](https://github.com/synthaea-lab/server) | The self-hosted control plane: Next.js and PostgreSQL |
| [ml](https://github.com/synthaea-lab/ml) | The ML pipeline: datasets, training, calibration, evaluation and the model registry |
| [rules](https://github.com/synthaea-lab/rules) | Detection content: Sigma and YARA rules, each with the samples it must match |
| [scenarios](https://github.com/synthaea-lab/scenarios) | Benign attack scenarios and the detections each one must trigger |
| [rig](https://github.com/synthaea-lab/rig) | The test rig: a machine catalog, Vagrant harnesses and a runner that reports expected versus detected |

## Get started

- [Documentation](https://synthaea.com/en/docs): architecture, installation, configuration and
  the control plane
- [Download](https://synthaea.com/en/download): pre-release packages with checksums
- [Progress](https://synthaea.com/en/progress): current status and recent activity

## Contributing

Contributions are welcome. Open issues on the repository of the component they concern; when in
doubt, use [agent](https://github.com/synthaea-lab/agent/issues). The
[contributing guide](https://synthaea.com/en/docs/contributing) and each repository's own
`CONTRIBUTING.md` or `README.md` explain how to set up and submit changes.

There is no CLA. Every commit carries a
[Developer Certificate of Origin](https://developercertificate.org/) sign-off (`git commit -s`),
and you keep your copyright.

## Security

Do not report vulnerabilities in public issues. The
[security policy](https://github.com/synthaea-lab/.github/blob/main/SECURITY.md) explains how to
reach the maintainers privately.

## License

Apache-2.0, except the Linux eBPF probes, which are dual-licensed GPL-2.0-only OR MIT because the
kernel verifier requires a GPL-compatible license.
