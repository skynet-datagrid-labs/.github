# Client apps and integrations inventory

**Checked:** 26 October 2026. No application was installed or removed during this review.

## GitHub Apps

The organization has one installed GitHub App: **CodeRabbit**. It is installed for **all repositories** and has these permissions:

- Read: Actions, Discussions, Members, Metadata.
- Write: Checks, Contents, Issues, Pull Requests, and Commit Statuses.

This is a broad repository-wide integration because it can write code, issues, pull requests, checks, and statuses. It is currently used for automated PR review. Keep it only while maintainers want this workflow; organization owners should periodically verify repository selection, permissions, and app activity under **Organization Settings → Third-party Access → GitHub Apps**. No change was made because removing or narrowing the installation could disrupt active review workflows and needs owner review.

## OAuth applications and organization Actions policy

The current token can list installed GitHub Apps, but GitHub returned HTTP 403 for organization Actions-policy endpoints and requires `admin:org` scope. OAuth app access restrictions were not confirmed. Do not infer that no OAuth apps are authorized from the GitHub App installation list.

Organization owners can review **Settings → Third-party Access → OAuth app policy** and **Settings → Actions**. Check the approved OAuth applications, repository selection, granted scopes, action allow-list, and workflow token defaults. Revoke only after confirming the app is unused and that dependent workflows have a replacement.

## Other integrations

No additional organization-installed GitHub Apps were returned. No integration was installed for CI, project management, or collaboration during this review. GitHub Actions dynamic workflows seen in repositories are not evidence of an installed third-party app.
