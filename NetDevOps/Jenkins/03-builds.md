---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Builds and execution

[🇬🇧 English](03-builds.md) · [🇨🇴 Español](03-builds.es.md) · [↩ Jenkins](README.md)

**Platform:** Jenkins CLI / Jenkins LTS; examples pending lab validation.

## `build network-backup -s -v`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth build network-backup -s -v
```

- **Purpose:** Trigger an authorized network-backup build and wait for completion while showing console output.
- **Arguments:** `build network-backup`: starts the job; `-s`: wait until completion; `-v`: stream console output. May run changes defined by job. `-s` (global): Jenkins URL; `-webSocket`: transport.
- **Use case:** Run an approved backup pipeline and inspect its execution result.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified; avoid sharing logs with secrets.
