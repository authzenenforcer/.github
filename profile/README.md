<p align="center">
  <img src="https://raw.githubusercontent.com/authzenenforcer/authzen-enforcer/main/docs/assets/authzen-enforcer-logo.svg" alt="" width="112">
</p>

<h3 align="center">authzen-enforcer</h3>

<p align="center">
  A Policy Enforcement Point for the <a href="https://openid.net/wg/authzen/">OpenID AuthZEN Authorization API</a> in Java.
</p>

<p align="center">
  <a href="https://central.sonatype.com/artifact/io.github.authzenenforcer/authzen-enforcer-core"><img src="https://img.shields.io/maven-central/v/io.github.authzenenforcer/authzen-enforcer-core" alt="Maven Central"></a>
  <a href="https://github.com/authzenenforcer/authzen-enforcer/actions/workflows/ci.yml"><img src="https://github.com/authzenenforcer/authzen-enforcer/actions/workflows/ci.yml/badge.svg?branch=main" alt="CI"></a>
</p>

Your application asks a Policy Decision Point (PDP) such as Keycloak, Cerbos or Topaz whether a
caller may perform an action on a resource, and enforces the answer. authzen-enforcer is that
enforcing side: a zero-dependency client for Java 17+ and a Spring Boot starter, fail-closed by
default.

```java
@CheckPermission                     // read on {type: "documents", id: <id>}, asked of the PDP
@GetMapping("/documents/{id}")
public Document getDocument(@PathVariable String id) { ... }
```

```yaml
authzen:
  pdp:
    url: https://pdp.example.com     # the only required setting
```

| Repository | |
|---|---|
| [authzen-enforcer](https://github.com/authzenenforcer/authzen-enforcer) | The SDK: core client, Spring Boot starter, Micrometer and OpenTelemetry modules, [docs](https://github.com/authzenenforcer/authzen-enforcer/tree/main/docs) |
| [authzen-enforcer-examples](https://github.com/authzenenforcer/authzen-enforcer-examples) | Runnable examples against a containerized Keycloak PDP: plain Java and Spring Boot |

**Get involved:** ask in [Discussions](https://github.com/authzenenforcer/authzen-enforcer/discussions),
pick a [good first issue](https://github.com/search?q=org%3Aauthzenenforcer+label%3A%22good+first+issue%22+is%3Aopen&type=issues),
or see the [contributing guide](https://github.com/authzenenforcer/authzen-enforcer/blob/main/CONTRIBUTING.md).

<sub>An independent project, not affiliated with or endorsed by the OpenID Foundation.</sub>
