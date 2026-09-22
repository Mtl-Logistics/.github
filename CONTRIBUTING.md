# Contributing

These rules apply to **every repository** in the `Mtl-Logistics` organization
unless a repo's own `CONTRIBUTING.md` overrides them.

## Branching

`main` is always deployable. It accepts direct pushes — it cannot be
force-pushed or deleted, but nothing stops you writing to it.

That makes branching a judgement call rather than a rule. Push straight to
`main` for small, obvious, self-contained changes. Use a branch and a PR when
the change is non-trivial, touches auth, data or money, or you simply want a
second pair of eyes.

Branches are short-lived and named by what they do:

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
5. Wait for a review. Nothing in the tooling forces this, which is exactly why
   it matters: if you opened a PR, you wanted the review. Take it.
6. Merge with **Squash and merge**. The squash subject is the PR title, so the
   PR title must itself be a valid Conventional Commit.

`CODEOWNERS` marks who knows each area. Reviews are not enforced by branch
rules, so treat the file as a directory of who to ask, not a gate to satisfy.

## Code review

**As an author:** explain the *why* in the description, not the *what* — the
diff already says what. Respond to every comment, even if only to say "done".

**As a reviewer:** review within one working day. Distinguish blocking comments
from suggestions — prefix non-blocking ones with `nit:`. Approve when the change
is *better than what is on `main`*, not when it is perfect.

## Local checks before pushing

Because `main` takes direct pushes, these are the only gate between your
change and the default branch. Run them.

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
