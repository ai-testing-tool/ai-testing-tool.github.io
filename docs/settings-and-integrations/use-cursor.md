---
title: Use Cursor with Testing tool
---

Use **Cursor** with Testing tool by connecting **[Atlassian Rovo MCP](https://support.atlassian.com/atlassian-ai-gateway/docs/get-started-with-the-atlassian-remote-mcp-server/)** so the IDE agent can create, update, and query TestCases and inspect reports. Turning **Cursor** **Active** in Apps is a preference only — it does not register the MCP server.

For chat **inside Jira**, use the **Testing tool** Rovo agent, not Cursor. See [Find and open Testing tool](../ask-testing-tool/find-and-open.md).

## What Cursor is for

- Manage TestCases with AI (create / update / query via MCP tools)
- Inspect test reports / run insights
- Run the same kinds of Testing tool workflows from the IDE when tools are available in the MCP session

Tools become callable when Atlassian Rovo MCP is connected in Cursor and authenticated, and Testing tool is installed on your site.

## In Jira and Cursor

1. Open **Testing tool** → **Apps**.
2. Open **Cursor**.
3. Under **Actions & Documentation**, open **Open Atlassian Rovo MCP guide** ([get started](https://support.atlassian.com/atlassian-ai-gateway/docs/get-started-with-the-atlassian-remote-mcp-server/)).
4. In Cursor, add Atlassian Rovo MCP (`https://mcp.atlassian.com/v2/mcp`). Follow Cursor’s connection UI and complete OAuth.

## Agent skills / IDE plugins

Install agent skills from **[Testing Tool IDE Plugins](https://github.com/ai-testing-tool/testing-tool-ide-plugins)** (Cursor local plugin or project skills). Skills teach agent behavior (confirm-before-write, TestCase workflows); they do not register MCP. See the pack’s [Cursor install guide](https://github.com/ai-testing-tool/testing-tool-ide-plugins/blob/main/docs/install/cursor.md).

## FAQ

**I set Cursor Active. Why does the IDE not see tools?**  
Active never registers MCP. Add [Atlassian Rovo MCP](https://support.atlassian.com/atlassian-ai-gateway/docs/get-started-with-the-atlassian-remote-mcp-server/) in Cursor, authenticate, and ensure Testing tool is installed on your site.

**Should I use Cursor or Testing tool in Jira Chat?**  
For create/update/delete of TestCases in this project from Jira, pick **Testing tool** so confirm-before-write and permission checks run. Cursor is a separate client when MCP is connected.

## Related

- [Use Cursor, Copilot, or Claude with Testing tool](./cursor-copilot-claude.md)
- [Apps catalog](./apps-catalog.md)
- [What is Testing tool](../setup/what-is-testing-tool.md)
