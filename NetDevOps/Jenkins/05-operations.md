---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Operations and plugins

[🇬🇧 English](05-operations.md) · [🇨🇴 Español](05-operations.es.md) · [↩ Jenkins](README.md)

**Platform:** Jenkins CLI / Jenkins LTS; examples pending lab validation.

## `version`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth version
```

- **Purpose:** Display the Jenkins controller version reported by the CLI.
- **Arguments:** `version`: server version; global `-s`: URL; `-webSocket`: transport. `-auth @jenkins-auth`: credentials from a protected file.
- **Use case:** Record the Jenkins release before troubleshooting plugin compatibility.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified.

## `list-plugins`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth list-plugins
```

- **Purpose:** List installed Jenkins plugins and their versions, subject to authorization.
- **Arguments:** `list-plugins`: installed plugin list; no other command arguments. `-auth @jenkins-auth`: credentials from a protected file.
- **Use case:** Check whether pipeline and Git integrations are installed.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified.
