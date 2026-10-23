# Palo Alto Networks — PAN-OS

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Fabricante](../README.es.md)

Base de referencia para Palo Alto Networks NGFW. Los comandos de consulta operan en `>`; para modificar configuración entra con `configure` (`#`). Los cambios pasan a configuración candidata y requieren `commit` tras revisión.

**Compatibilidad:** PAN-OS genérico (confirma versión y plataforma).

```text
show system info | match sw-version
show system info | match hostname
```

## Guías CLI

- [🔎 Consultas y estado](01-show.es.md)
- [🛠️ Diagnóstico](02-troubleshooting.es.md)
- [🔌 Interfaces y enrutamiento](03-interfaces.es.md)
- [🔍 Filtros de salida y búsquedas](04-filters.es.md)
- [⚙️ Ejemplos de configuración](05-configuration.es.md)
- [🧭 VPN, políticas y operación](06-operations.es.md)
- [🧰 Consultas adicionales de campo](07-field-commands.es.md)
- [🧪 Sniffer, captura y debug](08-packet-debug.es.md)

> No supongas que `grep` o `include` funciona como en Fortinet/Cisco. PAN-OS utiliza `| match`, `| except` y filtros internos según comando.

**Seguridad:** la captura consume recursos y el commit puede aplicar cambios pendientes.
