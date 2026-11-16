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

## `get-job network-backup`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth get-job network-backup
```

- **Purpose:** Output the XML job configuration for a permitted Jenkins job.
- **Arguments:** `get-job`: fetch job XML; `network-backup`: example job name; may expose secrets in configuration. `-s`: Jenkins URL; `-webSocket`: transport.
- **Use case:** Review a network-backup job definition before making changes; do not publish XML.
- **Official reference:** https://www.jenkins.io/doc/book/managing/cli/

> Not lab-verified; protect credentials.
