---
tags: [cli, dell, os6, filters]
validation: not-lab-verified
---

# Output filters — Dell OS6

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Index](README.md)

**Compatibility:** OS6 / N-Series; CLI output filtering is available in OS6 6.6+ where supported. Verify with `show version` and `?`.

## `show running-config | include hostname`

```text
show running-config | include hostname
```

- **Purpose:** Find only the hostname configuration.
- **Options:** | include: matching lines.
- **Real use:** Identify the switch quickly.

## `show running-config | section interface`

```text
show running-config | section interface
```

- **Purpose:** Find interface configuration sections.
- **Options:** | section: matching block.
- **Real use:** Inspect port configurations.

## `show interfaces status | include 1/0/1`

```text
show interfaces status | include 1/0/1
```

- **Purpose:** Find an exact port in a list.
- **Options:** | include: search text.
- **Real use:** Check the uplink.

## `show logging | exclude LINK`

```text
show logging | exclude LINK
```

- **Purpose:** Hide repetitive link messages.
- **Options:** | exclude: omit matches.
- **Real use:** Focus on other alarms.

> Validate commands on the installed model and release; not lab-tested.

[Dell documentation](https://dl.dell.com/manuals/common/n-series-v663_cli_en-us.pdf)
