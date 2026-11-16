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

## `who-am-i`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth who-am-i
```

- **Purpose:** Show which Jenkins identity and authorities the CLI connection uses.
- **Arguments:** `-auth @jenkins-auth`: read username:API token from private file; `who-am-i`: current Jenkins identity. `-s`: Jenkins URL; `-webSocket`: transport.
- **Use case:** Verify least-privilege API credentials before accessing CI/CD jobs.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified; protect credentials.

## `help build`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth help build
```

- **Purpose:** Display the syntax and arguments supported by the build CLI command.
- **Arguments:** `help build`: help for build command; available flags depend on Jenkins CLI version. `-auth @jenkins-auth`: credentials from a protected file.
- **Use case:** Confirm supported flags before launching an approved pipeline.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified.
