---
tags: [cli, fortinet, fortios, troubleshooting]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🛠️ Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Fortinet](../README.es.md)

**Plataforma:** Fortinet / FortiOS · **Compatibilidad:** FortiOS 7.x (comprueba tu versión exacta).

## `execute ping 192.0.2.10`

```text
execute ping 192.0.2.10
```

- **Sirve para:** Prueba conectividad ICMP hacia un host.
- **Parámetros:** Cambia la IP de documentación por la del laboratorio.
- **Ejemplo de uso:** Probar alcance antes de revisar políticas.

- **Filtro práctico:** `get router info routing-table all | grep 192.0.2` — Tras fallar el ping, busca el prefijo del laboratorio.

## `execute traceroute 192.0.2.10`

```text
execute traceroute 192.0.2.10
```

- **Sirve para:** Consulta los saltos de red hacia un destino.
- **Parámetros:** La IP es el destino.
- **Ejemplo de uso:** Detectar una ruta inesperada.

- **Filtro práctico:** `get router info routing-table all | grep 192.0.2` — Comprueba la ruta después del traceroute.

## `diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 l`

```text
diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 l
```

- **Sirve para:** Captura paquetes coincidentes; termina tras 20 paquetes.
- **Parámetros:** any: todas las interfaces; filtro: host y puerto TCP; 4: interfaz y cabecera; 20: máximo de paquetes; l: hora local.
- **Ejemplo de uso:** Confirmar interfaz de entrada y salida del TCP/443.
- **Precaución:** Las capturas pueden mostrar metadatos. Limita el alcance; Ctrl+C detiene antes.

- **Filtro práctico:** `diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 l` — El filtro BPF ya está dentro del sniffer; no requiere pipe.

## `diagnose vpn tunnel list`

```text
diagnose vpn tunnel list | grep -i name=
```

- **Sirve para:** Consulta información de diagnóstico de túneles IPsec.
- **Parámetros:** Sin parámetros.
- **Ejemplo de uso:** Comprobar SAs en el diagnóstico de VPN.

- **Filtro práctico:** `diagnose vpn tunnel list | grep -i name=` — Busca nombres de túneles; revisa la salida completa para conocer su estado.


> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966
