---
title: Publish results from Bitbucket Pipelines
---

Publish Testing tool results from **Bitbucket Pipelines** by POSTing to this project's ingest URL with the ingest token. Store credentials as **repository or workspace variables**, then run the publish step after tests.

Turning **Bitbucket Pipelines** **Active** in Apps is a preference only — it does not create variables or change ingest.

## Variables

1. Connect ingest: [CI ingest URL and token](./ci-ingest-url-and-token.md).
2. In Bitbucket, add repository or workspace variables for the ingest URL and token. Mark the token secured.
3. Do not commit the token to `bitbucket-pipelines.yml`.

Platform docs: [Bitbucket Pipelines](https://support.atlassian.com/bitbucket-cloud/docs/get-started-with-bitbucket-pipelines/).

## In Jira

1. Open **Apps** → **Bitbucket Pipelines** (app Active), then **Setup**.
2. Use the **CI template builder** (Bitbucket Pipelines is preselected; pick a framework if you use a reporter).
3. Copy the step snippet into `bitbucket-pipelines.yml`.
4. Run the pipeline. A **new** launch creates TestExecutions; re-running the **same** launch reuses them.
5. Watch the toolbar **bell**, then refresh **Test execution** (check **No test cycle** if needed).

Pair with a [test framework reporter](./publish-results-from-a-test-framework.md) when the job should publish via the Testing tool reporter instead of a raw JSON upload.

## FAQ

**Upload failed after I rotated the token.**  
Update the repository or workspace variable to the new token. The old one is dead.

**Why is Setup / CI template builder disabled?**  
The Bitbucket Pipelines app is inactive, or ingest is not connected. Enable Project Integration, then connect ingest on Setup.

## Related

- [Publish results from CI](./publish-results-from-ci.md)
- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [Apps catalog](./apps-catalog.md)
