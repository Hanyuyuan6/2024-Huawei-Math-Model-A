# Security Policy

## Supported version

Security fixes are applied to the current default branch. Historical research snapshots and archived experiment artifacts are not maintained as separate supported releases unless a release note says otherwise.

## Report a vulnerability privately

Use GitHub's **Security → Advisories → Report a vulnerability** workflow for this repository. Private vulnerability reporting is enabled.

Do not open a public issue, discussion, or pull request for a suspected vulnerability, leaked credential, unsafe deserialization path, dependency compromise, or exploit details before the report has been triaged.

Include:

- affected commit, file, and configuration;
- realistic impact and threat model;
- minimal reproduction steps or proof of concept;
- whether a credential or third-party system may already be exposed;
- any safe mitigation you have tested.

For ordinary correctness bugs, reproducibility questions, or documentation problems that do not create a security impact, use a normal GitHub issue.

## Secrets

Never submit a live secret as evidence. Redact it, provide only the minimum identifying suffix when necessary, and rotate it immediately if exposure is plausible.
