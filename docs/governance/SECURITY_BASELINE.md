# Security baseline and checklists

See [Security configuration and verification](SECURITY_CONFIGURATION_AND_VERIFICATION.md) for live settings. The organization is on GitHub Free; feature availability depends on repository visibility and plan.

## Current baseline — 26 October 2026

All four public repositories have Dependabot alerts and security updates, secret-scanning alerts, push protection, and private vulnerability reporting enabled. There are no open Dependabot alerts. Dependency manifests were not found. The organization defaults for new repositories enable Dependency Graph, Dependabot alerts/security updates, secret scanning, and push protection. Advanced Security remains off.

CodeQL is configured for Python in `alpha-centauri-rescue`; the latest inspected CodeQL setup run succeeded and there are no CodeQL alerts. No code-scanning analysis was returned for the other three repositories. All four `main` branches are unprotected. All GitHub Actions are allowed and SHA pinning is not required. Workflow-token defaults are write-capable for three repositories and read-only for `sales-intelligence-dashboard`; do not change without checking workflows and obtaining approval for restrictive changes.

## Secure development checklist

- [ ] No credentials, personal data, or unlicensed restricted datasets committed.
- [ ] Dataset/model source, permissions, retention, and redistribution terms documented.
- [ ] Dependencies declared and updated in small reviewed changes; lockfiles maintained where applicable.
- [ ] Inputs validated; serialization and access controls fit the application.
- [ ] Tests cover critical transforms; research metrics include split/provenance and limitations.
- [ ] README documents safe setup; sample configuration uses placeholders only.

## GitHub Actions checklist

- [ ] Workflow/job `permissions` are minimal and explicit.
- [ ] Third-party actions are pinned to full commit SHAs where practical.
- [ ] Fork and pull-request triggers do not expose secrets or privileged write tokens.
- [ ] Avoid untrusted PR code in privileged `pull_request_target` workflows.
- [ ] Caches and artifacts contain no secrets or restricted data.
- [ ] Required checks exist, are stable, and have successful runs before rules require them.

## Dependency policy

Use maintained dependencies that are necessary for the project. Pin/lock according to ecosystem; review source, license, advisories, and transitive changes. Keep Dependabot security updates enabled. Add Dependabot version-update configuration only after adding a supported dependency manifest. Triage high-impact issues promptly and record accepted risks, mitigations, and review dates. Do not auto-merge unreviewed breaking changes.

## Vulnerability response

All four public repositories support private vulnerability reporting through **Security → Report a vulnerability**. Keep exploit details out of public issues. Triage privately; identify affected versions, impact, and safe mitigation; coordinate a fix and advisory; verify credential invalidation if a secret was exposed; and document a restricted post-incident review.
