# Jenkins — Referencia CLI

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ NetDevOps](../README.es.md)

**Compatibilidad:** Jenkins LTS / Jenkins CLI (Java); confirma versión, permisos y comandos disponibles con `help`.

- [CLI y autenticación](01-cli.es.md)
- [Gestión de jobs](02-jobs.es.md)
- [Builds y ejecución](03-builds.es.md)
- [Logs y diagnóstico](04-diagnostics.es.md)
- [Operaciones y plugins](05-operations.es.md)

**Preparación:** Descarga `jenkins-cli.jar` desde tu propia instancia Jenkins. Define `JENKINS_URL` apuntando a un servidor autorizado y usa `-auth @jenkins-auth` con un archivo privado de credenciales (usuario:API token), permisos `chmod 600`; no lo publiques ni lo incluyas en Git. Algunos comandos modifican o ejecutan jobs.

**Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/
