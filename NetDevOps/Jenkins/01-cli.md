---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# CLI and authentication

[🇬🇧 English](01-cli.md) · [🇨🇴 Español](01-cli.es.md) · [↩ Jenkins](README.md)

**Platform:** Jenkins CLI / Jenkins LTS; examples pending lab validation.

## `java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket help`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket help
```

- **Purpose:** List CLI commands available on the Jenkins controller, subject to permissions and plugins.
- **Arguments:** `-jar`: run JAR; `-s`: Jenkins URL; `-webSocket`: WebSocket transport; `help`: list commands.
- **Use case:** Discover supported operations before automating Jenkins in the lab.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified.
