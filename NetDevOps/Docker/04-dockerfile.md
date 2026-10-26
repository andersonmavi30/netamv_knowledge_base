---
tags: [docker, dockerfile, rockylinux, apache, php]
validation: not-lab-verified
---

# Dockerfile: Rocky Linux 9 + Apache + PHP

[🇬🇧 English](04-dockerfile.md) · [🇨🇴 Español](04-dockerfile.es.md) · [↩ Docker](README.md)

**Goal:** build an Apache/PHP demo image serving `hola.php`.

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

- **`FROM`:** Rocky Linux 9 base image.
- **`RUN`:** installs Apache, PHP and PHP-FPM, and creates `hola.php`.
- **`EXPOSE 80`:** documents the container port.
- **`CMD`:** starts PHP-FPM and keeps Apache in the foreground.

## Build and test

From the directory containing the example Dockerfile:

```bash
docker build -t apache:php .
docker run -d --name apache-php -p 127.0.0.1:8080:80 apache:php
curl -I http://localhost:8080/
```

Open in browser: `http://localhost:8080/hola.php`.

- **`docker build -t apache:php .`:** builds and tags from the current directory.
- **`docker run -d -p 127.0.0.1:8080:80`:** publishes container port 80 to local host port 8080 only.
- **`curl -I`:** checks HTTP response; open the PHP page in a browser to verify processing.

**Example file:** [`examples/rockylinux-apache-php/Dockerfile`](examples/rockylinux-apache-php/Dockerfile).

> **Lab only.** `phpinfo()` exposes sensitive details. Do not expose publicly. For production, separate concerns/services and remove `hola.php`.

[Rocky Linux PHP docs](https://docs.rockylinux.org/guides/web/php/) · [Dockerfile reference](https://docs.docker.com/reference/dockerfile/)
