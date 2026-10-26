# Security baseline and checklists

## Secure development checklist
- [ ] No credentials, personal data, or unlicensed restricted datasets committed.
- [ ] Dataset/model source, permission, retention, and redistribution terms documented.
- [ ] Dependencies declared and updated in small reviewed changes; lockfile maintained where applicable.
- [ ] Input validation, safe serialization, and access controls appropriate to the application.
- [ ] Tests cover critical transforms and edge cases; research metrics include split/provenance and limitations.
- [ ] README documents safe setup; sample configuration uses placeholders only.

## GitHub Actions checklist
- [ ] Workflow/job `permissions` are minimal and explicit.
- [ ] Third-party actions pinned to full commit SHA where practical; updates reviewed.
- [ ] Fork and pull-request triggers do not expose secrets or privileged write tokens.
- [ ] Avoid executing untrusted PR code in privileged `pull_request_target` context.
- [ ] Cache/artifacts contain no secrets or restricted data; retention is appropriate.
- [ ] Required checks are real, stable, and observed passing before branch rules require them.

## Dependency policy
Use maintained, necessary dependencies. Pin/lock according to ecosystem; review source, license, advisories and transitive changes. Enable available Dependabot alerts and security updates. Triage exploitable/high-impact issues promptly; record accepted risk, mitigation owner and review date. Do not auto-merge unreviewed breaking dependency changes.

## Configuration audit observations — 26 Oct 2026
All four repositories had main unprotected. API-reported Dependabot security updates and secret scanning disabled. Organization defaults for new repositories had Dependabot alerts, secret scanning and Advanced Security off. Actions allowed all actions; SHA pinning not required. `alpha-centauri-rescue` lists CodeQL and Dependency Graph dynamic workflows, which should be inspected for run results. GitHub Free observed; feature availability varies. Verify Settings → Code security and analysis per repository before making claims about coverage.

## Post-audit change

On 26 Oct 2026, Dependabot vulnerability alerts, secret-scanning alerts and push protection were enabled and API-verified on all four public repositories. Automatic Dependabot security-update PRs remain disabled. Organization defaults for future repositories remain unchanged. See the audit report for the pull request and limits.
