---
title: Publish results from Cypress
---

Register the **Testing tool Cypress reporter** (`@ai-testing-tool/forge-cypress`) so Cypress runs publish results to this project. Cypress uses the **reporter path only** — do not add a separate JSON upload job unless the package guide says so.

You must also register the Cypress **plugin** so `after:run` publishes one launch for the whole `cypress run`. This reporter does not replace Test Design.

## Install

```bash
npm install -D @ai-testing-tool/forge-cypress @ai-testing-tool/forge-commons cypress-multi-reporters
```

Peer: `cypress` ≥12. Package guide: [qa-cypress](https://github.com/ai-testing-tool/testing-tool-js/tree/main/qa-cypress).

## Configure

In `cypress.config.js`, set the reporter and register the plugin (and metadata helper) in `setupNodeEvents`:

```js
reporter: 'cypress-multi-reporters',
reporterOptions: {
  reporterEnabled: '@ai-testing-tool/forge-cypress',
  qaCypressReporterOptions: {
    // mode: 'ingest' | 'file' | 'off',
  },
},
e2e: {
  setupNodeEvents(on, config) {
    require('@ai-testing-tool/forge-cypress/plugin')(on, config);
    require('@ai-testing-tool/forge-cypress/metadata')(on);
    return config;
  },
},
```

Direct reporter without multi-reporters: `reporter: '@ai-testing-tool/forge-cypress'`. The plugin is still required.

Set `AI_TESTING_TOOL_MODE=ingest` plus project key, ingest URL, and token when the run should upload. Default mode is `off`.

Prefer **Jira issue keys in test titles**. `qa.step()` callbacks must stay **synchronous**.

## In Jira

1. Connect [ingest](./ci-ingest-url-and-token.md).
2. Open **Apps** → **Cypress**. Follow **Open guide**, or **Setup** with Cypress preselected.
3. Run `cypress run` with `AI_TESTING_TOOL_MODE=ingest` after your test stage.

## FAQ

**Do I need a second job that uploads JSON?**  
No. The reporter + plugin publish on `cypress run`. Follow the package README; do not add an extra upload job unless that guide says so.

**Did ingest overwrite the steps I wrote in Test Design?**  
A new launch clones design onto a new TestExecution. Re-sync of the **same** launch does not re-clone.

## Related

- [Publish results from a test framework](./publish-results-from-a-test-framework.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Design a TestCase](../work-in-jira/design-a-testcase.md)
