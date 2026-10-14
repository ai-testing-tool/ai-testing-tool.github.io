---
title: Use Cursor, Copilot, or Claude with Testing tool
---

Cursor, GitHub Copilot, and Claude connect through the **[Atlassian Rovo MCP Server](https://support.atlassian.com/atlassian-ai-gateway/docs/get-started-with-the-atlassian-remote-mcp-server/)** (`https://mcp.atlassian.com/v2/mcp`) so agents can manage TestCases and reports from the IDE. Turning an app **Active** in Apps is a preference only — it does not register or authenticate MCP.

For chat **inside Jira**, use the **Testing tool** Rovo agent, not these IDE tools. See [Find and open Testing tool](../ask-testing-tool/find-and-open.md).

## In this section

- [Use Cursor with Testing tool](./use-cursor.md)
- [Use GitHub Copilot with Testing tool](./use-github-copilot.md)
- [Use Claude with Testing tool](./use-claude.md)

## Agent skills / IDE plugins

For portable agent instructions (confirm-before-write, TestCase workflows) across Cursor, Claude, and Copilot, use:

**[Testing Tool IDE Plugins](https://github.com/ai-testing-tool/testing-tool-ide-plugins)** — skills teach agent behavior; this guide owns human MCP setup. Connect Atlassian Rovo MCP in the IDE first. **Active** in Apps does not register MCP.

## Shared capabilities

- Manage TestCases with AI (create / update / query via MCP tools available in the session)
- Inspect test reports / run insights when those tools are available
- Prefer Testing tool–specific tools when they appear; otherwise use Atlassian platform tools carefully

If tools are not callable yet, confirm Atlassian Rovo MCP is connected and authenticated, and that Testing tool is installed on the site.

Rovo’s catalog card is different: it is the in-Jira agent. Active there does not install or remove Testing tool. The site must have Rovo enabled.

## Related

- [Testing Tool IDE Plugins (agent skills)](https://github.com/ai-testing-tool/testing-tool-ide-plugins)
- [Apps catalog](./apps-catalog.md)
- [What is Testing tool](../setup/what-is-testing-tool.md)
- [Start here](../start-here.md)
