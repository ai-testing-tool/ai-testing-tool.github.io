---
title: See coverage on a story or epic
---

The **Cycle traceability** panel appears on Jira issues that are **not** a TestCase and **not** a TestExecution — stories, epics, and other work items. You link **test cycles** to the issue and see coverage for those cycles' TestCase members.

Coverage comes from linked cycles only (members + latest run status). It does not read TestCase design steps or Test Pad actuals as the coverage model.

On the same issue types you also get a **QA Checklist** panel: a per–TestCase list from Coverage links and/or linked-cycle members, with design step count and latest run status/executor. Expand a TestCase row to see its test runs (one row per TestExecution) and change a run’s status when a TestExecution exists.

## Open the panel

1. Open a story, epic, or other non-TestCase / non-TestExecution issue.
2. Find the **Cycle traceability** panel (full view and issue modal). It loads on its own.
3. Click **Link test cycles** and choose one or more cycles. Links persist.
4. **Unlink** a cycle (or linked project group) when it should no longer count.

With links, you see at least **TOTAL TEST RUNS**, **EXECUTED**, and **UNEXECUTED** (plus the status bar the panel shows). With no links or no members: empty or zero — not an error.

![Cycle traceability on a story with linked test cycles and coverage counts](./media/see-coverage--test-results-panel.png)

## Ask Testing tool from a story

Use **Ask Testing tool** on this panel (hidden if Rovo is off) to draft TestCases from the issue. Creating cases is not the same as linking a cycle. After cases exist, add them to a cycle, then link that cycle here for coverage.

## FAQ

**Why is this panel missing on a TestCase?**  
TestCases use the **Test design** panel. TestExecutions use the **Test execution** panel.

**I linked a Requirement's TestCases. Why is coverage still zero?**  
This panel counts **cycles**, not requirement links. Create or pick a test cycle that contains those cases, then link that cycle.

## Related

- [Manage requirements](./manage-requirements.md)
- [Run a test cycle](./run-a-test-cycle.md)
- [Find and open Testing tool](../ask-testing-tool/find-and-open.md)
- [Start here](../start-here.md)
