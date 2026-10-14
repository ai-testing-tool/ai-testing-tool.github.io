---
title: Install and open Testing tool
---

A Jira admin installs this Forge app on the site. After install, each project opens **Testing tool** from the project navigation — that hub is where you design cases, run cycles, and open the Rovo agent.

## Install on the site

1. A Jira admin installs the app from the Atlassian Marketplace (or from a private distribution link your vendor sent).
2. Approve the requested Jira permissions when prompted.
3. Confirm the app appears under **Apps** / **Manage apps** on the site.

You do not install the agent separately. The Rovo agent ships with the same app. The **site** must also have Rovo enabled, or Ask CTAs stay hidden. See [Permissions, credits, and limits](./permissions-credits-limits.md).

## Open Testing tool in a project

1. Open a Jira software project where you want test management.
2. In the project navigation, open **Testing tool** (the app project page).
3. If issue types are not ready, you will see onboarding instead of Requirements / Test design. Continue with [Make a project TMS-ready](./make-project-tms-ready.md).
4. When types are ready, click **Launch Testing tool For Jira** (or you land directly in the hub).

From the hub you can open **Requirements**, **Test design**, **Test execution**, and **Apps** (catalog; CI setup from an app’s **Setup** action). The toolbar also has a CI push **bell**, background job progress, Help (opens the agent when Rovo is on), and **More** for Excel import/export.

## Open the agent after install

Install alone does not open the agent. Use [Find and open Testing tool](../ask-testing-tool/find-and-open.md): Rovo Chat → **Testing Agent**, Help on the Testing tool toolbar, or the Ask CTAs (**Ask Rovo** on Requirements and Test design, **Ask Testing tool** on Cycle traceability, **Fill steps with Rovo** on a Manual TestCase).

## FAQ

**I installed the app but I do not see Testing tool.**  
You may be in a project the app does not extend, or you need to refresh the project. Confirm the app is installed for Jira on this site, then reopen the project.

**I see Testing tool but no Ask CTA.**  
Rovo is off on the site, or you are on a screen without a CTA. Use Rovo Chat and pick **Testing Agent**, or the Help icon when it is shown.

**Does Apps → Rovo Active install the agent?**  
No. That Project Integration toggle is a per-project preference. The agent is already part of the installed app.

## Related

- [Start here](../start-here.md)
- [Make a project TMS-ready](./make-project-tms-ready.md)
- [Permissions, credits, and limits](./permissions-credits-limits.md)
- [Find and open Testing tool](../ask-testing-tool/find-and-open.md)
