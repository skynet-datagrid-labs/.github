# Project management guide

## Workflow

Backlog → Ready → In Progress → Review → Done. Use a blocked status or `status:blocked` label with a written unblock condition. Keep GitHub issue state separate from project status and update both coherently.

## Suggested portfolio project

Create only after inspecting existing Projects v2. Fields: Status (single select), Priority (P0–P3), Repository (single/multi-select), Milestone/date, Work type, Risk. Views: Portfolio board by Status; Roadmap by milestone; Triage table for open items missing priority/owner; Blocked view; Release view. Add repository issue sources and workflows only after a pilot.

Definition of Ready: outcome, acceptance criteria, bounded scope, dependencies, data/privacy/license risk, priority, milestone and responsible function are clear. Definition of Done: criteria met, review and checks complete, docs/reproducibility updated, risks addressed, issue closed and release notes updated when applicable.

Severity: Critical = active exposure or broadly unusable; High = major correctness/capability impairment; Medium = workaround exists; Low = minor impact. Priority: P0 urgent security/service stop; P1 committed deliverable blocked; P2 normal planned work; P3 improvement.

Cross-repository dependencies use linked issues (`blocked by`, `blocks`) and a portfolio item. Weekly review: shipped, next, blocked, risks, decisions; inspect stale items, milestone health and failed checks. Monthly milestone review records scope changes and acceptance evidence.
