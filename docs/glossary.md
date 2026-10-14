---
title: Glossary
---

This glossary is the vocabulary for Testing tool. Use these names in Rovo and in Jira so answers stay consistent.

## Product names

**Testing tool**  
The Jira project page (Requirements, Test design, Test execution, Apps) and the conversational name for the Rovo agent. Same Forge app: **AI Testing Tool**.

**Testing Agent**  
The Rovo Chat picker label for the agent. Prefer **Testing tool** in conversation.

**AI Testing Tool**  
Forge app / Marketplace name. Prefer **Testing tool** in conversation.

## Work types (names are case-sensitive)

**Requirement**  
A Jira issue that describes a need. You link TestCases to it.

**TestCase**  
A Jira issue that holds **design**: summary, preconditions, postconditions, and steps (action, optional data, expected result).

**TestExecution**  
A Jira issue that holds one **run** of a TestCase. Steps are a snapshot. Editing a run does not change the TestCase design.

**Bug**  
A defect linked from a failed run or from a TestCase.

## Design and execution

**Suite**  
A folder in Test design that groups TestCases.

**Test cycle** (also called a plan)  
A set of TestCases you intend to run together, with progress counts.

**No test cycle**  
System plan in Test execution for TestExecutions that are not on a named cycle (including unbound CI runs). Deleting a named cycle moves its runs here. You do not create or rename it.

**Test type**  
**Manual** or **Automated** on a TestCase (copied to new TestExecutions at create). UI/Excel create → Manual; CI create → Automated. Manual = editable design and Pad. Automated = design/status locks and a **CI/CD builds** tab.

**Test Pad**  
The step-by-step runner. On Manual runs, status and actual results are written on the TestExecution snapshot only. Automated Pad is view-only.

**Launch**  
One upload or manual run batch. A new launch creates new TestExecutions; re-syncing the same launch reuses those TestExecutions.

**Ingest**  
The project URL and token CI or a reporter uses to publish results into Testing tool.

**README sync status badge**  
A public SVG image (CircleCI-style) from the ingest URL that shows whether the latest launch for a branch has finished syncing to Jira. No token. Copy from **Apps → Setup → README status badge**.

**CI push notifications**  
Toolbar **bell** on Testing tool. Live New / Synced / Error when CI posts and fan-out finishes for this project. See [CI push notifications](./settings-and-integrations/ci-push-notifications.md).

## Apps and AI

**Apps catalog**  
**Apps** tab listing CI platforms, test frameworks, AI agents, and coding tools. **Active** / Project Integration is a per-project preference. It does not install or remove the Rovo agent. CI ingest and the template builder open from an app’s **Setup** action.

**Ask Testing tool**  
CTAs that open Testing tool in the Rovo sidebar. Labels vary by surface: **Ask Rovo** (Requirements and Test design), **Ask Testing tool** (Cycle traceability on a story/epic), **Fill steps with Rovo** (Manual TestCase **Test design** panel). The toolbar **Help** icon does the same when Rovo is enabled.

**Rovo credits**  
Your site's Atlassian AI allowance. Testing tool requests consume these (about 10 per request). This app does not sell unlimited AI.

**Proposal / confirm**  
Testing tool shows a draft and a recommended action (create, update, delete, split, or ask for more context). It only writes after you confirm that item.

**Hard delete**  
Confirmed delete removes the TestCase Jira issue. It is not an unlink or an archive.

## FAQ

**Why did Testing tool ask me for a project or issue key?**  
Chat opened without issue context. Give a key; do not expect it to pick one.

**Why did it refuse to create a TestCase?**  
The project is missing the **TestCase** work type, or you do not have create permission. See Apps onboarding, then Refresh.

## Related

- [Start here](./start-here.md)
- [What is Testing tool](./setup/what-is-testing-tool.md)
- [Find and open Testing tool](./ask-testing-tool/find-and-open.md)
