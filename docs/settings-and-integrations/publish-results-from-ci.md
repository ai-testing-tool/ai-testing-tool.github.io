---
title: Publish results from CI
---

CI platforms publish results by POSTing to this project's ingest URL with the ingest token. Use **CI template builder** to generate a snippet for your platform (and framework if you use a reporter).

Store the URL and token as repository or pipeline **secrets**. Do not commit them.

## In this section

- [Publish results from GitHub Actions](./publish-github-actions.md)
- [Publish results from GitLab CI](./publish-gitlab-ci.md)
- [Publish results from Azure Pipelines](./publish-azure-pipelines.md)
- [Publish results from Bitbucket Pipelines](./publish-bitbucket-pipelines.md)
- [Publish results from Jenkins](./publish-jenkins.md)

Shared capabilities: **Publish results via ingest**, **Generate pipeline snippets**, and **Use project ingest URL and token**.

## In Jira (any platform)

1. Connect ingest: [CI ingest URL and token](./ci-ingest-url-and-token.md).
2. Open **Apps**, pick your CI app, then **Setup**.
3. Use the **CI template builder** (platform is preselected; pick a framework if you use a reporter).
4. Copy the snippet into the pipeline. Put ingest URL and token in secrets / CI variables.
5. Run the job after your test stage. A **new** launch creates TestExecutions; re-running the **same** launch reuses them.
6. Watch the toolbar **bell** for New / Synced / Error, then open **Test execution** (often under **No test cycle**). See [CI push notifications](./ci-push-notifications.md).

## FAQ

**Upload failed after I rotated the token.**  
Update the secret to the new token. The old one is dead.

**Upload failed with HTTP 424 after a Forge redeploy.**  
**Recreate** the ingest URL on Setup, then update the URL secret. See [CI ingest URL and token](./ci-ingest-url-and-token.md).

**I see the launch but no TestExecutions yet.**  
Sync is scheduled. Watch the toolbar bell, then refresh Test execution.

## Related

- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [CI push notifications](./ci-push-notifications.md)
- [README sync status badge](./readme-sync-status-badge.md)
- [Publish results from a test framework](./publish-results-from-a-test-framework.md) (Playwright, Mocha, Jest, Cypress, Vitest, WebdriverIO)
- [Apps catalog](./apps-catalog.md)
- [Run a test cycle](../work-in-jira/run-a-test-cycle.md)
- [Start here](../start-here.md)
