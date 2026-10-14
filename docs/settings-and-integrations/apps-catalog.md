---
title: Apps catalog
---

**Apps** is the catalog for this project. It lists supported CI platforms, test frameworks, AI agents, and AI coding tools. **Active** (Project Integration) is a per-project preference only — it does not change ingest, install Testing tool, or register MCP.

## Open Apps

1. Open **Testing tool** → **Apps** (or the Apps toolbar icon when you are on another tab).
2. Search by name or keyword, or browse sections (**CI pipelines**, **Test frameworks**, **AI agents**, **Coding tools**).
3. Open an app. Detail shows **What this application can do** and **Actions & Documentation**.
4. Toggle **Project Integration** if you want the catalog to remember what this project uses.

## What Active does not do

| App kind                                                                      | Active does **not**                                       |
| ----------------------------------------------------------------------------- | --------------------------------------------------------- |
| CI (GitHub Actions, GitLab CI, Azure Pipelines, Bitbucket Pipelines, Jenkins) | Revoke ingest tokens or block CI upload                   |
| Framework (Playwright, Mocha, Jest, Cypress, Vitest, WDIO)                    | Install the reporter in your repo                         |
| AI agent (Rovo)                                                               | Install or remove Testing tool. The site still needs Rovo |
| Cursor, GitHub Copilot, Claude                                                | Enable MCP registration by itself                         |

## Next step from an app

- CI or framework: **Setup** opens ingest + CI template builder for that platform or framework (app must be Active). Use **Open guide** for package or platform docs.
- AI agent (Rovo): **Test it** opens Testing tool — then [Find and open Testing tool](../ask-testing-tool/find-and-open.md).
- Coding tool: **Open Atlassian Rovo MCP guide** — [Cursor](./use-cursor.md), [GitHub Copilot](./use-github-copilot.md), or [Claude](./use-claude.md).

From Setup you can return to the app detail or back to the Apps list. New projects default all catalog apps to Active unless you turn them off.

## FAQ

**I turned Rovo off in Apps. Why is the agent still in Chat?**  
The agent ships with the installed Forge app. Active is only a preference badge.

**Why is Setup disabled on an app?**  
The app is inactive in this project. Enable **Project Integration**, then use Setup. Ingest must still be connected for the template builder — see [CI ingest URL and token](./ci-ingest-url-and-token.md).

**Where did the Settings tab go?**  
The hub tab is **Apps**. Open a CI or framework app and choose **Setup** for ingest and the template builder. Live CI feedback is the toolbar **bell** — see [CI push notifications](./ci-push-notifications.md).

## Related

- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [CI push notifications](./ci-push-notifications.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Start here](../start-here.md)
