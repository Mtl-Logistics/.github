# Security Policy

## Reporting a vulnerability

**Do not open a public issue, PR or Discussion for a security problem.**

Report it privately through **GitHub Security Advisories**:

1. Go to the affected repository → **Security** → **Report a vulnerability**
2. Or, if that repo has advisories disabled, use the
   [`.github` repository advisory form](https://github.com/Mtl-Logistics/.github/security/advisories/new)

Include, as far as you can:

- what the issue is and which component it affects
- the version, commit or environment you saw it on
- steps to reproduce, or a proof of concept
- the impact you believe it has

### What to expect

| Stage | Target |
|---|---|
| Acknowledgement | 2 business days |
| Initial assessment and severity | 5 business days |
| Fix or mitigation for critical issues | 30 days |
| Public disclosure | Coordinated with you, after a fix ships |

We will keep you updated while we work, and credit you in the advisory unless
you ask us not to.

## Scope

In scope: source code, CI configuration, container images and infrastructure
definitions published under the `Mtl-Logistics` organization.

Out of scope: findings that require a compromised device or account, social
engineering of our staff, volumetric denial of service, and reports produced by
an automated scanner with no demonstrated impact.

## Supported versions

Unless a repository states otherwise, we support the latest released minor
version on the default branch. Older versions receive fixes only for critical
vulnerabilities.

## Our commitments

- Secret scanning and push protection are enabled across the organization
- Dependabot alerts and security updates are enabled on every repository
- CodeQL runs on every pull request to `main` for supported languages
- Branch protection prevents unreviewed code reaching `main`

## If you leak a credential

1. **Rotate it immediately.** Revocation beats cleanup every time.
2. Tell the security team.
3. Do not try to erase it from history alone — rewriting shared history needs
   coordination, and the secret is already considered compromised.
