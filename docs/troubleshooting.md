---
title: Troubleshooting
---

Use this page when Testing tool is missing, blocked, or refusing a write. Start with the symptom, then the fix. Names: **Testing tool** (project hub and agent), **Testing Agent** (Rovo picker).

## I cannot find Testing tool or Ask Testing tool

- No Chat / buttons hidden → Rovo is off on the site. Ask a site admin. Hidden is intentional.
- Agent listed as **Testing Agent** → same agent; product name is Testing tool.
- Apps → Rovo is inactive → preference only; it does not remove the agent. See [Find and open Testing tool](./ask-testing-tool/find-and-open.md).
- Toolbar **Help** missing → Rovo is off, or you are not on the Testing tool hub.

## Onboarding never clears / Launch is disabled

Issue types must be named exactly **Requirement**, **TestCase**, **TestExecution**, **Bug**. Link types must exist as **Coverage**, **Execution**, and **Found**. Click **Refresh**. See [Make a project TMS-ready](./setup/make-project-tms-ready.md).

## Testing tool will not create, update, or delete

- It is waiting for you to **confirm** that proposal item.
- Missing TestCase work type, or you lack Create / Edit / Delete issues. Confirm does not override Jira.
- Chat opened from the top nav with no key — give a project or issue key; it will not guess.
- Neutral denial: you cannot browse that issue (existence is not confirmed).
- Delete is a **hard delete** of the TestCase issue, not an unlink.

See [Permissions, credits, and limits](./setup/permissions-credits-limits.md).

## Ingest 401, 424, or CI setup unavailable

- Token rotated or never copied → set a new secret, or **Rotate** and update CI.
- **HTTP 424** after a Forge redeploy → **Recreate** the ingest URL on Setup, then update the URL secret. Token is unchanged. [CI ingest URL and token](./settings-and-integrations/ci-ingest-url-and-token.md).
- **CI setup unavailable** → connect ingest first.
- Launch visible, no TEs yet → wait for the toolbar **bell** / background jobs, then refresh Test execution (check **No test cycle**).

## CI push bell is empty or stuck

- You need **Testing tool** open for that project while the push lands. See [CI push notifications](./settings-and-integrations/ci-push-notifications.md).
- Confirm ingest posted (401/424 fixes above). Look under Test execution for new runs.

## README badge is red or broken

- No launch for that **project** / **gitBranch** yet, or sync failed → check Test execution and the bell. Confirm CI sends `gitBranch` on ingest.
- Badge URL must include `format=svg`. Status GET needs **no** token; do not put the ingest token in the image URL.
- See [README sync status badge](./settings-and-integrations/readme-sync-status-badge.md).

## Coverage is zero on a story

The **Cycle traceability** panel counts **linked test cycles**, not requirement↔TestCase links. [See coverage on a story or epic](./work-in-jira/see-coverage.md).

## Pad does not show my new design step

That launch already cloned the old design. Start a **new** launch. [Use Test Pad](./work-in-jira/use-test-pad.md).

## Pad or status is locked

**Test type** is **Automated**. CI owns design and results. Switch the TestCase to **Manual** only if you need to edit design or record Pad results yourself. See [TestCase issue panel](./work-in-jira/testcase-issue-panel.md).

## Excel import failed

Over **50** rows or **2 MiB**, or validation errors on headers/types. Fix the sheet; import does not write until validation passes. [Import and export TestCases](./work-in-jira/import-and-export.md). Watch the toolbar for background job progress after a successful upload.

## FAQ

**Does this app give unlimited AI?**  
No. About **10 Rovo credits** per agent request.

**Can the agent read a Confluence requirement page?**  
Not in this version. Paste the text or point it at a Jira issue.

## Related

- [Start here](./start-here.md)
- [Glossary](./glossary.md)
