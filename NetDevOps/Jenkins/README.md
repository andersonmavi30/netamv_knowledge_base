# Jenkins — CLI reference

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ NetDevOps](../README.md)

**Compatibility:** Jenkins LTS / Jenkins CLI (Java); verify version, permissions and available commands using `help`.

- [CLI and authentication](01-cli.md)
- [Job management](02-jobs.md)
- [Builds and execution](03-builds.md)
- [Logs and diagnostics](04-diagnostics.md)
- [Operations and plugins](05-operations.md)

**Setup:** Download `jenkins-cli.jar` from your own Jenkins instance. Set `JENKINS_URL` to an authorized server and use `-auth @jenkins-auth` with a private credentials file (username:API token), permission `chmod 600`; never commit it. Some commands trigger jobs or alter state.

**Official reference:** https://www.jenkins.io/doc/book/managing/cli/
