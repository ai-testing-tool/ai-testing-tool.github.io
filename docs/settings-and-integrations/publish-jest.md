---
title: Publish results from Jest
---

Add the **Testing tool Jest reporter** (`@ai-testing-tool/forge-jest`) in `jest.config` so each Jest run can publish results and autogenerate TestCases on ingest. Pair it with a [CI snippet](./publish-results-from-ci.md) from the template builder.

This reporter does not replace Test Design. Design you edit in Jira stays on the TestCase; a **new** launch clones a snapshot onto a TestExecution.

## Install

```bash
npm install -D @ai-testing-tool/forge-jest @ai-testing-tool/forge-commons
```

Package guide: [qa-jest](https://github.com/ai-testing-tool/testing-tool-js/tree/main/qa-jest).

## Configure

In `jest.config.js`:

```js
reporters: [
  'default',
  ['@ai-testing-tool/forge-jest', { /* mode / projectKey optional */ }],
],
```

Set `AI_TESTING_TOOL_MODE=ingest` plus project key, ingest URL, and token when the run should upload. Default mode is `off`. `file` writes an ingest payload locally.

Prefer **Jira issue keys in test titles**. Use `qa` helpers from `@ai-testing-tool/forge-jest/jest`. Run with `--runInBand` when you rely on those helpers so they share the reporter bridge.

## In Jira

1. Connect [ingest](./ci-ingest-url-and-token.md).
2. Open **Apps** → **Jest**. Follow **Open guide**, or **Setup** with Jest preselected.
3. Run Jest with `AI_TESTING_TOOL_MODE=ingest` after your test stage.

Optional Path A: `npx jest --json --outputFile=…` plus the CLI upload. Prefer the reporter unless you already have that JSON pipeline.

## FAQ

**Did ingest overwrite the steps I wrote in Test Design?**  
A new launch clones design onto a new TestExecution. Re-sync of the **same** launch does not re-clone.

## Related

- [Publish results from a test framework](./publish-results-from-a-test-framework.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Design a TestCase](../work-in-jira/design-a-testcase.md)
