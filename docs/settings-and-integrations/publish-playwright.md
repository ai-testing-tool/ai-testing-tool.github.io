---
title: Publish results from Playwright
---

Add the **Testing tool Playwright reporter** (`@ai-testing-tool/forge-playwright`) so each Playwright run can publish results and autogenerate TestCases on ingest. Pair it with a [CI snippet](./publish-results-from-ci.md) from the template builder.

This reporter does not replace Test Design. Design you edit in Jira stays on the TestCase; a **new** launch clones a snapshot onto a TestExecution.

## Install

```bash
npm install -D @ai-testing-tool/forge-playwright @ai-testing-tool/forge-commons @playwright/test
```

Peer: `@playwright/test` ≥1.40. Package guide: [qa-playwright](https://github.com/ai-testing-tool/testing-tool-js/tree/main/qa-playwright).

## Configure

In `playwright.config.js`, add the reporter next to `list` (or your existing reporters):

```js
reporter: [
  ['list'],
  ['@ai-testing-tool/forge-playwright', { /* mode / projectKey optional */ }],
],
```

Set `AI_TESTING_TOOL_MODE=ingest` plus project key, ingest URL, and token when the run should upload. Default mode is `off` (no network). `file` writes an ingest payload locally.

Prefer **Jira issue keys in test titles**. Use native Playwright `test.step()` — do not use `qa.step()`.

## In Jira

1. Connect [ingest](./ci-ingest-url-and-token.md).
2. Open **Apps** → **Playwright**. Follow **Open guide**, or **Setup** with Playwright preselected.
3. Run Playwright with `AI_TESTING_TOOL_MODE=ingest` after your test stage.

Optional Path A: emit Playwright JSON and upload with the CLI. Prefer the reporter (`mode=ingest` or `file`) unless you already have that JSON pipeline.

## FAQ

**Did ingest overwrite the steps I wrote in Test Design?**  
A new launch clones design onto a new TestExecution. Re-sync of the **same** launch does not re-clone.

## Related

- [Publish results from a test framework](./publish-results-from-a-test-framework.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Design a TestCase](../work-in-jira/design-a-testcase.md)
