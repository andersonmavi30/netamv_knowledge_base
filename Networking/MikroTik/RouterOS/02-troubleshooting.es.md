---
tags: [cli, mikrotik, routeros, troubleshooting]
vendor: MikroTik
os: "RouterOS"
versions: "7.x"
validation: not-lab-verified
---

# 🛠️ Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ MikroTik](../README.es.md)

**Plataforma:** MikroTik / RouterOS · **Versión orientativa:** 7.x.

## `/ping 192.0.2.10 count=5 src-address=192.0.2.1`

```text
/ping 192.0.2.10 count=5 src-address=192.0.2.1
```

- **Sirve para:** Envía cinco pings con IP origen definida.
- **Parámetros/filtros:** count: paquetes; src-address: IP origen.
- **Caso real:** Probar conectividad desde la LAN.

## `/tool traceroute 198.51.100.10`

```text
/tool traceroute 198.51.100.10
```

- **Sirve para:** Muestra saltos hasta el host.
- **Parámetros/filtros:** IP destino: equipo objetivo.
- **Caso real:** Localizar dónde se interrumpe la ruta.

## `/ip firewall connection print where src-address~"192.0.2.10"`

```text
/ip firewall connection print where src-address~"192.0.2.10"
```

- **Sirve para:** Busca sesiones cuyo origen es un host.
- **Parámetros/filtros:** where + ~: busca texto de IP, incluido IP:puerto.
- **Caso real:** Revisar conexiones de un host interno.

## `/log print where message~"error"`

```text
/log print where message~"error"
```

- **Sirve para:** Muestra logs que contienen error.
- **Parámetros/filtros:** message~: patrón de texto sensible a mayúsculas.
- **Caso real:** Buscar errores recientes.

## `/tool sniffer quick ip-protocol=icmp`

```text
/tool sniffer quick ip-protocol=icmp
```

- **Sirve para:** Observa paquetes ICMP en vivo.
- **Parámetros/filtros:** quick: vista en vivo; ip-protocol: filtra ICMP.
- **Caso real:** Ver si llegan los pings al router.
- **Precaución:** La captura puede mostrar datos sensibles; detener con Ctrl+C.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/328084/IP+Routing) · [Documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet+Sniffer)
