---
title: Find and open Testing tool
---

You open Testing tool from Rovo Chat, the project hub **Help** icon, or the Ask CTAs inside the hub (**Ask Rovo**, **Ask Testing tool**, **Fill steps with Rovo**). The agent only appears when Rovo is enabled on the site.

## From Rovo Chat

1. Click **Chat** in the Jira top navigation.
2. Open the agent picker.
3. Choose **Testing Agent** (product name: **Testing tool**).
4. Use a starter, or ask in your own words (for example, "Generate TestCase proposals for this issue").

If you opened chat from an issue, Testing tool already has that issue as context. If you opened chat from the top nav with no issue open, tell it the project or issue key — it will not guess.

## From the project hub

1. Open the project **Testing tool** page.
2. Click the toolbar **Help** (question-circle) icon — or click **Ask Rovo** on **Requirements** or **Test design**.

The sidebar opens Testing tool with the current project (Requirements / Test design / Help) or the issue when that CTA includes it (issue panels).

## From a Jira issue

- On a **story or epic** (not a TestCase or TestExecution): use **Ask Testing tool** on the **Cycle traceability** panel.
- On a **Manual TestCase** issue: use **Fill steps with Rovo** on the **Test design** panel (hidden for Automated or when Rovo is off).

## Conversation starters

- Generate TestCase proposals for this issue
- Fill missing steps for this TestCase
- Summarize testing progress for this project

## If you cannot find it

- **No Chat / no Rovo** — the site does not have Rovo enabled. Ask a site admin. Ask CTAs and Help stay hidden on purpose.
- **No Testing tool page** — the app is not installed on this site, or you are not in a project where it is available.
- **Buttons missing on a project that already uses Testing tool** — Rovo is off, or you are on a surface that does not have a CTA yet. Use Rovo Chat and pick **Testing Agent**.
- **Agent is listed as Testing Agent** — same agent; use it. The product name is **Testing tool**.

## FAQ

**Do I have to pick Testing Agent, or will default Rovo know?**  
Default Rovo can point you here if this knowledge folder is attached as Rovo knowledge. For create/update/delete of TestCases, switch to **Testing Agent** so the right actions run.

**Does turning an app Active in Apps install the agent?**  
No. Apps → Rovo Active is a per-project preference. The agent is part of the installed Forge app. The site still needs Rovo.

## Related

- [Start here](../start-here.md)
- [What is Testing tool](../setup/what-is-testing-tool.md)
- [Glossary](../glossary.md)
