---
title: Publish results from GitHub Actions
---

Publish Testing tool results from **GitHub Actions** by POSTing to this project's ingest URL with the ingest token. Use **repository secrets** for the URL and token, then run an upload job on each pipeline after your test stage.

Turning **GitHub Actions** **Active** in Apps is a preference only — it does not create secrets or change ingest.

## Secrets

1. Connect ingest: [CI ingest URL and token](./ci-ingest-url-and-token.md).
2. In the GitHub repo, add secrets for the ingest URL and token (names often match what the template builder emits).
3. Do not commit the token to the workflow file.

Platform docs: [GitHub Actions](https://docs.github.com/en/actions).

## In Jira

1. Open **Apps** → **GitHub Actions** (app Active), then **Setup**.
2. Use the **CI template builder** (GitHub Actions is preselected; pick a framework if you use a reporter).
3. Copy the workflow snippet into `.github/workflows/`.
4. Run the pipeline. A **new** launch creates TestExecutions; re-running the **same** launch reuses them.
5. Watch the toolbar **bell**, then refresh **Test execution** (check **No test cycle** if needed).

Pair with a [test framework reporter](./publish-results-from-a-test-framework.md) when the job should publish via the Testing tool reporter instead of a raw JSON upload.

## FAQ

**Upload failed after I rotated the token.**  
Update the repository secret to the new token. The old one is dead.

**Why is Setup / CI template builder disabled?**  
The GitHub Actions app is inactive, or ingest is not connected. Enable Project Integration, then connect ingest on Setup.

## Related

- [Publish results from CI](./publish-results-from-ci.md)
- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [Apps catalog](./apps-catalog.md)
