FROM rockylinux:9

# Apache + PHP-FPM (Rocky Linux 9)
RUN dnf -y install httpd php php-cli php-common php-fpm && dnf clean all

RUN printf '%s\n' '<?php phpinfo(); ?>' > /var/www/html/hola.php

EXPOSE 80

# Lab-only: run PHP-FPM and Apache together.
CMD ["/bin/sh", "-c", "/usr/sbin/php-fpm -D && exec /usr/sbin/httpd -DFOREGROUND"]
