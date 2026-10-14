---
title: Publish results from Mocha
---

Add the **Testing tool Mocha reporter** (`@ai-testing-tool/forge-mocha`) so Mocha runs publish results to this project. Mocha uses the **reporter path only** — do not add a separate JSON upload job unless the package guide says so.

This reporter does not replace Test Design. Design you edit in Jira stays on the TestCase; a **new** launch clones a snapshot onto a TestExecution.

## Install

```bash
npm install -D @ai-testing-tool/forge-mocha @ai-testing-tool/forge-commons mocha
```

Peer: `mocha` ≥10. Package guide: [qa-mocha](https://github.com/ai-testing-tool/testing-tool-js/blob/main/qa-mocha/README.md).

## Configure

In `.mocharc.js`:

```js
module.exports = {
  spec: ['test/**/*.spec.js'],
  reporter: '@ai-testing-tool/forge-mocha',
  reporterOptions: {
    // mode: 'ingest' | 'file' | 'off',
    // projectKey: 'DEMO',
  },
};
```

Set `AI_TESTING_TOOL_MODE=ingest` plus project key, ingest URL, and token when the run should upload. Default mode is `off`.

Prefer **Jira issue keys in test titles**. Use `qa` helpers from `@ai-testing-tool/forge-mocha/mocha` for steps and fields.

## In Jira

1. Connect [ingest](./ci-ingest-url-and-token.md).
2. Open **Apps** → **Mocha**. Follow **Open guide**, or **Setup** with Mocha preselected.
3. Run Mocha with `AI_TESTING_TOOL_MODE=ingest` after your test stage.

## FAQ

**Do I need a second job that uploads JSON?**  
No. The reporter publishes on the Mocha process. Follow the package README; do not add an extra upload job unless that guide says so.

**Did ingest overwrite the steps I wrote in Test Design?**  
A new launch clones design onto a new TestExecution. Re-sync of the **same** launch does not re-clone.

## Related

- [Publish results from a test framework](./publish-results-from-a-test-framework.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Design a TestCase](../work-in-jira/design-a-testcase.md)
