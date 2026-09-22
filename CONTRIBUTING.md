# Contributing

These rules apply to **every repository** in the `Mtl-Logistics` organization
unless a repo's own `CONTRIBUTING.md` overrides them.

## Branching

`main` is protected and always deployable. Work happens on short-lived branches:

```
feat/shipment-eta-api
fix/route-optimizer-timeout
chore/bump-node-22
docs/warehouse-runbook
```

Prefix must be one of `feat` · `fix` · `chore` · `docs` · `refactor` · `test` · `perf` · `ci` · `build` · `revert`.

## Commits

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
type(scope): short imperative subject

Optional body explaining the why, wrapped at 72 characters.

Refs: #123
```

Breaking changes get a `!` after the scope (`feat(api)!: drop v1 endpoints`)
and a `BREAKING CHANGE:` footer.

## Pull requests

1. Open the PR against `main`, filling in the template.
2. Keep it small — under ~400 changed lines is the target. Split large work.
3. Mark it **Draft** while it is still moving.
4. CI must be green. A red pipeline is not a review problem, it is yours.
5. At least one approving review from a `CODEOWNERS` reviewer is required.
6. Merge with **Squash and merge**. The squash subject is the PR title, so the
   PR title must itself be a valid Conventional Commit.

Do not merge your own PR unless you are the sole maintainer of that repo and
the change is a documented exception.

## Code review

**As an author:** explain the *why* in the description, not the *what* — the
diff already says what. Respond to every comment, even if only to say "done".

**As a reviewer:** review within one working day. Distinguish blocking comments
from suggestions — prefix non-blocking ones with `nit:`. Approve when the change
is *better than what is on `main`*, not when it is perfect.

## Local checks before pushing

Every repo exposes the same entry points, whatever the stack underneath:

```bash
make lint      # or: npm run lint
make test      # or: npm test
make build     # or: npm run build
```

If a repo cannot offer one of these, its README says why.

## Dependencies

- New runtime dependencies need a line in the PR description justifying them.
- Dependabot PRs are reviewed like any other change; do not blind-merge majors.
- Never commit lockfile changes that you did not intend to make.

## Security

Never commit secrets, tokens, `.env` files, customer data or production
credentials. Push protection will block known secret formats, but it is a net,
not a guarantee. If you leak something, **rotate it first**, then tell the
security team — see [`SECURITY.md`](SECURITY.md).
