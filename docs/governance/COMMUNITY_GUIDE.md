# Community guide

## Where work belongs

- Bugs, features, tasks, and research proposals go through repository issue forms.
- Open questions and project discussion belong in GitHub Discussions.
- Pull requests should link an issue where appropriate and include scope, evidence, validation, data/model impact, and documentation updates.
- Vulnerabilities must be reported privately through **Security → Report a vulnerability**; never post exploit details in public issues or discussions.

The `.github` repository now has Discussions enabled. Discussions were already enabled on `alpha-centauri-rescue` and `sales-intelligence-dashboard`; they remain disabled on `Kenya-Product-Sales` because its current dashboard handoff does not need a second support channel.

## Shared standards

Organization-wide files live in the `.github` repository: `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `SUPPORT.md`, issue forms, and the pull-request template. Repository-specific guides may add detail for a project stack, but should preserve these safety and contribution expectations.

Topics and descriptions are set from verified repository contents. No license was added; the four existing repositories have no license metadata, and license selection needs a rights-holder decision.

## Label taxonomy

Ten labels are present in every repository:

- Type: `type:bug`, `type:feature`, `type:task`, `type:research`.
- Priority: `priority:P0` urgent/security or service stop, `priority:P1` committed deliverable blocked, `priority:P2` planned work, `priority:P3` improvement.
- `status:blocked` requires an unblock condition in the issue.
- `security` is for security-hardening work; never use it to post sensitive vulnerability details.

No empty milestones or sample issues were created. Create milestones only for real deliverables with agreed dates and maintainers.
