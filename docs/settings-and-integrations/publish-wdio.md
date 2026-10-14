---
title: Publish results from WebdriverIO
---

Wire the **Testing tool WebdriverIO reporter and service** (`@ai-testing-tool/forge-wdio`) in `wdio.conf` so WDIO runs publish results to this project. WDIO uses the **reporter path only** — do not add a separate JSON upload job unless the package guide says so.

Supports WebdriverIO 8+ with **Mocha** or **Cucumber**. This reporter does not replace Test Design.

## Install

```bash
# Mocha (default)
npm install -D @ai-testing-tool/forge-wdio @ai-testing-tool/forge-commons @wdio/mocha-framework

# Cucumber
npm install -D @ai-testing-tool/forge-wdio @ai-testing-tool/forge-commons @wdio/cucumber-framework
```

Package guide: [qa-wdio](https://github.com/ai-testing-tool/testing-tool-js/tree/main/qa-wdio).

## Configure

In `wdio.conf.js` you need all three: reporter, `QaWdioService`, and `beforeRunHook` / `afterRunHook` on `onPrepare` / `onComplete`. Those hooks are required for ingest and file modes.

Cucumber: set `useCucumber: true` on the reporter. Prefer Jira keys in the scenario title or tags such as `@AUTH-101`.

Set `AI_TESTING_TOOL_MODE=ingest` plus project key, ingest URL, and token when the run should upload. Default mode is `off`.

Prefer **Jira issue keys in test titles**. Use `await qa.step()` from `@ai-testing-tool/forge-wdio` for step timelines.

## In Jira

1. Connect [ingest](./ci-ingest-url-and-token.md).
2. Open **Apps** → **WebdriverIO (WDIO)**. Follow **Open guide**, or **Setup** with WDIO preselected.
3. Run `wdio` with `AI_TESTING_TOOL_MODE=ingest` after your test stage.

## FAQ

**Do I need a second job that uploads JSON?**  
No. The reporter + service publish on the WDIO process. Follow the package README; do not add an extra upload job unless that guide says so.

**Did ingest overwrite the steps I wrote in Test Design?**  
A new launch clones design onto a new TestExecution. Re-sync of the **same** launch does not re-clone.

## Related

- [Publish results from a test framework](./publish-results-from-a-test-framework.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Design a TestCase](../work-in-jira/design-a-testcase.md)
