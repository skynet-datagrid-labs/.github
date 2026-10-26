# Security incident response runbook

**Purpose:** contain and recover from credential exposure, unauthorized access, malicious workflow/dependency, or sensitive data publication. **Authority:** organization owner and designated security contact; assign these functions privately.

1. Receive report privately; acknowledge and avoid copying secrets into issues/logs.
2. Establish incident coordinator, scope, timeline, affected repos/accounts/data, and severity.
3. Contain: revoke exposed credential, restrict affected deployment/workflow or access if authorized, preserve audit evidence. Rotate dependent credentials as required.
4. Remediate: remove vulnerable code/data, patch dependencies, review history exposure and downstream copies, test fix in controlled branch.
5. Recover: release fix, restore known-good service/data, verify access and monitoring, notify impacted parties as appropriate.
6. Review: timeline, root cause, impact, controls, corrective action owners and due dates; keep sensitive details restricted.

Verification: confirm old credentials fail, patched revision deployed, relevant alerts clear, and recovery integrity checked. Rollback: restore last known-good deployment/ref from verified backup while preserving forensic evidence. Never assume deleting a file from HEAD removes it from Git history or invalidates a secret.
