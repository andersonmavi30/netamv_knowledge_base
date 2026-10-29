---
tags: [cli, cisco, ios, interfaces]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# 🔌 Configuración de interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS · **Versiones de referencia:** IOS 15.x (classic; feature availability varies). Confirma el comando en tu versión instalada.

## `configure terminal`

```text
configure terminal
interface GigabitEthernet0/0
 description LAB-LAN
 ip address 192.0.2.1 255.255.255.0
 no shutdown
end
```

- **Sirve para:** Configura la dirección IPv4 y habilita una interfaz.
- **Parámetros:** description: etiqueta; ip address: IP y máscara; no shutdown: habilita puerto.
- **Ejemplo de uso:** Habilitar la LAN de laboratorio.
- **Precaución:** Modificar interfaces de producción puede interrumpir la conexión.

- **Filtro práctico:** `show running-config | section ^interface GigabitEthernet0/0` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.


## `show running-config interface GigabitEthernet0/0`

```text
show running-config interface GigabitEthernet0/0
```

- **Sirve para:** Consulta configuración de interfaz en versiones que la soportan.
- **Parámetros:** Nombre: reemplazar según el modelo.
- **Ejemplo de uso:** Revisar configuración de la LAN.

- **Filtro práctico:** `show ip interface brief | include GigabitEthernet0/0` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## `show interfaces description | include UPLINK`

```text
show interfaces description | include UPLINK
```

- **Sirve para:** Encuentra estado y descripciones de interfaces identificadas como UPLINK.
- **Parámetros:** description: etiquetas y estado; | include UPLINK: líneas coincidentes.
- **Ejemplo de uso:** Localizar el uplink WAN o core sin recorrer todos los puertos.
- **Referencia:** [Documentación del fabricante](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/command/ir-cr-book/ir-s4.html)

> Referencia breve, no validada en laboratorio. Valida con la ayuda de la CLI y documentación del modelo/release.

**Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/configuration/15-mt/ir-15-mt-book/ir-cfg-vir-if.html
