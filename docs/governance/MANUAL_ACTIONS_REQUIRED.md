# Manual actions requiring owner or maintainer review

1. Complete the user-approved GitHub authorization for `read:project` and `project`; then inspect the three existing organization Projects before configuring one. The current CLI still reports only `gist`, `read:org`, `repo`, and `workflow` scopes.
2. Review member MFA readiness privately before enabling the organization MFA requirement; the member API does not expose enrollment status.
3. Repository deletion/transfer and visibility changes remain available to members; user approved making these owner-only, but read-after-write still shows the settings enabled. Complete this in organization Member privileges and verify. Outside-collaborator restrictions were not approved.
4. Review CodeQL setup and plan suitable CI after inspecting project source and workflows. No dependency manifests were found in the four repository trees.
5. Pilot `main` branch protection/rules only after confirming successful check names and reviewer availability; these controls can block work.
6. Map existing teams and repository grants to current responsibilities; do not change memberships without owner review.
7. Review the corrected profile README and current community guidance in this branch before merging.
8. Select licenses only with rights-holder approval; no license was added.

## Status

The governance baseline and profile were published by PR #1. Non-admin repository/team creation was disabled and verified. Repository security controls and new-repository defaults are enabled and verified. Remaining actions are the pending project authorization, owner UI changes that did not take through the API, MFA readiness, and review/publication of this corrective documentation update.
