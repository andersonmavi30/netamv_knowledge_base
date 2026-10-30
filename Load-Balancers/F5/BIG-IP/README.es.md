# F5 BIG-IP — TMOS / LTM

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ F5](../README.es.md)

Referencia de comandos de F5 BIG-IP con enfoque en virtual servers, pools, conexiones, red y captura. Los comandos comienzan con `tmsh` desde Bash; dentro de tmsh se omite ese prefijo.

## Categorías

- [Consultas y estado](01-show.es.md)
- [Diagnóstico](02-troubleshooting.es.md)
- [Interfaces y routing](03-interfaces.es.md)
- [Filtros de salida](04-filters.es.md)
- [Configuración](05-configuration.es.md)
- [Operación LTM](06-operations.es.md)
- [Verificaciones adicionales](07-field-commands.es.md)
- [Captura y debug](08-packet-debug.es.md)

**Filtro:** `list ltm virtual | grep -i lab` dentro de `tmsh`; desde Bash, `tmsh list ltm virtual | grep -i lab`.

> Valida versión, partición (`/Common`) y permisos antes de aplicar cambios.
