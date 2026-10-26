---
tags: [docker, dockerfile, rockylinux, apache, php]
validation: not-lab-verified
---

# Dockerfile: Rocky Linux 9 + Apache + PHP

[🇬🇧 English](04-dockerfile.md) · [🇨🇴 Español](04-dockerfile.es.md) · [↩ Docker](README.es.md)

**Objetivo:** construir una imagen de prueba con Apache, PHP y `hola.php`.

## `Dockerfile`

```dockerfile
FROM rockylinux:9

# Apache + PHP-FPM (Rocky Linux 9)
RUN dnf -y install httpd php php-cli php-common php-fpm && dnf clean all

RUN printf '%s\n' '<?php phpinfo(); ?>' > /var/www/html/hola.php

EXPOSE 80

# Lab-only: run PHP-FPM and Apache together.
CMD ["/bin/sh", "-c", "/usr/sbin/php-fpm -D && exec /usr/sbin/httpd -DFOREGROUND"]
```

- **`FROM`:** imagen base Rocky Linux 9.
- **`RUN`:** instala Apache, PHP y PHP-FPM, y crea `hola.php`.
- **`EXPOSE 80`:** documenta el puerto interno.
- **`CMD`:** inicia PHP-FPM y deja Apache en primer plano.

## Construir y probar

Desde el directorio que contiene el Dockerfile de ejemplo:

```bash
docker build -t apache:php .
docker run -d --name apache-php -p 127.0.0.1:8080:80 apache:php
curl -I http://localhost:8080/
```

Abrir en navegador: `http://localhost:8080/hola.php`.

- **`docker build -t apache:php .`:** crea imagen etiquetada usando el directorio actual como contexto.
- **`docker run -d -p 127.0.0.1:8080:80`:** publica el puerto 80 del contenedor solo en el localhost del host por el puerto 8080.
- **`curl -I`:** comprueba respuesta HTTP; la página PHP se verifica abriéndola en el navegador.

**Ubicación real del ejemplo:** [`examples/rockylinux-apache-php/Dockerfile`](examples/rockylinux-apache-php/Dockerfile).

> **Solo laboratorio.** `phpinfo()` muestra detalles sensibles; no expongas esta página públicamente. Para producción separa procesos/servicios y retira `hola.php` del contenedor.

[Rocky Linux PHP docs](https://docs.rockylinux.org/guides/web/php/) · [Dockerfile reference](https://docs.docker.com/reference/dockerfile/)
