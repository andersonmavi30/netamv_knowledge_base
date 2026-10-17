---
tags: [cli, dell, os10, packet-debug]
validation: not-lab-verified
---

# Mirroring / debug — Dell OS10

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** Dell SmartFabric OS10 (PowerSwitch hardware/release dependent). Verifica con `show version` y `?`.

> ⚠️ Dell no usa un sniffer universal. Port mirroring exige un puerto de análisis y autorización. Detén las sesiones al terminar; los paquetes pueden incluir datos sensibles.

## `monitor session 1`

```text
configure terminal
monitor session 1
 source interface ethernet 1/1/7 rx
 destination interface ethernet 1/1/1
 no shut
 exit
end
```

- **Sirve para:** Replica paquetes recibidos a puerto de análisis; conecta Wireshark allí.
- **Parámetros:** rx: entrada; destination: puerto monitor; no shut: habilita.
- **Caso real:** Investigar pérdida de tráfico de aplicación.

## `show monitor session all`

```text
show monitor session all
```

- **Sirve para:** Consulta estado de mirroring.
- **Parámetros:** all: todas las sesiones.
- **Caso real:** Confirmar sesión activa.

## `show interface ethernet 1/1/7 | grep error`

```text
show interface ethernet 1/1/7 | grep error
```

- **Sirve para:** Busca errores antes de capturar.
- **Parámetros:** | grep: filtra líneas.
- **Caso real:** Verificar fallos en el origen.

## `no monitor session 1`

```text
configure terminal
no monitor session 1
end
```

- **Sirve para:** Elimina sesión temporal.
- **Parámetros:** no: borra sesión.
- **Caso real:** Limpiar al terminar.

> Los comandos se deben validar en la versión y modelo instalados; no se han probado en laboratorio.

[Guía de Dell](https://www.dell.com/support/manuals/en-us/dell-emc-smartfabric-os10/smartfabric-os-user-guide-10-5-0/Filter-show-commands?guid=guid-758c857a-eba2-477a-a8f5-f0738c185e54&lang=en-us)
