---
tags: [cli, cisco, ios, troubleshooting]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🛠️ Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS · **Versiones de referencia:** IOS 15.x (classic; feature availability varies). Confirma el comando en tu versión instalada.

## `ping 192.0.2.10`

```text
ping 192.0.2.10
```

- **Sirve para:** Prueba conectividad IPv4.
- **Parámetros:** 192.0.2.10: destino.
- **Ejemplo de uso:** Verificar acceso a un host de laboratorio.

## `traceroute 192.0.2.10`

```text
traceroute 192.0.2.10
```

- **Sirve para:** Muestra los saltos hacia un destino.
- **Parámetros:** 192.0.2.10: destino.
- **Ejemplo de uso:** Ubicar dónde se interrumpe una ruta.

## `show interfaces GigabitEthernet0/0`

```text
show interfaces GigabitEthernet0/0
```

- **Sirve para:** Consulta estado y errores de una interfaz.
- **Parámetros:** GigabitEthernet0/0: nombre de interfaz según equipo.
- **Ejemplo de uso:** Buscar errores CRC.

## `show logging`

```text
show logging
```

- **Sirve para:** Muestra mensajes del registro.
- **Parámetros:** Sin opciones.
- **Ejemplo de uso:** Encontrar caída de enlace.

> Referencia breve, no validada en laboratorio. Valida con la ayuda de la CLI y documentación del modelo/release.

**Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html · https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/configuration/15-mt/ir-15-mt-book/ir-cfg-vir-if.html
