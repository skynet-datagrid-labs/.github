# Live organization audit and implementation status

**Checked:** 26 October 2026. **Organization:** `skynet-datagrid-labs`. **Plan:** Free. **Authenticated account:** `Tony405-spec`, active organization `admin` role. CLI token scopes at audit: `gist`, `read:org`, `repo`, `workflow`. The account was not reported as an owner by the membership endpoint; the endpoint exposed role `admin`. No credential values are stored here.

## Organization and repository inventory

The organization has four public repositories and no private repositories:

| Repository | Purpose/evidence | Topics | Current controls |
|---|---|---|---|
| `alpha-centauri-rescue` | Kaggle Spaceship Titanic project; Python/Jupyter; `src`, `notebooks`, `data`, and `submissions` | `kaggle`, `spaceship-titanic`, `machine-learning`, `python`, `jupyter-notebook` | `main` unprotected; Python CodeQL setup configured weekly |
| `Kenya-Product-Sales` | Kenya FMCG KPI dashboard; data, workbook, PDF and assets | `business-intelligence`, `kenya`, `power-bi`, `sales-analytics` | `main` unprotected; no code-scanning analysis returned |
| `sales-intelligence-dashboard` | Power BI/Tableau/Python dashboard assets; workbook, PDF, PBIX, data and assets | `business-intelligence`, `tableau`, `power-bi`, `data-visualization` | `main` unprotected; no code-scanning analysis returned |
| `.github` | Organization profile, community standards, shared governance documentation | `governance`, `community-health`, `github-templates` | `main` unprotected; Discussions enabled |

Repository topics were empty before this corrective run. Descriptions and topics above were written and read back from GitHub. No license metadata is present; no license was added. Visibility and default branches were not changed.

## Security — completed and verified

On all four public repositories, GitHub API read-back confirms Dependabot alerts, Dependabot security updates, secret-scanning alerts, push protection, and private vulnerability reporting are enabled. No open Dependabot alerts were returned. No dependency manifests were found, so Dependabot version updates were not configured.

Organization defaults for new repositories are enabled for Dependency Graph, Dependabot alerts, Dependabot security updates, secret scanning, and push protection. Advanced Security is disabled. These defaults do not change repository visibility; private-repository feature eligibility remains plan-dependent.

`alpha-centauri-rescue` has a configured weekly CodeQL setup for Python; the latest inspected CodeQL setup run succeeded and no CodeQL alerts were returned. The other three repositories returned no code-scanning analysis; the API did not identify source languages there. Do not treat their configured setup state with an empty language list as active code scanning.

All four `main` branches are unprotected and no rulesets were returned. Actions are enabled and all actions are allowed; SHA pinning is not required. Workflow token defaults are `write` and can approve pull requests for `alpha-centauri-rescue`, `Kenya-Product-Sales`, and `.github`; `sales-intelligence-dashboard` uses `read` and cannot approve PRs. These settings were not tightened because changing them may break workflows and requires owner approval.

## Client apps — inventory and limits

The organization has one GitHub App installation: CodeRabbit, selected for all repositories. It has read access to Actions, Discussions, Members, and Metadata; write access to Checks, Contents, Issues, Pull Requests, and Commit Statuses. No app was installed or removed. Organization OAuth-app policy and Actions policy endpoints returned HTTP 403; the CLI token lacks `admin:org`. See [client apps and integrations](CLIENT_APPS_AND_INTEGRATIONS.md).

## Project management — scope blocker

The organization Projects page shows three existing Projects. GraphQL returned `INSUFFICIENT_SCOPES` for `read:project`, so project titles, fields, views, workflows, and linked repositories could not be inspected. No project was created to avoid duplication. A request to authorize `read:project` and `project` scopes is pending; after approval, inspect all three before configuring one.

Repository labels are configured consistently: `type:bug`, `type:feature`, `type:task`, `type:research`, `priority:P0`–`P3`, `status:blocked`, and `security` are present in each repository. No empty milestones or sample issues were created.

## Team administration — inspected, no membership changes

The closed `cryo-crew` team has a Read grant on `alpha-centauri-rescue`; `dev-team` has a Read grant on `sales-intelligence-dashboard`. The organization default repository permission is `none`. Non-admin members cannot create repositories or teams. Repository deletion/transfer, visibility changes, and outside collaborator invitations remain enabled; outside collaborators currently count zero. Organization MFA enforcement remains disabled.

The API's `role=admin` member query returned 20 accounts, including the authenticated account, but did not distinguish organization owners from other administrators. No member names are published. Existing team membership and repository grants were not changed. Review owner status and organization controls under **Organization Settings → Organization roles** and **Member privileges**.

## Community — completed controls and pending publication

Discussions are enabled on `.github`, `alpha-centauri-rescue`, and `sales-intelligence-dashboard`; they remain disabled on `Kenya-Product-Sales`. The `.github` repository now has a descriptive summary and shared topics. The issue taxonomy is available in all four repositories and matches the organization issue forms.

This branch proposes updates to the `.github` repository root README and profile links, plus `CODE_OF_CONDUCT.md`, `SUPPORT.md`, and expanded feature-specific runbooks. Until its pull request is merged, those files are **prepared for review**, not live. Existing `CONTRIBUTING.md`, `SECURITY.md`, issue forms, and PR template remain in `.github`.

## Changes applied in this corrective run

- Enabled private vulnerability reporting and Dependabot security updates on all four public repositories; read-back verified.
- Enabled Dependency Graph, Dependabot alerts/security updates, secret scanning, and push protection as organization defaults for new repositories; read-back verified.
- Added ten issue taxonomy labels to each of the four repositories and verified label presence.
- Applied evidence-based repository topics, updated the `.github` description, and enabled `.github` Discussions; all read back successfully.
- No repository visibility, branch rules, memberships, team permissions, ownership, licenses, app installations, or credentials were changed.

## Status classifications

- **Completed and verified:** CLI authentication and admin role; four-repository inventory; repository and team grants; security settings above; app installation; new-repository security defaults; labels, topics, `.github` description, and Discussions toggle.
- **Already configured:** default repository permission `none`; `alpha-centauri-rescue` Python CodeQL setup; Discussions on `alpha-centauri-rescue` and `sales-intelligence-dashboard`.
- **Prepared for review:** organization root README and profile corrections, Code of Conduct, Support guide, and updated governance documentation on this branch.
- **Blocked by scopes:** Project inventory/configuration (`read:project`, `project`) and organization Actions/OAuth policy inspection (`admin:org`).
- **Requires owner approval:** branch protection/required reviews or checks; tightening workflow token permissions/action allow-list; MFA enforcement; repository deletion/visibility/outside-collaborator restrictions; changes to existing team grants/membership; removal or narrowing of CodeRabbit.
- **Unavailable / not appropriate:** Dependabot version updates because no dependency manifest exists; no license selection without rights-holder approval.
