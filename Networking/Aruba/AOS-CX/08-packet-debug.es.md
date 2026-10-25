---
tags: [cli, aruba, aos-cx]
validation: not-lab-verified
---

# Captura y diagnóstico

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** AOS-CX 10.x; validar por modelo y release.

## `mirror session 1`

```text
configure terminal
mirror session 1
source interface 1/1/2 both
destination interface 1/1/3
enable
end
```

**Validar con:**

```text
show mirror | include 1
```

- **Sirve para:** Replica tráfico al analizador.
- **Parámetros:** source: tráfico; destination: puerto monitor.
- **Ejemplo de uso:** Analizar con Wireshark.

## `show mirror | include 1`

```text
show mirror | include 1
```

- **Sirve para:** Comprueba mirroring.
- **Parámetros:** include: ID sesión.
- **Ejemplo de uso:** Confirmar SPAN.

## `mirror session 1`

```text
configure terminal
mirror session 1
disable
end
```

**Validar con:**

```text
show mirror | include 1
```

- **Sirve para:** Deshabilita mirroring.
- **Parámetros:** disable: detiene replicación.
- **Ejemplo de uso:** Finalizar captura.

## `diag utilities tshark`

```text
diagnostic
diag utilities tshark
```

- **Sirve para:** Analiza paquetes enviados a CPU si es compatible.
- **Parámetros:** tshark: captura interactiva; Ctrl+C: detener.
- **Ejemplo de uso:** Diagnosticar paquete.

> Validar en laboratorio. Mirror/tshark requieren soporte y autorización; deshabilita al finalizar.
