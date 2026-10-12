---
tags: [cli, huawei, vrp, troubleshooting]
vendor: Huawei
os: "VRP"
versions: "S-series VRP V200 (platform/release specific)"
validation: not-lab-verified
---

# 🛠️ Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Huawei](../README.es.md)

**Plataforma:** Huawei / VRP · **Versión orientativa:** S-series VRP V200 (platform/release specific).

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Sirve para:** Prueba conectividad ICMP.
- **Parámetros/filtros:** IP: destino.
- **Caso real:** Verificar camino al gateway.

## `tracert 198.51.100.10`

```text
tracert 198.51.100.10
```

- **Sirve para:** Muestra saltos IPv4 al destino.
- **Parámetros/filtros:** IP: dirección destino.
- **Caso real:** Localizar dónde se corta el tráfico.

## `display interface GigabitEthernet0/0/1`

```text
display interface GigabitEthernet0/0/1
```

- **Sirve para:** Consulta estadísticas y errores del puerto.
- **Parámetros/filtros:** La interfaz cambia según el modelo.
- **Caso real:** Buscar errores o caídas.

## `display logbuffer | include DOWN`

```text
display logbuffer | include DOWN
```

- **Sirve para:** Busca logs con DOWN.
- **Parámetros/filtros:** | include: solo líneas coincidentes.
- **Caso real:** Encontrar interfaces que caen.

## `display arp | include 192.0.2.10`

```text
display arp | include 192.0.2.10
```

- **Sirve para:** Busca entrada ARP del host.
- **Parámetros/filtros:** | include: coincidencia de texto, no contexto completo.
- **Caso real:** Comprobar aprendizaje MAC.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
