---
title: Publish results from Jenkins
---

Publish Testing tool results from **Jenkins** by POSTing to this project's ingest URL with the ingest token. Inject the URL and token as **credentials**, then run the publish step after tests.

Turning **Jenkins** **Active** in Apps is a preference only — it does not create credentials or change ingest.

## Credentials

1. Connect ingest: [CI ingest URL and token](./ci-ingest-url-and-token.md).
2. In Jenkins, store the ingest URL and token as credentials (or secret text). Bind them into the job or pipeline.
3. Do not hardcode the token in the Jenkinsfile.

Platform docs: [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/).

## In Jira

1. Open **Apps** → **Jenkins** (app Active), then **Setup**.
2. Use the **CI template builder** (Jenkins is preselected; pick a framework if you use a reporter).
3. Copy the pipeline or freestyle step snippet into your job.
4. Run the job after tests. A **new** launch creates TestExecutions; re-running the **same** launch reuses them.
5. Watch the toolbar **bell**, then refresh **Test execution** (check **No test cycle** if needed).

Pair with a [test framework reporter](./publish-results-from-a-test-framework.md) when the job should publish via the Testing tool reporter instead of a raw JSON upload.

## FAQ

**Upload failed after I rotated the token.**  
Update the Jenkins credential to the new token. The old one is dead.

**Why is Setup / CI template builder disabled?**  
The Jenkins app is inactive, or ingest is not connected. Enable Project Integration, then connect ingest on Setup.

## Related

- [Publish results from CI](./publish-results-from-ci.md)
- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [Apps catalog](./apps-catalog.md)
