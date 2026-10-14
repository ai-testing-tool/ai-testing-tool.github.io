---
title: Make a project TMS-ready
---

A project is TMS-ready when it has four Jira issue types named exactly **Requirement**, **TestCase**, **TestExecution**, and **Bug**, and the site has three issue link types named **Coverage**, **Execution**, and **Found**. Until those exist, Testing tool shows onboarding and the agent cannot create TestCases.

Issue type names are **case-sensitive**. `Testcase` or `Test Case` will show as **Missing**.

## What you will see

Open the project **Testing tool** page. If setup is incomplete, onboarding titled **Team managed configuration** lists each work type and each link type as ready or **Missing**.

You need permission to add issue types in that project (project admin, or a Jira admin who can edit the issue type scheme). Creating missing link types on **Refresh** needs site configuration permission (`manage:jira-configuration`).

## Steps

1. Open **Testing tool** for the project.
2. Click **Download Testing tool Jira issue icons** if you want the official icons when you create the types.
3. Create the four issue types with these exact names:
   - Requirement
   - TestCase
   - TestExecution
   - Bug
4. Add them to this project (team-managed: create in the project; company-managed: add them to the project's issue type scheme).
5. Confirm site link types **Coverage**, **Execution**, and **Found** (Jira settings → Issues → Issue linking), or click **Refresh** so the app can create any that are missing.
6. Return to Testing tool and click **Refresh**.
7. When every work-type and link-type row shows ready (check), click **Launch Testing tool For Jira**.

Need the Jira settings screen? Use **Add these work types in Jira, click here** at the bottom of onboarding. Link types are configured under **Issue linking**.

Where the app can provision or attach the named types for you, use that in-app action, then **Refresh**. You do not need a full browser reload if Refresh succeeds.

### Link type phrases

| Name      | Outward        | Inward       |
| --------- | -------------- | ------------ |
| Coverage  | is covered by  | covers       |
| Execution | is executed as | executes     |
| Found     | found          | was found by |

## After it is ready

- Requirements, Test design, and Test execution are usable.
- Testing tool can create TestCases in this project (you still confirm each write in chat).
- If Testing tool still refuses create, you may lack **Create issues** on the project — see [Permissions, credits, and limits](./permissions-credits-limits.md).

## FAQ

**Why does Refresh still say Missing?**  
The type name does not match exactly, the type is not on this project's scheme, a link type could not be created (permissions), or you refreshed before Jira finished saving. Check the name, then Refresh again.

**Can I reuse an existing Bug type?**  
Yes, if it is named exactly **Bug** and it is available in this project.

**Do I do this on every project?**  
Issue types are per project. Link types are site-wide — once Coverage / Execution / Found exist on the site, every project can use them.

**Will Testing tool set this up for me?**  
No. It will fail closed and point you at Apps / this setup. An admin must add the work types. Link types may be created automatically on Refresh when the app has configuration permission.

## Related

- [Install and open Testing tool](./install-and-open.md)
- [Permissions, credits, and limits](./permissions-credits-limits.md)
- [Glossary](../glossary.md)
- [Start here](../start-here.md)
