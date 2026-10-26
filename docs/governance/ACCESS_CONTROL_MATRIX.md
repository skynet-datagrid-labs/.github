# Access control matrix

This is a proposed model; no real member assignments are made here.

| Function/team | Typical access | Scope |
|---|---|---|
| Organization owners | Admin | Organization settings and owner duties; keep membership minimal |
| Core maintainers | Maintain; Admin only for named repo stewards | Repositories they actively steward |
| Project contributors | Write | Specific active project repositories |
| Triage/community | Triage | Issue/PR operations without code write |
| Reviewers/learners | Read | Repositories needed for learning/review |
| Security response | Maintain/Admin only if incident role requires it | Restricted incident scope where supported |

Team candidates: Core Maintainers; Data Science and Analytics; ML Engineering; Software and Infrastructure; Security and QA; Documentation and Community. Create only teams with an actual function, maintainer and members. Review effective team/repository grants quarterly. Existing `cryo-crew` and `dev-team` should be mapped to actual project responsibilities before any change.

Onboarding: sponsor confirms role and repositories; verify MFA; grant least access; explain data/security/conduct/review practices; provide approved secret access only if necessary; test access; set review date.

Offboarding: transfer issues/releases/ownership; remove team and outside collaborator grants; revoke app/token access and credentials under owner control; rotate exposed shared credentials; verify access removal; record privately. Do not publish member rosters.
