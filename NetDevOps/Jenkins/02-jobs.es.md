---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Gestión de jobs

[🇬🇧 English](02-jobs.md) · [🇨🇴 Español](02-jobs.es.md) · [↩ Jenkins](README.es.md)

**Plataforma:** Jenkins CLI / Jenkins LTS; ejemplos pendientes de validación en laboratorio.

## `list-jobs`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth list-jobs
```

- **Sirve para:** Listar jobs visibles para el usuario autenticado en la vista raíz de Jenkins.
- **Parámetros:** `list-jobs`: lista jobs según permisos de Jenkins; sin argumentos. `-s`: URL Jenkins; `-webSocket`: transporte.
- **Ejemplo de uso:** Identificar jobs NetDevOps antes de iniciar un pipeline.
- **Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/

> Pendiente de validación en laboratorio; proteger credenciales.
