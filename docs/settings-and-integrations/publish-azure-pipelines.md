---
title: Publish results from Azure Pipelines
---

Publish Testing tool results from **Azure Pipelines** by POSTing to this project's ingest URL with the ingest token. Keep the URL and token in pipeline **secret variables**, then run the publish step after tests.

Turning **Azure Pipelines** **Active** in Apps is a preference only — it does not create variables or change ingest.

## Secret variables

1. Connect ingest: [CI ingest URL and token](./ci-ingest-url-and-token.md).
2. In Azure DevOps, add secret variables for the ingest URL and token on the pipeline or variable group.
3. Do not echo the token in the YAML or logs.

Platform docs: [Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/).

## In Jira

1. Open **Apps** → **Azure Pipelines** (app Active), then **Setup**.
2. Use the **CI template builder** (Azure Pipelines is preselected; pick a framework if you use a reporter).
3. Copy the snippet into your pipeline YAML.
4. Run the pipeline. A **new** launch creates TestExecutions; re-running the **same** launch reuses them.
5. Watch the toolbar **bell**, then refresh **Test execution** (check **No test cycle** if needed).

Pair with a [test framework reporter](./publish-results-from-a-test-framework.md) when the job should publish via the Testing tool reporter instead of a raw JSON upload.

## FAQ

**Upload failed after I rotated the token.**  
Update the secret variable to the new token. The old one is dead.

**Why is Setup / CI template builder disabled?**  
The Azure Pipelines app is inactive, or ingest is not connected. Enable Project Integration, then connect ingest on Setup.

## Related

- [Publish results from CI](./publish-results-from-ci.md)
- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [Apps catalog](./apps-catalog.md)
