---
title: What is Testing tool
---

Testing tool is the Jira test-management app and its Rovo agent. Use the project page to manage cases and cycles, and the agent to draft, update, and summarize TestCases — it is not a separate website.

The Forge / Marketplace name is **AI Testing Tool**. In Rovo Chat the picker shows **Testing Agent**. Prefer **Testing tool** in conversation.

## What you can do

- Generate TestCase proposals from a Jira issue, its linked issues, or requirement text you paste in chat
- Fill missing steps, preconditions, or postconditions on an existing Manual TestCase
- Create, update, or delete a TestCase **after you confirm** in the conversation
- Summarize stored test-cycle / plan progress for the project

## What it will not do

- Change TestExecution run results or mark steps passed/failed on its own
- Write or delete anything until you explicitly confirm that item
- Invent Jira issue keys or steps that were not in the fetched data or text you provided
- Work if Rovo is off on the site, or if the project is missing the **TestCase** work type

## How it fits with the rest of the app

- **Testing tool** (project page) — Requirements, Test design, Test execution, and Apps
- **Issue panels** — Test design on TestCase issues, Test execution on TestExecution issues, Cycle traceability on stories and epics
- **Testing Agent** — the Rovo agent you open from chat, Help, or Ask CTAs (**Ask Rovo** / **Ask Testing tool** / **Fill steps with Rovo**)

## FAQ

**Is Testing tool a different product from the project hub?**  
No. Same app. The project page and the agent share the name **Testing tool**.

**Does this app give me unlimited AI?**  
No. Each agent request uses your site's Rovo credits (about 10 per request).

**Can I use it from Confluence?**  
Not in this version. Point the agent at a Jira issue, or paste the requirement into chat.

## Related

- [Start here](../start-here.md)
- [Find and open Testing tool](../ask-testing-tool/find-and-open.md)
- [Glossary](../glossary.md)
