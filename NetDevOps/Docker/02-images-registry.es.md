---
tags: [docker, containers, netdevops, images-registry]
validation: not-lab-verified
---

# Imágenes y registros

[🇬🇧 English](02-images-registry.md) · [🇨🇴 Español](02-images-registry.es.md) · [↩ Docker](README.es.md)

## `docker images --filter "reference=*apache*"`

```bash
docker images --filter "reference=*apache*"
```

- **Sirve para:** Lista imágenes locales que coinciden con apache.
- **Parámetros:** --filter reference=: patrón de imagen/tag.
- **Ejemplo de uso:** Buscar imagen Apache personalizada.

## `docker rmi apache:php`

```bash
docker rmi apache:php
```

- **Sirve para:** Elimina una imagen local etiquetada.
- **Parámetros:** rmi: elimina imagen; apache:php: repositorio y etiqueta.
- **Ejemplo de uso:** Eliminar imagen de prueba obsoleta.
- **Precaución:** Destructivo; los contenedores que usan la imagen pueden impedir borrarla. No fuerces sin revisar.

## `docker commit apache andersonmavi30/apache:manual`

```bash
docker commit apache andersonmavi30/apache:manual
```

- **Sirve para:** Crea imagen desde la capa modificable de un contenedor.
- **Parámetros:** commit: nombre/ID y nueva imagen:etiqueta.
- **Ejemplo de uso:** Guardar cambio manual de laboratorio.
- **Precaución:** Los volúmenes no se incluyen; para reproducibilidad prefiere Dockerfile.

## `docker login`

```bash
docker login
```

- **Sirve para:** Inicia sesión en Docker Hub mediante el navegador.
- **Parámetros:** Sin opciones: Docker Hub; `--username` permite indicar el usuario.
- **Ejemplo de uso:** Autenticarse antes de `docker push andersonmavi30/apache:php`.
- **Precaución:** No incluyas contraseñas ni tokens en la terminal ni en el repositorio.

**Alternativa: especificar usuario (inicio de sesión interactivo):**

```bash
docker login --username andersonmavi30
```

## `docker tag apache:php andersonmavi30/apache:php`

```bash
docker tag apache:php andersonmavi30/apache:php
```

- **Sirve para:** Asigna un repositorio de Docker Hub a una imagen local.
- **Parámetros:** tag: imagen origen y nuevo repositorio:etiqueta.
- **Ejemplo de uso:** Preparar imagen local para Docker Hub.

## `docker push andersonmavi30/apache:php`

```bash
docker push andersonmavi30/apache:php
```

- **Sirve para:** Publica imagen etiquetada en un registro.
- **Parámetros:** push: imagen con repositorio; requiere permisos.
- **Ejemplo de uso:** Subir la imagen de laboratorio Apache/PHP.
- **Precaución:** Usa tu repositorio/namespace real; evita publicar secretos.

> Ejemplos de referencia. Verifica nombre/ID, puertos y estado antes de ejecutar comandos que borren o interrumpan contenedores.

[Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
