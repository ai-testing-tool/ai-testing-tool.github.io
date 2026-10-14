---
title: README sync status badge
---

Embed a **CircleCI-style** SVG badge in a repo README so anyone can see whether the latest CI ingest for a branch has finished syncing into Jira. The badge uses the same ingest URL as CI uploads. **Status GET is public** (no token). **POST** ingest still needs the Bearer token.

Modeled after [CircleCI status badges](https://circleci.com/docs/guides/integration/status-badges/).

## Copy the snippet

1. Connect ingest: [CI ingest URL and token](./ci-ingest-url-and-token.md).
2. Open **Testing tool → Apps** → a CI or framework app → **Setup**.
3. Under **README status badge**, select and copy the Markdown (clipboard paste from Forge is unavailable for this field).
4. Paste into your repo `README.md`.
5. Change `gitBranch=main` if your default branch (or the branch you care about) is different.

Default snippet shape:

```markdown
[![AI Testing Tool]({ingestUrl}?format=svg&projectKey=AUTH&gitBranch=main)]({jira-or-docs-url})
```

## What the badge shows

| Color  | Meaning                                                       |
| ------ | ------------------------------------------------------------- |
| Yellow | Ingest landed; Jira fan-out still **pending** / **syncing**   |
| Green  | Fan-out **synced**                                            |
| Red    | **error**, unmapped TMS types, missing launch, or bad request |

While Testing tool is open you can also watch the same lifecycle in the toolbar bell — see [CI push notifications](./ci-push-notifications.md).

## How lookup works

The badge URL is a **GET** on the ingest web trigger. No Authorization header.

1. **`gitCommitSha`** — pin that launch (same id CI sent on ingest).
2. Else **`gitBranch`** — latest launch stored for that branch in the project.
3. Else — latest launch in the project (any branch).

CI must send `gitBranch` (and usually `gitCommitSha`) on ingest so branch badges stay meaningful. Reporters and template snippets typically set these from the pipeline environment.

## Pin a commit (optional)

```markdown
[![AI Testing Tool]({ingestUrl}?format=svg&projectKey=AUTH&gitCommitSha=<full-sha>)]({jira-or-docs-url})
```

Use a real SHA. Do not put angle brackets in the URL.

## JSON poll (CI)

Same URL without `format=svg` returns JSON for scripts:

```http
GET {ingestUrl}?projectKey=AUTH&gitBranch=main
```

```json
{ "ok": true, "executionSyncStatus": "synced" }
```

Poll until `synced` or `error` (or timeout). Still **no auth** on GET.

## FAQ

**Why is the badge red / “error”?**  
No launch for that project/branch yet, sync failed, or TMS issue types are missing. Check Test execution and the toolbar bell. Confirm CI is posting `gitBranch`.

**Does the badge expose my ingest token?**  
No. Status GET is public. Keep the **token** only in CI secrets for POST upload.

**Can I use the badge without a branch?**  
Yes — omit `gitBranch` to track the latest launch in the project. Prefer a branch for README embeds so feature-branch noise does not flip the badge.

**Does Active on the Apps catalog change the badge?**  
No. Active is a preference only.

## Related

- [CI ingest URL and token](./ci-ingest-url-and-token.md)
- [CI push notifications](./ci-push-notifications.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Apps catalog](./apps-catalog.md)
- [Start here](../start-here.md)
