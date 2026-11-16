---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# CLI y autenticación

[🇬🇧 English](01-cli.md) · [🇨🇴 Español](01-cli.es.md) · [↩ Jenkins](README.es.md)

**Plataforma:** Jenkins CLI / Jenkins LTS; ejemplos pendientes de validación en laboratorio.

## `java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket help`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket help
```

- **Sirve para:** Listar los comandos CLI disponibles en la instancia Jenkins, según permisos y plugins.
- **Parámetros:** `-jar`: ejecuta el archivo JAR; `-s`: URL del servidor; `-webSocket`: transporte WebSocket; `help`: lista comandos.
- **Ejemplo de uso:** Descubrir las operaciones disponibles antes de automatizar Jenkins en el laboratorio.
- **Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/

> Pendiente de validación en laboratorio.
