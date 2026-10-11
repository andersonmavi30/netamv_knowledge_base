---
tags: [cli, fortinet, fortios, configuration]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# ⚙️ Configuración general

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Fortinet](../README.es.md)

**Plataforma:** Fortinet / FortiOS · **Versiones de referencia:** FortiOS 7.x. Confirma el comando en tu versión instalada.

## `config system global`

```text
config system global
    set hostname FGT-LAB
end
```

- **Sirve para:** Cambia el nombre del firewall.
- **Parámetros:** set hostname: nuevo nombre; end: aplicar y salir.
- **Ejemplo de uso:** Nombrar un FortiGate de laboratorio.

- **Verificación:** `get system status | grep -i hostname` — Comprueba el hostname configurado.

## `config system dns`

```text
config system dns
    set primary 1.1.1.1
    set secondary 9.9.9.9
end
```

- **Sirve para:** Configura los servidores DNS del dispositivo.
- **Parámetros:** primary: DNS preferido; secondary: DNS alterno.
- **Ejemplo de uso:** Resolver FQDN desde el firewall.
- **Precaución:** Cambiar DNS puede afectar actualizaciones y objetos FQDN.

- **Verificación:** `show system dns | grep -i primary` — Verifica el DNS primario.

## `config firewall address`

```text
config firewall address
    edit "LAB-NET"
        set subnet 192.0.2.0 255.255.255.0
    next
end
```

- **Sirve para:** Crea un objeto de dirección IPv4 de una subred.
- **Parámetros:** edit: nombre; set subnet: red y máscara; next: guardar.
- **Ejemplo de uso:** Usar LAB-NET en una política de prueba.

- **Verificación:** `show firewall address | grep -f LAB-NET` — Revisa el objeto creado.

## `config firewall addrgrp`

```text
config firewall addrgrp
    edit "LAB-SOURCES"
        set member "LAB-NET"
    next
end
```

- **Sirve para:** Crea un grupo con un objeto de direcciones existente.
- **Parámetros:** set member: objetos existentes; reemplaza los miembros actuales.
- **Ejemplo de uso:** Agrupar orígenes del laboratorio.
- **Precaución:** Verifica que exista LAB-NET; set member puede sobrescribir miembros.

- **Verificación:** `show firewall addrgrp | grep -f LAB-SOURCES` — Revisa los miembros del grupo.

## `config router static`

```text
config router static
    edit 0
        set dst 198.51.100.0 255.255.255.0
        set gateway 192.0.2.254
        set device "port3"
    next
end
```

- **Sirve para:** Agrega una ruta estática IPv4.
- **Parámetros:** edit 0: nueva entrada; dst: destino/máscara; gateway: siguiente salto; device: interfaz de salida.
- **Ejemplo de uso:** Llegar a una red de laboratorio por port3.
- **Precaución:** Supone que port3 llega a 192.0.2.254; una ruta incorrecta afecta el tráfico.

- **Verificación:** `get router info routing-table all | grep 198.51.100` — Busca la ruta instalada; comprueba la conectividad por separado.

## `config firewall service custom`

```text
config firewall service custom
    edit "LAB-HTTPS-8443"
        set tcp-portrange 8443
    next
end
```

- **Sirve para:** Define un servicio TCP personalizado para políticas.
- **Parámetros:** tcp-portrange: puerto o rango de destino TCP.
- **Ejemplo de uso:** Usar el puerto 8443 en una política de laboratorio.

- **Verificación:** `show firewall service custom | grep -f LAB-HTTPS-8443` — Consulta los ajustes del servicio TCP personalizado.


> Referencia breve, no validada en laboratorio. Valida con la ayuda de la CLI y documentación del modelo/release.

**Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.2/administration-guide/777334/basic-configuration · https://docs.fortinet.com/document/fortigate/7.6.6/cli-reference/200835411/config-router-static
