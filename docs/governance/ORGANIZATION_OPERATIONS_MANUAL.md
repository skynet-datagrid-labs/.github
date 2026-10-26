# Skynet Datagrid Labs — Organization Operations Manual

**Prepared:** 26 October 2026 · **Status:** Baseline and operating design; verify changing GitHub settings before applying.

## Purpose and scope

This manual governs collaboration across the currently visible organization repositories: `alpha-centauri-rescue`, `Kenya-Product-Sales`, `sales-intelligence-dashboard`, and `.github`. The organization is a student-led data science collaboration hub. This manual does not confer authority or assign named owners. Roles below are functions to fill by agreement.

## Quick start

1. Select a repository classification and confirm an accountable maintainer before starting substantial work.
2. Create an issue with outcome, context, acceptance criteria, risks, and dependencies.
3. Move work through **Backlog → Ready → In Progress → Review → Done**; mark blocked work with `status:blocked` and explain the unblock condition.
4. Work on a short-lived branch; open a pull request with linked issue, tests/evidence, documentation and data impact.
5. Review for correctness, reproducibility, privacy, licensing and security. Merge only after agreed checks pass and a maintainer accepts the change.
6. Record releases and operational decisions in the repository.

## Governance

The organization exists to build and teach reproducible data science, machine learning, analytics and software engineering through collaborative projects. Governance should favor transparent written decisions, small reversible changes, least privilege, respectful conduct, and evidence-based claims.

**Functional roles:** Organization owner handles account security, billing/plan, organization policy and escalation. Repository maintainer stewards repository access, standards, reviews, releases and issue health. Project lead coordinates scope, milestones, dependencies and status. Contributors propose and deliver scoped work. Security contact triages vulnerability reports and coordinates remediation. One person may fill multiple functions only where the organization agrees; no person is assigned by this document.

**Decisions:** Routine changes follow repository review. Cross-repository standards require a written proposal in `.github` and maintainer discussion. Access, visibility, ownership, licensing, archival, transfer, and security-policy changes require owner approval and a recorded rationale. Escalate urgent security or conduct concerns privately to an organization owner; do not publish vulnerability details in public issues.

**Repository lifecycle:** Create a repository only with a purpose, sponsor/maintainer, visibility rationale, data and license review, README, and maintenance expectation. Names use lowercase kebab-case for new projects; existing names are preserved. Classify at creation and review quarterly. Archive only after maintainer and owner approval, checking dependents, data retention, links, and recovery needs. Classification is descriptive, not a quality ranking.

## Portfolio classifications (evidence at audit date)

| Repository | Classification | Evidence and caveat |
|---|---|---|
| `alpha-centauri-rescue` | Active project | Python/Jupyter ML competition submission; latest push 20 Oct 2026; source, notebook and data directories present. |
| `Kenya-Product-Sales` | Active project | Kenya FMCG KPI dashboard project; latest push 20 Sep 2026; data, workbook, PDF and assets present. |
| `sales-intelligence-dashboard` | Active project | Power BI/Tableau/Python dashboard assets; latest push 15 Sep 2026; workbook, PDF, PBIX, data and assets present. |
| `.github` | Shared infrastructure | Organization profile and shared image assets. The profile currently contains numerous claims and project links not represented in the four-repository inventory; validate before promoting them. |

No flagship or archived designation is assigned without a documented sponsor decision. Organization API returned four public repositories and no private repositories at audit time.

## Work management

Use an organization Project (Projects v2) if an owner with `read:project`/project write access can create and maintain it. Do not create a duplicate until existing projects are inspected with that scope. Suggested fields: Status (Backlog, Ready, In Progress, Review, Done; blocked via label or a Blocked field), Priority (P0–P3), Repository, Target milestone, Work type, Risk. Views: portfolio board grouped by Status; roadmap grouped by milestone; triage table filtered to open/untriaged; blocked view filtered by `status:blocked`; release view by milestone. Keep issue state, project status and release status aligned.

**Definition of Ready:** problem and user/outcome clear; acceptance criteria testable; scope bounded; dependencies and data/privacy/licensing implications identified; priority and target milestone agreed; owner function identified.

**Definition of Done:** acceptance criteria met; review complete; relevant checks pass; documentation and reproducibility updated; data/model provenance and limitations noted; security/privacy/licensing impacts addressed; issue closed and release notes updated when applicable.

**Priority:** P0 urgent security/data exposure or service-stopping defect; P1 blocks a committed deliverable or corrupts material results; P2 normal planned work; P3 improvement/opportunity. **Severity** describes impact: critical (active exposure or broadly unusable), high (major capability/data correctness impaired), medium (workaround exists), low (minor impact). Do not use priority as a substitute for severity.

Cross-repository dependencies use `blocked by #N`/`blocks #N` references and a shared project item, with repository-prefixed issue link when needed. Weekly, project leads review stale Ready/In Progress/Review items, blockers, due milestones, CI failures, security alerts and release readiness; publish a short update with shipped, next, blocked, risks, and decisions.

## Review and releases

Open a pull request early when design feedback is useful. Use a focused branch and descriptive title. Reviewers check behavior, tests, data handling, reproducibility, dependencies, docs, accessibility, secret exposure, licensing, and workflow permissions. Resolve all requested changes or document accepted risk. For research results, record dataset source/version, split strategy, random seeds where meaningful, metric definitions, and known limitations. Avoid claiming production readiness unless deployment and operations evidence supports it.

Use annotated version tags for deliberate releases; choose SemVer only for versioned software with a meaningful compatibility contract. Dashboard/research repositories may use dated releases or snapshots. Release notes describe changes, evidence, data/model compatibility, known issues and rollback. Do not publish sensitive data or credentials in artifacts.

## Access, onboarding and offboarding

Default organization repository permission is `none` (verified at audit). Keep it. Grant per-repository access through teams where membership and need are known. Read supports viewing; Triage issue/PR management; Write code contribution; Maintain repository administration; Admin only for trusted owners. Never give access simply to fill a proposed team. Existing `cryo-crew` and `dev-team` membership is visible to authenticated administrators; do not publish names in public handbook. Team repo assignments need a permissions review because API responses did not yield an unambiguous effective access level.

**Onboarding:** confirm sponsor and role; verify account MFA; add to the smallest appropriate team/repository; explain data, security, conduct and review rules; grant secrets only when necessary through approved stores; verify access; set review date.

**Offboarding:** confirm departure and repository responsibilities; transfer open work and ownership; remove org/team/outside-collaborator access; revoke tokens and third-party app access within owner control; rotate shared credentials if exposed; remove deploy keys/secrets as applicable; verify access removal and record completion privately.

Quarterly, owners review org owners, teams, outside collaborators, repository grants, installed apps, deploy keys and stale access. Current org-level controls allow members to create, delete and change visibility of repositories and invite outside collaborators. Owner review is recommended before changing these controls; do not change them as part of this baseline.

## Security and data handling

Use MFA on every organization account. Avoid committing credentials, personal data, restricted datasets, or license-incompatible material. Store runtime credentials in GitHub Actions secrets or an approved external secret manager with minimum scope and rotation owner. Prefer synthetic or documented public sample data. Review dataset terms, privacy, consent and redistribution rights before committing data.

Dependencies: declare and pin direct dependencies using the ecosystem lockfile where supported; update in small reviewed changes; inspect advisories and transitive changes; remove unused packages. Enable Dependabot alerts/security updates where available. Consider secret scanning/push protection and code scanning according to repository language, visibility and plan. GitHub Free plan and API-reported org defaults show these new-repository security controls are disabled; repository inspection showed Dependabot security updates and secret-scanning features disabled on all four repositories. Feature availability can vary by visibility and account entitlement. Validate in Settings → Code security and analysis before relying on controls.

Actions: use least privilege (`permissions` at workflow/job level); avoid `write-all`; pin third-party actions to full commit SHAs where practical; restrict triggers for untrusted forks; do not expose secrets to pull-request code; cache safely; review artifact contents and retention. Current repo API showed Actions enabled with all actions allowed and SHA pinning not required; CodeQL/Dependency Graph dynamic workflows appeared for `alpha-centauri-rescue`, but this does not prove successful runs. No default branch was protected on the four repositories at inspection. Do not require checks until the checks exist and have successful runs.

### Vulnerability response

1. Receive privately via repository Security tab/private vulnerability reporting when available, or a designated owner contact. Do not ask reporters to post exploit details publicly.
2. Acknowledge promptly; record affected versions, impact, reproducibility and safe contact channel in a restricted record.
3. Triage severity, exposure, data impact, affected dependencies and mitigations. Assign a response coordinator by function.
4. Contain: disable affected workflow/deployment or revoke exposed credential if authorized; preserve evidence; do not put secret values in tickets.
5. Remediate in a private branch/advisory when disclosure would increase risk; review and test fix; coordinate a release and user notice.
6. Verify deployment, alerts and credential invalidation; publish advisory after a fix or coordinated disclosure decision.
7. Conduct a blameless review and record timeline, cause, impact, corrective actions and owner functions.

If private reporting is unavailable, document a monitored security contact in SECURITY.md and instruct reporters not to include exploit details in public issues. Response target: acknowledge within two business days when staffed; critical exposures are escalated immediately to an owner. This is a proposed service target, not a current commitment.

## Maintenance, backup and recovery

Weekly: triage issues/PRs, blocked work, failed checks and security alerts. Monthly: review dependency updates, stale branches, release notes, workflow permissions and repository documentation. Quarterly: review access, classification, data retention, licenses, project portfolio, recovery copies and handbook accuracy. At each release: verify tag/artifacts, documentation, rollback instructions and data/model provenance.

GitHub is the canonical remote, not a complete independent backup. For important repositories, maintain an owner-approved mirror or periodic encrypted organization-controlled backup of Git history, releases, issues/projects where needed, and critical artifacts, with access limited and restore tested quarterly. Large PBIX/PDF/data assets may need separate retention policy. Never place backup secrets in the repository. Recovery: owner verifies incident and known-good backup; restore to a new repository or isolated location first; compare refs and checksums; validate confidentiality and issues/metadata; then approve cutover. Keep original intact until verification and record recovery decisions.

## Manual GitHub setup guide

**Project:** organization page → Projects → New project → Board. Add Status, Priority, Repository, Milestone and Work type fields; create Board, Roadmap, Triage, Blocked and Release views. Add repositories and define automation only after field behavior is confirmed. CLI/API alternatives require suitable project scopes; current token lacks `read:project`, so project inventory was not available.

**Repository security:** open each repository → Settings → Code security and analysis. Check available Dependabot alerts/updates, secret scanning/push protection, and code scanning. Enable only features actually offered; record date and result. For `alpha-centauri-rescue`, inspect existing CodeQL/Dependency Graph dynamic workflows before changing them.

**Branch rules:** repository → Settings → Branches → Add branch protection rule for `main` or use Rulesets if available. First identify actual required checks via Actions/Checks. Pilot one repository; require PRs and one approval only where maintainers are available; consider stale approval dismissal and conversation resolution. Do not require status names that have not run. Exemptions and enforcement vary by plan.

**Organization security controls:** organization → Settings → Authentication security / Member privileges / Repository defaults. Review MFA requirement and creation/deletion/visibility/invitation controls with owners. The current audit observed MFA requirement disabled and broad member repository privileges; changes need owner decision and member readiness planning.

## Failure handling and rollback

If a new check blocks valid work, inspect its run and failure logs; fix the workflow or temporarily bypass only with documented maintainer/owner decision. If an automation mislabels or moves work, disable that automation, restore issue/project state manually and review affected items. For accidental data or credential publication, restrict access as appropriate, revoke the credential immediately, preserve audit evidence, remove the material from current refs, then coordinate history remediation; deleting the visible file alone does not invalidate a secret. For mistaken repository configuration, record previous values before change and restore them through the same Settings page/API; verify after rollback.

## Review cadence

Owners review organization controls quarterly and after membership or security incidents. Maintainers review repository standards and contribution guidance quarterly. Project leads review boards weekly and milestones monthly. Security contact reviews open alerts weekly and response procedures quarterly. Assign actual people and contact channels through an owner decision; this manual intentionally does not invent them.

## Current configuration note — 26 October 2026

After the initial audit snapshot, Dependabot vulnerability alerts, secret-scanning alerts, and push protection were enabled and API-verified on all four public repositories. Automatic Dependabot security-update PRs and organization-wide defaults for new repositories remain disabled. This does not establish that any current alert scan is clean; review the repository Security tabs. The detailed change and verification record is in AUDIT_AND_IMPLEMENTATION_STATUS.md.

