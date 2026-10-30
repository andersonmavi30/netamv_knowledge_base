# Check Point — Gaia / Security Gateway

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Check Point](../README.es.md)

Referencia operacional de Gaia y Security Gateway, diferenciando **Gaia Clish**, **Expert** y la política de seguridad gestionada en SmartConsole.

**Versión:** Gaia R8x (comprueba release exacto).

## Guías

- [Consultas y estado](01-show.es.md)
- [Diagnóstico](02-troubleshooting.es.md)
- [Interfaces y routing](03-interfaces.es.md)
- [Filtros de salida](04-filters.es.md)
- [Configuración](05-configuration.es.md)
- [Operación de firewall](06-operations.es.md)
- [Verificaciones operativas](07-field-commands.es.md)
- [Captura y debug](08-packet-debug.es.md)

**Filtros:** dentro de **Expert**, usa `clish -c "show ..." | grep ...`; no presupongas que el pipe Bash está disponible en el prompt Clish.

> Captura y debug pueden afectar el rendimiento y exponer datos.
