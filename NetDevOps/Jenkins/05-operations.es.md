---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Operaciones y plugins

[🇬🇧 English](05-operations.md) · [🇨🇴 Español](05-operations.es.md) · [↩ Jenkins](README.es.md)

**Plataforma:** Jenkins CLI / Jenkins LTS; ejemplos pendientes de validación en laboratorio.

## `version`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth version
```

- **Sirve para:** Mostrar la versión del controlador Jenkins que informa la CLI.
- **Parámetros:** `version`: versión del servidor; `-s` global: URL; `-webSocket`: transporte. `-auth @jenkins-auth`: credenciales desde archivo protegido.
- **Ejemplo de uso:** Registrar versión de Jenkins antes de diagnosticar compatibilidad.
- **Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/

> Pendiente de validación en laboratorio.
