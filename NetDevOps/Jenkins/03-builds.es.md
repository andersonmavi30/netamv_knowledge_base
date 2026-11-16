---
tags: [jenkins, cli, netdevops, cicd]
validation: not-lab-verified
---

# Builds y ejecución

[🇬🇧 English](03-builds.md) · [🇨🇴 Español](03-builds.es.md) · [↩ Jenkins](README.es.md)

**Plataforma:** Jenkins CLI / Jenkins LTS; ejemplos pendientes de validación en laboratorio.

## `build network-backup -s -v`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth build network-backup -s -v
```

- **Sirve para:** Iniciar un build autorizado de respaldo de red, esperar el resultado y mostrar la consola.
- **Parámetros:** `build network-backup`: ejecuta job; `-s`: espera fin; `-v`: muestra consola. El job puede modificar sistemas. `-s` (global): URL Jenkins; `-webSocket`: transporte.
- **Ejemplo de uso:** Ejecutar pipeline de respaldo aprobado y revisar resultado.
- **Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/

> Pendiente de validación en laboratorio; evita compartir logs con secretos.
