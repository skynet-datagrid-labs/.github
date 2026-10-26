# Change log

## 2026-10-26 — Initial audit package
- Created local governance and operating documentation from read-only GitHub inspection.
- Added repository inventory, prioritized risks, access and project models, maintenance calendar, security runbooks, and manual setup actions.
- No changes were written to GitHub.

## 2026-10-26 — Security baseline and review branch
- Enabled and API-verified Dependabot vulnerability alerts, secret-scanning alerts and push protection on all four public repositories.
- Opened draft PR #1 adding governance documents, forms, contribution and security policies, and the proposed profile README.
- Left organization-level defaults, automatic update PRs, branch rules, memberships and other admin settings unchanged.

## 2026-10-26 — Organization hardening and merge
- Merged PR #1 (5d118b) publishing governance docs, issue/PR templates, contribution/security guidance and an evidence-based organization profile.
- Enabled and verified non-admin restrictions on repository/team creation; kept default repository permission at none.
- Confirmed deletion, visibility and outside collaborator settings remained enabled after attempted API update; MFA readiness and Projects v2 access remain unresolved.


## 2026-10-26 — Governance publication
- Merged PR #1 (5d118b) to .github/main and verified key published files via GitHub Contents API.
- Restricted non-admin repository and team creation; API read-after-write verified. Other owner controls and MFA readiness remain outstanding.
