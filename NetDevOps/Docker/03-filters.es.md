---
tags: [docker, containers, netdevops, filters]
validation: not-lab-verified
---

# Filtros y diagnóstico

[🇬🇧 English](03-filters.md) · [🇨🇴 Español](03-filters.es.md) · [↩ Docker](README.es.md)

## `docker ps -a --filter "name=cisco"`

```bash
docker ps -a --filter "name=cisco"
```

- **Sirve para:** Filtra contenedores cuyo nombre contenga cisco.
- **Parámetros:** --filter name=: coincidencia parcial nativa.
- **Ejemplo de uso:** Localizar un contenedor de laboratorio Cisco.

## `docker ps -a --filter "status=exited"`

```bash
docker ps -a --filter "status=exited"
```

- **Sirve para:** Muestra únicamente contenedores con estado exited.
- **Parámetros:** --filter status=exited: filtra por estado.
- **Ejemplo de uso:** Encontrar servicios que se detuvieron.

## `docker images --filter "reference=*cisco*"`

```bash
docker images --filter "reference=*cisco*"
```

- **Sirve para:** Busca imágenes cuyo nombre coincida con cisco.
- **Parámetros:** --filter reference=: filtro de nombres con comodines.
- **Ejemplo de uso:** Identificar imágenes Cisco locales antes de limpiar.

## `docker ps -a --format '{{.Names}}' | grep -i cisco`

```bash
docker ps -a --format '{{.Names}}' | grep -i cisco
```

- **Sirve para:** Busca nombres de contenedores usando tubería de Linux.
- **Parámetros:** --format: devuelve nombres; | grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Buscar nombres Cisco en un host Linux.
- **Precaución:** Requiere shell con `grep` (Linux/WSL). Prefiere --filter por portabilidad.

## `docker images --format '{{.Repository}}:{{.Tag}}' | grep -i cisco`

```bash
docker images --format '{{.Repository}}:{{.Tag}}' | grep -i cisco
```

- **Sirve para:** Busca líneas repositorio:etiqueta de imágenes.
- **Parámetros:** --format: muestra repositorio y tag; grep -i: filtro.
- **Ejemplo de uso:** Encontrar versiones de imágenes por fabricante.
- **Precaución:** Depende del shell; alternativa: --filter reference=.

## `docker logs --tail 50 apache`

```bash
docker logs --tail 50 apache
```

- **Sirve para:** Consulta últimas 50 líneas de log del contenedor.
- **Parámetros:** --tail 50: últimas líneas; apache: nombre o ID.
- **Ejemplo de uso:** Diagnosticar por qué Apache no inicia.

## `docker logs apache 2>&1 | grep -i error`

```bash
docker logs apache 2>&1 | grep -i error
```

- **Sirve para:** Busca errores en logs con shell de Linux.
- **Parámetros:** 2>&1: combina stderr; | grep -i: busca sin distinguir mayúsculas.
- **Ejemplo de uso:** Reducir ruido en logs.
- **Precaución:** Solo si el shell admite grep y redirección.

> Ejemplos de referencia. Verifica nombre/ID, puertos y estado antes de ejecutar comandos que borren o interrumpan contenedores.

[Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
