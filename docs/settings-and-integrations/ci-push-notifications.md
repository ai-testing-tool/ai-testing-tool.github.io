---
title: CI push notifications
---

When a CI job posts results to this project, the Testing tool toolbar shows live notifications on the **bell** icon. You see when a push is received, when it finishes syncing into Jira, or when sync fails — without leaving the hub.

## Open notifications

1. Open the project **Testing tool** page.
2. In the toolbar (next to Help), click the **bell** icon.
3. Read the list. Unread rows stay highlighted until you open them or choose **Clear all**.

A badge on the bell shows how many unread items you have. An empty list means no CI pushes have arrived while this page session is subscribed.

## What each kind means

| Lozenge    | Meaning                                                                                  |
| ---------- | ---------------------------------------------------------------------------------------- |
| **New**    | Ingest accepted the launch. Jira fan-out may still be running.                           |
| **Synced** | Fan-out finished. TestCases / TestExecutions / defects from that launch are in Jira.     |
| **Error**  | Sync failed. Confirm the ingest URL and token, then check Test execution for the launch. |

Each row can show launch name (link to the CI build when the payload included a build URL), CI platform and framework, pass/fail totals, and sync counts (TestCases created / linked / updated, defects).

## When you get them

You must have **Testing tool** open for this project. Notifications arrive over Forge realtime for the current project only. Closing the page or switching projects stops the live feed for that session; open Testing tool again to keep watching.

They are separate from Jira email/watch notifications and from the toolbar **background job** progress (Excel import, create test runs, and similar).

## FAQ

**I ran CI but the bell stays empty.**  
Confirm ingest posted successfully ([CI ingest URL and token](./ci-ingest-url-and-token.md)) and that you are on the same project’s Testing tool page. Refresh the page if you opened the hub before the push. Check **Test execution** (often under **No test cycle**) for new runs.

**Synced said OK but I do not see TestExecutions.**  
Open **Test execution** and refresh. Look under the relevant cycle or **No test cycle**.

**Does Active on an Apps catalog card control this?**  
No. Notifications follow ingest + sync for the project, not the Active preference.

## Related

- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [README sync status badge](./readme-sync-status-badge.md)
- [Apps catalog](./apps-catalog.md)
- [Start here](../start-here.md)
