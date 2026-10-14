---
title: Publish results from GitLab CI
---

Publish Testing tool results from **GitLab CI** by POSTing to this project's ingest URL with the ingest token. Store credentials as **CI/CD variables**, then run an upload job **after** the test stage.

Turning **GitLab CI** **Active** in Apps is a preference only — it does not create variables or change ingest.

## Variables

1. Connect ingest: [CI ingest URL and token](./ci-ingest-url-and-token.md).
2. In GitLab, add CI/CD variables for the ingest URL and token (project or group). Mask the token.
3. Do not print the token in job logs.

Platform docs: [GitLab CI](https://docs.gitlab.com/ci/).

## In Jira

1. Open **Apps** → **GitLab CI** (app Active), then **Setup**.
2. Use the **CI template builder** (GitLab CI is preselected; pick a framework if you use a reporter).
3. Copy the job snippet into `.gitlab-ci.yml` so it runs after tests.
4. Run the pipeline. A **new** launch creates TestExecutions; re-running the **same** launch reuses them.
5. Watch the toolbar **bell**, then refresh **Test execution** (check **No test cycle** if needed).

Pair with a [test framework reporter](./publish-results-from-a-test-framework.md) when the job should publish via the Testing tool reporter instead of a raw JSON upload.

## FAQ

**Upload failed after I rotated the token.**  
Update the CI/CD variable to the new token. The old one is dead.

**Why is Setup / CI template builder disabled?**  
The GitLab CI app is inactive, or ingest is not connected. Enable Project Integration, then connect ingest on Setup.

## Related

- [Publish results from CI](./publish-results-from-ci.md)
- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [Apps catalog](./apps-catalog.md)
