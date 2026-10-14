---
title: Publish results from Vitest
---

Add the **Testing tool Vitest reporter** (`@ai-testing-tool/forge-vitest`) in `vitest.config` so each run can publish results and autogenerate TestCases on ingest. Pair it with a [CI snippet](./publish-results-from-ci.md) from the template builder.

This reporter does not replace Test Design. Design you edit in Jira stays on the TestCase; a **new** launch clones a snapshot onto a TestExecution.

## Install

```bash
npm install -D @ai-testing-tool/forge-vitest @ai-testing-tool/forge-commons
```

Package guide: [qa-vitest](https://github.com/ai-testing-tool/testing-tool-js/tree/main/qa-vitest).

## Configure

In `vitest.config.ts`:

```ts
test: {
  reporters: [
    'default',
    ['@ai-testing-tool/forge-vitest', { /* mode / projectKey optional */ }],
  ],
},
```

Set `AI_TESTING_TOOL_MODE=ingest` plus project key, ingest URL, and token when the run should upload. Default mode is `off`. Ingest format is `vitest-json`.

Prefer **Jira issue keys in test titles**. Wrap tests with `withQa` from `@ai-testing-tool/forge-vitest/vitest` when you want suite/step metadata.

## In Jira

1. Connect [ingest](./ci-ingest-url-and-token.md).
2. Open **Apps** → **Vitest**. Follow **Open guide**, or **Setup** with Vitest preselected.
3. Run Vitest with `AI_TESTING_TOOL_MODE=ingest` after your test stage.

Optional: native Vitest JSON plus the CLI upload. Prefer the reporter unless you already have that JSON pipeline.

## FAQ

**Did ingest overwrite the steps I wrote in Test Design?**  
A new launch clones design onto a new TestExecution. Re-sync of the **same** launch does not re-clone.

## Related

- [Publish results from a test framework](./publish-results-from-a-test-framework.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Design a TestCase](../work-in-jira/design-a-testcase.md)
