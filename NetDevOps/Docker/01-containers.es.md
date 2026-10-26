---
tags: [docker, containers, netdevops, containers]
validation: not-lab-verified
---

# Ciclo de vida de contenedores

[🇬🇧 English](01-containers.md) · [🇨🇴 Español](01-containers.es.md) · [↩ Docker](README.es.md)

## `docker ps -a --filter "name=apache"`

```bash
docker ps -a --filter "name=apache"
```

- **Sirve para:** Lista contenedores, incluso detenidos, cuyo nombre coincida con apache.
- **Parámetros:** -a: incluye detenidos; --filter name=: coincidencia de nombre.
- **Ejemplo de uso:** Buscar contenedor de laboratorio antes de cambiar.

## `docker run -d --name apache -p 127.0.0.1:8080:80 httpd:2.4`

```bash
docker run -d --name apache -p 127.0.0.1:8080:80 httpd:2.4
```

- **Sirve para:** Crea e inicia Apache desde la imagen oficial.
- **Parámetros:** -d: segundo plano; --name: nombre; -p: IP host:puerto host:puerto contenedor.
- **Ejemplo de uso:** Abrir http://localhost:8080.
- **Precaución:** Usa `httpd:2.4`, no una supuesta imagen `apache`; publica solo en localhost para el lab.

## `docker stop apache`

```bash
docker stop apache
```

- **Sirve para:** Detiene ordenadamente el contenedor.
- **Parámetros:** apache: nombre o ID.
- **Ejemplo de uso:** Detener Apache antes de mantenimiento.

## `docker start apache`

```bash
docker start apache
```

- **Sirve para:** Inicia un contenedor existente detenido.
- **Parámetros:** apache: nombre o ID.
- **Ejemplo de uso:** Reanudar laboratorio.

## `docker kill apache`

```bash
docker kill apache
```

- **Sirve para:** Finaliza forzosamente el contenedor.
- **Parámetros:** kill: envía SIGKILL por defecto; apache: destino.
- **Ejemplo de uso:** Usar solo si no responde a stop.
- **Precaución:** Puede interrumpir escrituras; prefiere docker stop.

## `docker rename apache apache-lab`

```bash
docker rename apache apache-lab
```

- **Sirve para:** Renombra un contenedor.
- **Parámetros:** Nombre actual y nombre nuevo.
- **Ejemplo de uso:** Distinguir servicio de prueba de producción.

## `docker exec -it apache-lab /bin/sh`

```bash
docker exec -it apache-lab /bin/sh
```

- **Sirve para:** Abre consola interactiva de un contenedor en ejecución.
- **Parámetros:** -i: interactivo; -t: terminal; /bin/sh: shell común.
- **Ejemplo de uso:** Revisar archivos y procesos dentro de Apache.
- **Precaución:** Usa `/bin/bash` si existe; `-ti` y `-it` son equivalentes.

## `docker rm -f apache-lab`

```bash
docker rm -f apache-lab
```

- **Sirve para:** Elimina forzosamente un contenedor, incluso activo.
- **Parámetros:** -f: fuerza detención y eliminación; nombre destino.
- **Ejemplo de uso:** Limpiar contenedor de laboratorio.
- **Precaución:** Destructivo: comprueba nombre y volúmenes antes de usar.

> Ejemplos de referencia. Verifica nombre/ID, puertos y estado antes de ejecutar comandos que borren o interrumpan contenedores.

[Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
