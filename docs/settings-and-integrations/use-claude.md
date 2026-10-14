---
title: Use Claude with Testing tool
---

Use **Claude** with Testing tool by connecting **[Atlassian Rovo MCP](https://support.atlassian.com/atlassian-ai-gateway/docs/get-started-with-the-atlassian-remote-mcp-server/)** so the agent can manage TestCases and reports from the IDE. Turning **Claude** **Active** in Apps is a preference only — it does not register MCP by itself.

For chat **inside Jira**, use the **Testing tool** Rovo agent, not Claude-in-IDE or Claude in Jira Chat. See [Find and open Testing tool](../ask-testing-tool/find-and-open.md).

## What Claude is for

- Manage TestCases with AI (create / update / query via MCP tools)
- Inspect test reports / run insights
- Run Testing tool workflows from Claude when tools are available in the MCP session

Tools become callable when Atlassian Rovo MCP is connected in Claude and authenticated, and Testing tool is installed on your site.

## In Jira and Claude

1. Open **Testing tool** → **Apps**.
2. Open **Claude**.
3. Under **Actions & Documentation**, open **Open Atlassian Rovo MCP guide** ([get started](https://support.atlassian.com/atlassian-ai-gateway/docs/get-started-with-the-atlassian-remote-mcp-server/)).
4. In Claude, add Atlassian Rovo MCP (`https://mcp.atlassian.com/v2/mcp`). Follow Claude’s MCP connection UI and complete OAuth.

## Agent skills / IDE plugins

Install agent skills from **[Testing Tool IDE Plugins](https://github.com/ai-testing-tool/testing-tool-ide-plugins)** (e.g. `.claude/skills/`). Skills teach agent behavior; they do not register MCP. See the pack’s [Claude install guide](https://github.com/ai-testing-tool/testing-tool-ide-plugins/blob/main/docs/install/claude.md).

## FAQ

**I set Claude Active. Why does the agent not see tools?**  
Active never registers MCP. Add [Atlassian Rovo MCP](https://support.atlassian.com/atlassian-ai-gateway/docs/get-started-with-the-atlassian-remote-mcp-server/) in Claude, authenticate, and ensure Testing tool is installed on your site.

**Should I use Claude in Jira Chat or Testing tool?**  
For create/update/delete of TestCases in this project, pick **Testing tool** so confirm-before-write and permission checks run. Claude-in-IDE is a separate client when MCP is connected.

## Related

- [Use Cursor, Copilot, or Claude with Testing tool](./cursor-copilot-claude.md)
- [Apps catalog](./apps-catalog.md)
- [What is Testing tool](../setup/what-is-testing-tool.md)
