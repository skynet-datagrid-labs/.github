# Team administration and access matrix

## Current structure

Two closed teams exist:

| Team | Observed purpose | Repository grant | Recommended access |
|---|---|---|---|
| `cryo-crew` | Kaggle Spaceship Titanic project team | `alpha-centauri-rescue`: Read (`pull`) | Keep Read for review; grant Write only to members actively maintaining code, after approval |
| `dev-team` | Development collaboration team | `sales-intelligence-dashboard`: Read (`pull`) | Keep Read for review; grant Write only when active contributors and maintainers agree |

No other team repository grants were returned. No new teams were created and no membership or existing permission was changed. Team member names are intentionally not published here.

## Least-privilege model

| Role | Suggested permission | Use |
|---|---|---|
| Organization owner | Organization Admin | Account security, billing, organization policies, owner recovery |
| Repository maintainer | Maintain; Admin only for trusted repository stewards | Reviews, issues, releases, repository settings |
| Active contributor | Write | Scoped code and documentation changes |
| Triage helper | Triage | Issue/PR labels and discussion without code write |
| Reviewer or learner | Read | View, discuss, and review public work |

The organization default permission is `none`. Non-admin repository and team creation is disabled. Members can still delete or transfer repositories, change visibility, and invite outside collaborators under current organization settings; an owner should review those controls. The authenticated account has an active organization `admin` role. The member-list API returned 20 accounts for its `role=admin` filter, but did not distinguish owners from other administrators in this response; confirm named owners in **Organization Settings → Organization roles** before owner-only changes.

## Membership procedures

**Onboarding:** sponsor confirms role and repositories; verify MFA; grant access through the smallest appropriate team; explain data, contribution, security, and conduct rules; provide secrets only through approved stores; set a review date.

**Role change:** confirm the new responsibilities with maintainers, adjust only the relevant repository/team grant, verify effective access, and record the reason in a private administrative record.

**Offboarding:** confirm work and ownership transfer; remove team/outside collaborator access only with approval; revoke app/token grants and credentials through their owners; verify access removal. Do not publish member rosters.

**Quarterly review:** owners review organization owners/admins, team rosters, outside collaborators, repository grants, installed apps, and stale access. Sensitive membership and ownership changes require explicit owner approval.
