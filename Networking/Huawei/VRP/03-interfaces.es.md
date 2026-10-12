---
tags: [cli, huawei, vrp, interfaces]
vendor: Huawei
os: "VRP"
versions: "S-series VRP V200 (platform/release specific)"
validation: not-lab-verified
---

# 🔌 Interfaces

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Huawei](../README.es.md)

**Plataforma:** Huawei / VRP · **Versión orientativa:** S-series VRP V200 (platform/release specific).

## `display interface brief | include GigabitEthernet0/0/1`

```text
display interface brief | include GigabitEthernet0/0/1
```

- **Sirve para:** Encuentra una interfaz física.
- **Parámetros/filtros:** | include: filtra líneas.
- **Caso real:** Revisar estado de puerto.

## `system-view`

```text
system-view
interface GigabitEthernet0/0/1
 description LAB-UPLINK
 undo shutdown
 quit
return
```

- **Sirve para:** Etiqueta y habilita un puerto Ethernet.
- **Parámetros/filtros:** system-view: configuración; undo shutdown: habilita; quit: sale de interfaz; return: vista usuario.
- **Caso real:** Activar un uplink de laboratorio.
- **Precaución:** Cambia estado de enlace; los roles varían según VRP.

## `system-view`

```text
system-view
vlan 10
 quit
interface Vlanif10
 ip address 192.0.2.1 255.255.255.0
 quit
return
```

- **Sirve para:** Crea VLAN 10 e interfaz L3 donde sea compatible.
- **Parámetros/filtros:** Vlanif10: interfaz VLAN; ip address: IP/máscara.
- **Caso real:** Gestionar switch por VLAN 10.
- **Precaución:** Algunos equipos requieren configuración L2/L3 previa.

## `display ip interface brief | include Vlanif10`

```text
display ip interface brief | include Vlanif10
```

- **Sirve para:** Verifica IP y estado de VLANIF.
- **Parámetros/filtros:** | include: muestra coincidencias.
- **Caso real:** Confirmar 192.0.2.1/24.

> Verifica los comandos y opciones mediante la ayuda CLI del equipo; ejemplos pendientes de validación en laboratorio.

**Referencias del fabricante:** [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100333403/cdd85713/basic-interface-configuration-commands) · [Documentation](https://info.support.huawei.com/enterprise/en/doc/EDOC1100335692/c1ebaf03/basic-ip-routing-configuration)
