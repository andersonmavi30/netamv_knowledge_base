# FortiOS — Referencia de comandos

[🇬🇧 English](README.md) · [🇨🇴 Español](README.es.md) · [↩ Fortinet](../README.es.md)

**Versión orientativa:** FortiOS 7.x. No garantiza que todas las variantes del CLI estén disponibles.

- [Operación adicional](06-operations.es.md)

## Índice

- [Consultas / estado](01-show.es.md)
- [Diagnóstico](02-troubleshooting.es.md)
- [Configuración de interfaces](03-interfaces.es.md)
- [Filtros de salida](04-filters.es.md)
- [Configuración general](05-configuration.es.md)
- [🧪 Captura / debug](08-packet-debug.es.md)

## ✅ Validar versión y sintaxis

```text
get system status
config firewall address
    ?
```

Confirma la versión exacta y revisa la ayuda contextual (usa `?` en el nivel correcto).

> Ejemplos ilustrativos pendientes de validación en laboratorio. Consulta la documentación de tu versión antes de producción.

- [Más comandos operativos](07-field-commands.es.md)

- [Cinco verificaciones operativas nuevas](09-operational-checks.es.md)

- [Cinco búsquedas operativas nuevas](10-targeted-queries.es.md)

## Notas para VDOM, rutas y políticas

- Utiliza `config global` para el ámbito global; `config vdom` y `edit <VDOM>` para el contexto de un VDOM. `config vdom global` no es el comando para entrar en Global.
- En los enlaces inter-VDOM, configura interfaces, rutas y políticas según el tráfico que deba iniciarse. Las políticas son stateful: la respuesta de una sesión establecida no requiere por sí sola una política inversa; se necesitan reglas adicionales si se inicia tráfico en ambos sentidos.
- NAT no es obligatorio entre redes internas enrutadas, pero tampoco está prohibido: depende de diseño, solapamiento y requisitos. El VDOM de gestión puede originar FortiGuard y otros servicios locales; no asumas que es el único VDOM con acceso a Internet.
- `config system virtual-wan-link` es sintaxis antigua; FortiOS 7.x utiliza `config system sdwan`.

**Referencias:** https://docs.fortinet.com/document/fortigate/7.0.8/administration-guide/335646/inter-vdom-routing · https://docs.fortinet.com/document/fortigate/7.4.4/administration-guide/256518/configuring-sd-wan-in-the-cli
