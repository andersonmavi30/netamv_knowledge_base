---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Job management

[🇬🇧 English](02-jobs.md) · [🇨🇴 Español](02-jobs.es.md) · [↩ Jenkins](README.md)

**Platform:** Jenkins CLI / Jenkins LTS; examples pending lab validation.

## `list-jobs`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth list-jobs
```

- **Purpose:** List jobs visible to the authenticated user in the Jenkins root view.
- **Arguments:** `list-jobs`: list jobs, restricted by Jenkins authorization; no arguments. `-s`: Jenkins URL; `-webSocket`: transport.
- **Use case:** Find available NetDevOps jobs before triggering a pipeline.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified; protect credentials.
