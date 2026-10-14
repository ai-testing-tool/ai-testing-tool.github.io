---
title: CI ingest URL and token
---

Each project has an **ingest URL** and a **token**. CI jobs and reporters POST test results to that URL. You set this up under **Testing tool → Apps** by opening a CI or framework app and choosing **Setup** — there is no separate Jira admin page.

The plaintext token is shown **once** when you connect or rotate. Select and copy it into your CI secret manager (clipboard paste from Forge is unavailable for these fields). After that, the field is masked.

## Connect the project

1. Open **Testing tool** → **Apps**.
2. Open a CI or framework app (for example **GitHub Actions** or **Playwright**), then click **Setup**.
3. Under **Ingest configuration**, expand the section if needed. If the project is not connected, click **Connect project**.
4. Select and copy the **CI ingest endpoint** URL.
5. When the warning **Plaintext token freshly generated** appears, select and copy the token from the field, then click **I have saved the token**.

## Rotate token

**Rotate** issues a new plaintext token (shown once) and invalidates the old one. Update every pipeline secret, or uploads start failing with 401. The ingest URL stays the same.

## Recreate ingest URL

**Recreate** deletes the current webtrigger URL and issues a new one. The ingest **token is not changed**. Use this after a Forge redeploy if POST ingest returns **HTTP 424**, or when the old URL must be retired. Confirm in the dialog, then update every pipeline secret that stores the ingest URL.

## After connect

- **CI template builder** becomes available (otherwise: **CI setup unavailable** — connect the project first).
- **README status badge** — select and copy the Markdown image snippet for repo READMEs (public sync status; no token). See [README sync status badge](./readme-sync-status-badge.md).
- Toolbar **bell** shows live New / Synced / Error for CI pushes while Testing tool is open. See [CI push notifications](./ci-push-notifications.md).

Active toggles on the Apps catalog do **not** revoke this token or block upload.

## FAQ

**Who can see the token later?**  
Nobody in plaintext. Copy it when it is shown, or Rotate to get a new one.

**Does Testing tool need this token?**  
No. The Rovo agent uses your Jira session. Ingest is for CI and reporters only.

**Rotate vs Recreate?**  
Rotate replaces only the Bearer token. Recreate replaces only the URL. Update the matching CI secrets for whichever you changed.

## Related

- [Apps catalog](./apps-catalog.md)
- [CI push notifications](./ci-push-notifications.md)
- [README sync status badge](./readme-sync-status-badge.md)
- [Publish results from CI](./publish-results-from-ci.md)
- [Publish results from a test framework](./publish-results-from-a-test-framework.md)
- [Start here](../start-here.md)
