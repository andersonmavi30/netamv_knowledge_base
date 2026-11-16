---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Logs y diagnóstico

[🇬🇧 English](04-diagnostics.md) · [🇨🇴 Español](04-diagnostics.es.md) · [↩ Jenkins](README.es.md)

**Plataforma:** Jenkins CLI / Jenkins LTS; ejemplos pendientes de validación en laboratorio.

## `console network-backup -f`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth console network-backup -f
```

- **Sirve para:** Seguir la salida de consola de la última ejecución del job.
- **Parámetros:** `console`: salida del build; `network-backup`: job; `-f`: sigue logs hasta que termine. `-s` (global): URL Jenkins; `-webSocket`: transporte.
- **Ejemplo de uso:** Investigar logs de orquestación Jenkins–AWX sin iniciar otro job.
- **Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/

> Pendiente de validación en laboratorio; evita compartir logs con secretos.
