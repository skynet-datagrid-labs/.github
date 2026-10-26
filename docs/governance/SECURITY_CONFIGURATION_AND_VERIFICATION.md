# Security configuration and verification

**Checked:** 26 October 2026 · **Plan:** GitHub Free · **Repositories:** four public repositories.

## Current repository controls

| Repository | Dependabot alerts | Dependabot security updates | Secret scanning | Push protection | Private vulnerability reporting | Code scanning |
|---|---|---|---|---|---|---|
| `alpha-centauri-rescue` | Enabled; no open alerts | Enabled; not paused | Enabled | Enabled | Enabled | CodeQL default setup configured for Python, weekly; latest inspected CodeQL setup run succeeded; no open CodeQL alerts |
| `Kenya-Product-Sales` | Enabled; no open alerts | Enabled; not paused | Enabled | Enabled | Enabled | No source language detected; no code-scanning analysis returned |
| `sales-intelligence-dashboard` | Enabled; no open alerts | Enabled; not paused | Enabled | Enabled | Enabled | No source language detected; no code-scanning analysis returned |
| `.github` | Enabled; no open alerts | Enabled; not paused | Enabled | Enabled | Enabled | No source language detected; no code-scanning analysis returned |

Dependabot alert/update, secret-scanning, push-protection, and private-reporting settings were read back from the GitHub API after configuration. No open Dependabot or CodeQL alerts were returned at audit time. This is a point-in-time result, not a guarantee that repositories contain no secrets or vulnerabilities.

All four repositories are public. No dependency manifests were found in the repository trees; Dependabot version updates are therefore not configured. Add version-update configuration only when a supported dependency manifest and package ecosystem exist.

## Organization defaults and access

The organization is on GitHub Free. New-repository defaults for dependency graph, Dependabot alerts, Dependabot security updates, secret scanning, and push protection are enabled. Advanced Security remains disabled. Feature applicability to future private repositories depends on plan entitlement; verify security status after each repository is created.

The default repository permission is `none`. Non-admin members cannot create repositories or teams. Repository deletion/transfer, visibility changes, and invitations for outside collaborators remain allowed; these organization controls were not changed. Organization-wide MFA enforcement is off. No member or team membership was changed.

## Actions and branch controls

All four repositories allow all GitHub Actions and do not require third-party actions to be pinned to a full commit SHA. Repository workflow-token defaults are `write` for `alpha-centauri-rescue`, `Kenya-Product-Sales`, and `.github`; `sales-intelligence-dashboard` uses `read`. The first three also allow workflow tokens to approve pull requests. The organization Actions policy endpoint could not be read with the current token because GitHub requires `admin:org` scope.

All four default `main` branches are unprotected and no repository rulesets were returned. Do not add required check names until a check has a verified successful run. Enforcing pull-request reviews or required checks can block direct work; obtain owner approval and confirm reviewer capacity before enabling rules.

## Manual security review

1. Organization owners review **Settings → Security and quality → Authentication security** and decide on MFA enforcement after confirming member enrollment and recovery access.
2. In each repository, review **Settings → Code security and analysis** and **Security and quality** for new alerts.
3. In **Settings → Actions → General**, review allowed actions, workflow token permissions, and whether a SHA-pinning policy fits the workflows.
4. For a branch rule, confirm actual check names under **Actions** and **Checks**; pilot a single repository with a staffed reviewer group before enforcing.
5. After a vulnerability report, use the private advisory flow, triage privately, rotate exposed credentials through the relevant provider, and publish a fix only when safe.

## Plan and permission limits

Secret scanning, push protection, and private vulnerability reporting are enabled on these public repositories. Organization-level Actions and OAuth-app policy endpoints returned HTTP 403 because this CLI token lacks `admin:org`. Projects and OAuth settings should be read after the appropriate scopes or owner UI access are available.
