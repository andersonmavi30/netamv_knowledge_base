---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Captura y depuración — Fortinet FortiOS

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** FortiOS 7.x.

> ⚠️ Captura y debug pueden generar carga o datos sensibles. Utilízalos solo en entornos autorizados, con filtros y límites; detén al finalizar.

## diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 a

```text
diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 a
```

- **Sirve para:** Captura hasta 20 paquetes TCP/443 del host, mostrando interfaces.
- **Parámetros:** any: todas las interfaces; BPF: host/puerto; 4: cabecera e interfaz; 20: máximo; a: hora absoluta.
- **Caso real:** Identificar interfaces de entrada/salida en una conexión HTTPS fallida.

## diagnose sniffer packet any 'arp or icmp' 4 20 a

```text
diagnose sniffer packet any 'arp or icmp' 4 20 a
```

- **Sirve para:** Revisa ARP e ICMP con captura limitada.
- **Parámetros:** arp or icmp: alternativas BPF; 20: máximo.
- **Caso real:** Ver si ARP y ping llegan al firewall.

## diagnose debug disable

```text
diagnose debug disable
diagnose debug reset
```

- **Sirve para:** Detiene el debug y limpia filtros anteriores.
- **Parámetros:** disable: detiene depuración; reset: limpia opciones.
- **Caso real:** Dejar el firewall sin debug después del diagnóstico.

**Referencia del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/administration-guide/680228/performing-a-sniffer-trace-cli-and-packet-capture

**Aviso:** no todos los equipos soportan sniffer/EPC en hardware de forwarding. Debug de protocolos no equivale a PCAP.

## `diagnose sniffer packet any 'src host 192.0.2.10 and dst host 198.51.100.20' 4 20 a`

```text
diagnose sniffer packet any 'src host 192.0.2.10 and dst host 198.51.100.20' 4 20 a
```

- **Sirve para:** Capturar hasta 20 paquetes entre origen y destino definidos.
- **Parámetros:** `any`: todas interfaces; `src/dst host`: filtro de dirección; `4`: cabecera/interfaz; `20`: límite; `a`: timestamp absoluto.
- **Ejemplo de uso:** Verificar entrada y salida de un flujo de prueba.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.8/administration-guide/680228/performing-a-sniffer-trace-or-packet-capture

> Pendiente de validación en laboratorio. Usar solo durante diagnóstico autorizado.

## `diagnose sniffer packet port1 'src host 192.0.2.10 and icmp' 4 20 a`

```text
diagnose sniffer packet port1 'src host 192.0.2.10 and icmp' 4 20 a
```

- **Sirve para:** Capturar una traza ICMP limitada desde un origen en port1.
- **Parámetros:** `port1`: interfaz ejemplo; `src host`: origen; `icmp`: protocolo; `4 20 a`: detalle, cantidad y timestamp.
- **Ejemplo de uso:** Comprobar si ICMP llega al puerto interno esperado.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.8/administration-guide/680228/performing-a-sniffer-trace-or-packet-capture

> Pendiente de validación en laboratorio. Usar solo durante diagnóstico autorizado.

## `diagnose debug flow trace stop`

```text
diagnose debug flow trace stop
```

- **Sirve para:** Detener una sesión activa de trazas de flujo.
- **Parámetros:** `flow trace stop`: detiene el trace; usar `diagnose debug reset` para limpieza completa.
- **Ejemplo de uso:** Cerrar las trazas cuando ya se obtuvo evidencia.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio. Usar solo durante diagnóstico autorizado.

## `diagnose debug flow filter clear`

```text
diagnose debug flow filter clear
```

- **Sirve para:** Limpiar filtros previos del debug de flujo.
- **Parámetros:** `flow filter clear`: elimina filtros IPv4 de trazas.
- **Ejemplo de uso:** Preparar una sesión de diagnóstico limpia.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; recuerda detener y resetear el debug.

## `diagnose debug flow filter addr 192.0.2.10`

```text
diagnose debug flow filter addr 192.0.2.10
```

- **Sirve para:** Filtrar el tráfico relacionado con una IP específica.
- **Parámetros:** `addr`: coincide con IP del host; `192.0.2.10`: ejemplo.
- **Ejemplo de uso:** Reducir los logs a un host de prueba.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; recuerda detener y resetear el debug.

## `diagnose debug flow filter saddr 192.0.2.10`

```text
diagnose debug flow filter saddr 192.0.2.10
```

- **Sirve para:** Filtrar paquetes cuyo origen es una dirección IPv4 concreta.
- **Parámetros:** `saddr`: filtro por IPv4 origen.
- **Ejemplo de uso:** Rastrear tráfico generado por una estación.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; recuerda detener y resetear el debug.

## `diagnose debug flow filter daddr 198.51.100.20`

```text
diagnose debug flow filter daddr 198.51.100.20
```

- **Sirve para:** Filtrar paquetes hacia una dirección IPv4 destino.
- **Parámetros:** `daddr`: filtro por IPv4 destino.
- **Ejemplo de uso:** Comprobar políticas hacia un servidor.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; recuerda detener y resetear el debug.

## `diagnose debug flow trace start 20`

```text
diagnose debug flow trace start 20
```

- **Sirve para:** Iniciar hasta 20 registros de traza del flujo filtrado.
- **Parámetros:** `trace start 20`: inicia una traza limitada; configurar filtros primero.
- **Ejemplo de uso:** Revisar decisiones de política y routing de una sesión.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; detener con `diagnose debug disable`, `diagnose debug flow trace stop` y `diagnose debug reset`.

## `diagnose debug flow show function-name enable`

```text
diagnose debug flow show function-name enable
```

- **Sirve para:** Incluir nombres de funciones internas en mensajes del debug.
- **Parámetros:** `show function-name enable`: agrega nombres de función a la salida.
- **Ejemplo de uso:** Identificar la etapa en que se descarta un paquete.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; detener con `diagnose debug disable`, `diagnose debug flow trace stop` y `diagnose debug reset`.

## `diagnose debug flow show iprope enable`

```text
diagnose debug flow show iprope enable
```

- **Sirve para:** Incluir detalles del procesamiento de políticas cuando la versión lo permita.
- **Parámetros:** `show iprope enable`: detalles del motor de políticas; depende de versión.
- **Ejemplo de uso:** Revisar coincidencias de políticas en una traza.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; detener con `diagnose debug disable`, `diagnose debug flow trace stop` y `diagnose debug reset`.

## `diagnose debug enable`

```text
diagnose debug enable
```

- **Sirve para:** Habilitar la impresión de diagnóstico previamente configurado con filtros.
- **Parámetros:** `debug enable`: comienza a mostrar mensajes; detener luego con disable y reset.
- **Ejemplo de uso:** Iniciar diagnóstico de políticas tras limitar la cantidad de trazas.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.10/administration-guide/54688/debugging-the-packet-flow

> Pendiente de validación en laboratorio; detener con `diagnose debug disable`, `diagnose debug flow trace stop` y `diagnose debug reset`.
