# Assignment

A training assignment from **New Indictrans Technologies Pvt Ltd** — my first company —
completed over roughly two weeks in October and November 2021 while learning the
[Frappe Framework](https://frappeframework.com) and ERPNext.

The task was to go from nothing to a working bench: install Frappe and ERPNext, build
custom apps on top of them, and implement a small project-and-task system with
workflows and a dashboard.

> **This repository is a snapshot of a `frappe-bench` working directory, not an
> installable app.** It was committed whole — virtualenv, built assets, logs and all —
> which is not how a Frappe project should be version-controlled. It is kept as a
> record of the assignment rather than as something to clone and run. See
> [What's actually here](#whats-actually-here) before trying to use it.

## What the assignment covered

Reconstructed from the commit history, which was used as a progress log:

| Commit | Milestone |
|---|---|
| `63cc2564` | Blank bench setup |
| `0b8fc340`, `a4a8485f`, `8b8e7bb5` | Frappe app and site creation |
| `e285d3fb` | Requirement #001 completed |
| `56180060` | Project and Task demo |
| `95ae805a` | ERPNext installed alongside the custom app |
| `2d082db9` | Workflow created |
| `83c6eb4a` | Custom app installed |
| `dc4e2c3a` | Dashboard page |

Four apps were registered on the bench (`sites/apps.txt`):

- `frappe` and `erpnext` — the framework and ERP application
- `demo_app` — a scratch app for working through the early requirements
- `project_management` — the main deliverable, a project and task system

Two sites were built:

- `erpnextuse.case` — the ERPNext use-case site
- `projectmanagement.sys` — the site hosting the custom project management app

## What's actually here

Worth being blunt about, because the layout is misleading:

**The custom app source code is not in this repository.** `apps/demo_app`,
`apps/project_management`, `apps/frappe` and `apps/erpnext` are recorded as git
submodule pointers (gitlinks), but there is no `.gitmodules` file to say where they
came from. The directories are empty and the commit hashes cannot be resolved. So the
actual assignment code — doctypes, workflow, dashboard — is not recoverable from here.

**What is committed instead** is the surrounding bench: a Python 3.8 virtualenv
(~21,800 files, the overwhelming bulk of the repository), compiled front-end assets,
Redis configs, scheduler logs, and both sites' data directories.

In other words, the repository preserves the *shape* of the bench and the commit
history of the work, but not the code that was written.

## Environment

- Frappe Framework and ERPNext as of late 2021
- Python 3.8
- MariaDB, Redis

## Looking back

The thing this repository best demonstrates is what I did not know yet about version
control at the time. A Frappe bench should never be committed: `env/`, `sites/assets/`,
and `sites/*/private/` are all generated or environment-specific, and each custom app
belongs in its own repository, installed with `bench get-app`. Committing the bench
wrapper instead means the 21,800 files that did not matter were preserved and the
handful that did were lost to unresolvable submodule pointers.

Keeping it unedited seemed more useful than tidying it up after the fact.

## License

No license specified.
