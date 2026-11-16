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

## `who-am-i`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth who-am-i
```

- **Sirve para:** Mostrar identidad y permisos reconocidos para la conexión CLI.
- **Parámetros:** `-auth @jenkins-auth`: carga usuario:token API desde archivo privado; `who-am-i`: identidad actual. `-s`: URL Jenkins; `-webSocket`: transporte.
- **Ejemplo de uso:** Comprobar credenciales y permisos mínimos antes de consultar los jobs.
- **Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/

> Pendiente de validación en laboratorio; proteger credenciales.

## `help build`

```bash
java -jar jenkins-cli.jar -s "$JENKINS_URL" -webSocket -auth @jenkins-auth help build
```

- **Sirve para:** Mostrar sintaxis y parámetros admitidos para el comando CLI build.
- **Parámetros:** `help build`: ayuda del comando build; los flags dependen de la versión. `-auth @jenkins-auth`: credenciales desde archivo protegido.
- **Ejemplo de uso:** Confirmar flags compatibles antes de iniciar un pipeline aprobado.
- **Referencia oficial:** https://www.jenkins.io/doc/book/managing/cli/

> Pendiente de validación en laboratorio.
