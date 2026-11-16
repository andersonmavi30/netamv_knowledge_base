---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Logs and diagnostics

[🇬🇧 English](04-diagnostics.md) · [🇨🇴 Español](04-diagnostics.es.md) · [↩ Jenkins](README.md)

**Platform:** Jenkins CLI / Jenkins LTS; examples pending lab validation.

## `console network-backup -f`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth console network-backup -f
```

- **Purpose:** Follow console output from the latest build of the selected job.
- **Arguments:** `console`: build output; `network-backup`: target job; `-f`: follow live output until completion. `-s` (global): Jenkins URL; `-webSocket`: transport.
- **Use case:** Investigate Jenkins-to-AWX orchestration output without starting another job.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified; avoid sharing logs with secrets.
