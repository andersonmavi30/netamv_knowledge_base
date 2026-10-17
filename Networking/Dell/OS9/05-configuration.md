---
tags: [cli, dell, os9, configuration]
validation: not-lab-verified
---

# Configuration — Dell OS9

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Index](README.md)

**Compatibility:** Dell Networking OS9 / Force10; confirm the platform and FTOS-derived CLI. Verify with `show version` and `?`.

## `hostname DELL-LAB`

```text
configure
hostname DELL-LAB
end
```

- **Purpose:** Set hostname on compatible OS9 versions.
- **Options:** hostname: device name.
- **Real use:** Name test switch.

## `write memory`

```text
write memory
```

- **Purpose:** Save validated settings.
- **Options:** write memory: persist configuration.
- **Real use:** Keep configuration after reload.

## `show configuration`

```text
show configuration
```

- **Purpose:** Inspect configuration in supporting OS9 modes.
- **Options:** Available in supported configuration contexts.
- **Real use:** Review before save.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://i.dell.com/sites/doccontent/shared-content/data-sheets/en/Documents/ESG-Dell-Force10-FTOS-CLI-Spec-Sheet.pdf)
