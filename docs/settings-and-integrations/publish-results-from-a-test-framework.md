---
title: Publish results from a test framework
---

Pick the reporter for your test runner. Each page covers install, config, and how ingest creates launches. Pair the reporter with a [CI snippet](./publish-results-from-ci.md) from the template builder.

Reporters do not replace Test design. They upload run results. Design you edit in Jira stays on the TestCase; a **new** launch clones a snapshot onto a TestExecution. New TestCases created by ingest start as **Automated**.

## In this section

- [Publish results from Playwright](./publish-playwright.md)
- [Publish results from Mocha](./publish-mocha.md)
- [Publish results from Jest](./publish-jest.md)
- [Publish results from Cypress](./publish-cypress.md)
- [Publish results from Vitest](./publish-vitest.md)
- [Publish results from WebdriverIO](./publish-wdio.md)

Shared capabilities: create test runs via reporter, publish results to Testing tool, autogenerate TestCases on ingest.

## In Jira (any reporter)

1. Connect [ingest](./ci-ingest-url-and-token.md).
2. Open **Apps**, open your framework app, follow **Open guide**, or **Setup** (template builder with that framework preselected).
3. Set `AI_TESTING_TOOL_MODE=ingest` (or the equivalent in the package README) so the reporter uploads when the run finishes.

## FAQ

**Did ingest overwrite the steps I wrote in Test design?**  
A new launch clones design onto a new TestExecution. Re-sync of the **same** launch does not re-clone. Editing the TestCase design does not rewrite an in-progress TE. CI-created cases are **Automated** (design and Pad locked).

## Related

- [Apps catalog](./apps-catalog.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Design a TestCase](../work-in-jira/design-a-testcase.md)
- [Start here](../start-here.md)
