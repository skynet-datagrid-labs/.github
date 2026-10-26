# Manual actions requiring owner or maintainer review

1. Add `read:project`/project permissions to the GitHub authentication used for audit, then inventory existing org projects before creating anything. Current GraphQL call was blocked by missing `read:project`.
2. Decide whether and when to require MFA organization-wide; current setting is disabled. Communicate and allow members to enroll first; retain recovery/owner access.
3. Review member privileges: repository creation, deletion, visibility changes and outside collaborator invitations are currently enabled. Consider reducing these after owner review and member workflow assessment.
4. Verify per-repository security feature availability on the Free plan and enable appropriate Dependabot alerts/updates, secret scanning, push protection, CodeQL or other scanning.
5. Inspect CodeQL/Dependency Graph runs and add language-specific CI after reviewing current manifests and workflows.
6. Pilot `main` branch protection/rules on a repository after confirming successful check names and reviewer availability.
7. Map existing teams and repository grants to current responsibilities; this package does not recommend changing memberships without review.
8. Review proposed profile README against current portfolio; existing profile contains projects/metrics not present in accessible inventory. Update only after owners validate claims.
9. Select licenses only with rights-holder approval; no license was added.
10. Publish templates and governance docs through a reviewed PR to `.github` or a designated repository. This local package has not been pushed.

## Remaining owner actions after implementation

- In organization Settings → Member privileges, disable member repository deletion, visibility changes, and outside collaborator invitations if approved; API read-after-write did not change them.
- Verify member 2FA enrollment privately; then enable organization MFA requirement with recovery/access plan. Current member API omits enrollment status.
- Obtain
ead:project and project write access; inspect existing Projects v2 before creating a portfolio board.
- Review and apply branch protection only after checks and reviewer capacity are verified.


## Status of actions above

The governance documents and profile update were published by PR #1. Non-admin repository/team creation was disabled and verified. The other listed items remain owner follow-up, project-scope blockers, or staged engineering work as described in the audit report.
