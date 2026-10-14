---
title: Permissions, credits, and limits
---

Testing tool only does what **you** are allowed to do in Jira, and each chat request uses **your site's Rovo credits**. This app does not grant extra AI quota and does not bypass Jira permissions.

## Jira permissions the agent respects

Before it reads or writes, Testing tool checks the signed-in user:

| You want to                    | You need                                                                                                  |
| ------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Load an issue or draft from it | **Browse projects** (and see that issue)                                                                  |
| Create a TestCase              | **Create issues** in that project, and the project must be [TMS-ready](./make-project-tms-ready.md)       |
| Update steps on a TestCase     | **Edit issues** on that TestCase                                                                          |
| Delete an obsolete TestCase    | **Delete issues** on that TestCase. Delete is a **hard delete** of the Jira issue, only after you confirm |
| Summarize a project or cycle   | **Browse projects** on that project                                                                       |

If the check fails, the agent returns a neutral denial. It will not tell you whether the issue exists.

Site and project **admins** still own install, issue types, and Rovo enablement. Testing tool will not change permission schemes.

## Rovo must be on

- A site admin enables Rovo for the site.
- **Ask Rovo**, **Ask Testing tool**, and **Fill steps with Rovo** buttons are hidden when Rovo is off. That is intentional, not a broken control.
- You can still use Testing tool (design and runs) without Rovo.

## Credits

- Each Testing tool request consumes the customer's **Rovo credits** (about **10 per request**).
- This is not an unlimited "AI Testing Tool" or "Testing tool AI" entitlement.
- Longer chats cost more requests. Confirm-before-write avoids wasted create calls.

## Other limits you will feel

- **Jira only** — the agent cannot read a Confluence page as the requirement. Paste the text or point it at a Jira issue.
- **Issue context** — chat from the top nav has no issue. Give a project or issue key; the agent will not guess.
- **One confirmed write at a time** — create / update / delete run after you confirm that item. It will not silently bulk-create a whole split.
- **No run-result edits** — it will not mark TestExecution steps passed or failed.
- **Payload size** — long descriptions are truncated when it loads work context.

## FAQ

**Why did it say it cannot create a TestCase?**  
Missing **TestCase** work type, or you lack Create issues. Fix [Make a project TMS-ready](./make-project-tms-ready.md), or ask a project admin for create permission.

**Why did delete fail after I confirmed?**  
You do not have Delete issues on that TestCase. Confirm does not override Jira.

**Who pays for AI?**  
The Atlassian site that has Rovo, via Rovo credits. The Marketplace app does not bill a separate AI meter.

## Related

- [Install and open Testing tool](./install-and-open.md)
- [Make a project TMS-ready](./make-project-tms-ready.md)
- [What is Testing tool](./what-is-testing-tool.md)
- [Start here](../start-here.md)
