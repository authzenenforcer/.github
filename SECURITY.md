# Security policy

authzen-enforcer decides whether requests may proceed, so a flaw in it can let a request through
that should have been denied. Thank you for helping keep its users safe.

## Reporting a vulnerability

**Please do not open a public issue, discussion or pull request for a vulnerability.**

Report it privately through GitHub:
[Report a vulnerability](https://github.com/authzenenforcer/authzen-enforcer/security/advisories/new)
(the repository's **Security** tab → **Report a vulnerability**). Only the maintainers and you can
see the report, and it becomes a draft security advisory in which we can talk, prepare the fix and
request a CVE.

If you cannot use GitHub, write to
[authzen.enforcer@gmail.com](mailto:authzen.enforcer@gmail.com) with "Security" in the subject.

Please include what you can of:

- the affected module and version, such as `authzen-enforcer-spring-boot-starter` 0.2.0;
- what an attacker can do, and under which conditions (configuration, PDP, framework);
- the steps or a minimal test that shows it;
- anything you already know about a fix.

Test only against your own installations. Do not access other people's data or disrupt services.

## What happens next

- We acknowledge your report within **5 working days**.
- We confirm the problem, assess its impact and keep you informed of the progress.
- We fix it in a new release, publish a GitHub security advisory (with a CVE where warranted) and
  credit you, unless you prefer otherwise. We ask you to keep the details private until then.

authzen-enforcer is maintained in spare time; complex issues may take longer to fix, and we will
tell you if they do.

## Supported versions

Before 1.0, only the latest release receives security fixes.

| Version | Supported |
|---|---|
| 0.2.x | Yes |
| < 0.2 | No |

## Scope

In scope: the published modules, `authzen-enforcer-core`, `authzen-enforcer-spring-boot-starter`,
`authzen-enforcer-micrometer`, `authzen-enforcer-opentelemetry` and the BOM, for example a request
that is let through without a permit of the PDP, a credential or personal data that reaches logs,
events or the PDP when it should not, or a way to make the client fail open.

Out of scope:

- vulnerabilities of a PDP, such as Keycloak, Cerbos or Topaz: please report them to its project;
- the examples in [authzen-enforcer-examples](https://github.com/authzenenforcer/authzen-enforcer-examples),
  which are meant to run locally, for instance with a password grant client for their checks,
  unless they show a flaw of the SDK itself;
- behavior that the documentation describes as a choice of the application, such as fail-open,
  which is off by default.

How the SDK handles failures, credentials and personal data is described in
[docs/security-model.md](https://github.com/authzenenforcer/authzen-enforcer/blob/main/docs/security-model.md).
