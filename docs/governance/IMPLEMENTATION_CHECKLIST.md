# Initial setup and handover checklist

## Batch A — Audit
- [x] Confirm local folder is not a Git checkout.
- [x] Confirm GitHub CLI login without exposing token; active organization admin verified.
- [x] Inventory all four accessible repositories, branches, issues, PR activity, teams and visible settings.
- [x] Record scope/plan limitations and avoid unsupported claims.

## Batch B — Governance and reusable standards (prepared locally)
- [x] Operations manual, governance model, portfolio classifications and review cadence.
- [x] Project and issue management design.
- [x] Issue forms, PR template, CODEOWNERS example (unassigned placeholder prohibited from use), security response and contributor guidance.
- [ ] Owner/maintainer review before publishing to `.github` or another repository.
- [ ] Choose license deliberately; do not add a license without rights-holder decision.

## Batch C — CI and security (not implemented)
- [ ] Inspect recent CodeQL/Dependency Graph runs and project stack.
- [ ] Verify eligible alerts/scanning features in repo settings; pilot enabling.
- [ ] Add language-specific CI only after inspecting package manifests and existing workflows.
- [ ] Pilot branch rules based on successful check names; validate collaborator review capacity.

## Batch D — Projects (prepared; scope blocker)
- [ ] Obtain `read:project` and project write capability, inspect existing org projects.
- [ ] If no suitable project exists, owner creates portfolio project and fields/views per manual.
- [ ] Pilot automation and verify status sync before wider adoption.

## Batch E — Team and permissions (no changes made)
- [ ] Owners review current teams, effective grants, owners, outside collaborators and MFA readiness.
- [ ] Approve least-privilege changes and member communication plan before applying.

## Batch F — Verification and handover
- [ ] Review proposals in pull requests or owner-approved publication process.
- [ ] Verify settings after every change; record date, actor role, previous/new values, result and rollback.
- [ ] Assign actual role-holders and private security contact.
- [ ] Review the calendar below and schedule next review.

## Maintenance calendar

| Frequency | Procedure | Evidence |
|---|---|---|
| Weekly | Triage issues/PRs, blocked tasks, failed workflows and alerts | Updated statuses and short project report |
| Monthly | Dependency updates, stale branches, README/run instructions, workflow permissions | Review notes and merged maintenance PR |
| Quarterly | MFA/access/team/outside-collaborator review, classifications, data/licenses, backups and handbook | Owner checklist and recovery test record |
| Each release | Tag/artifacts, release notes, provenance, rollback and compatibility | Release record |
| After incident | Contain, remediate, notify as appropriate, conduct review | Restricted incident record and corrective actions |

## Post-audit progress
- [x] Enabled and re-verified Dependabot vulnerability alerts, secret-scanning alerts and push protection on each of four public repos.
- [x] Opened draft PR #1 with the governance baseline and reusable templates; awaiting review.
- [ ] Inspect PR review and CI results; merge only after maintainers approve.
- [ ] Continue staged rollout for MFA, member privileges, branch rules, CI, projects and team access.
