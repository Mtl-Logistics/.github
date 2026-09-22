# `.github` — organization defaults

This repository holds the defaults that apply to **every repository** in the
`Mtl-Logistics` organization. GitHub reads most of it automatically: a repo that
does not define its own copy of a file inherits the one here.

## What lives here

| Path | Effect |
|---|---|
| `profile/README.md` | The public landing page at [github.com/Mtl-Logistics](https://github.com/Mtl-Logistics) |
| `CONTRIBUTING.md` | Linked from every new issue and PR across the org |
| `CODE_OF_CONDUCT.md` | Org-wide community standards |
| `SECURITY.md` | Shown under every repo's **Security** tab |
| `SUPPORT.md` | Linked from the issue chooser |
| `.github/ISSUE_TEMPLATE/` | Default issue forms for repos without their own |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR template |
| `workflow-templates/` | Starter workflows offered in the **Actions** tab of every repo |
| `CODEOWNERS` | Default reviewers for changes to this repository |

## How inheritance works

A file here is a **fallback**, not an override. If a repository defines its own
`CONTRIBUTING.md` or `.github/ISSUE_TEMPLATE/`, that wins for that repository.
This is deliberate — a repo with genuinely different needs should say so.

`profile/README.md` is the exception: it only ever renders on the org page.

## Starter workflows

Everything in `workflow-templates/` shows up under
**Actions → New workflow → By Mtl-Logistics** in every repo in the org.

| Template | Use it for |
|---|---|
| `ci-node` | Node/TypeScript services — lint, types, test matrix, build, audit |
| `codeql` | Static security analysis, on PRs and weekly |
| `docker-publish` | Container images to GHCR with SBOM and build provenance |
| `pr-hygiene` | Conventional Commit PR titles and diff-size warnings |

Each needs a matching `<name>.properties.json` beside it. Both files must sit at
the top level of `workflow-templates/` — GitHub does not read subdirectories.

## Changing something here

Changes here affect every repository in the organization, so they go through a
pull request like anything else. The `Community health` workflow validates the
issue forms and workflow templates on every PR.
