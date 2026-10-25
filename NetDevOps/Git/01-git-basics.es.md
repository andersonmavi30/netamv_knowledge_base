---
tags: [git, version-control, netdevops]
validation: reference
---

# Git — Operación básica

[🇬🇧 English](01-git-basics.md) · [🇨🇴 Español](01-git-basics.es.md) · [↩ NetDevOps](../README.es.md)

## `git status --short`

```bash
git status --short
```

- **Sirve para:** Lista archivos modificados, nuevos y preparados.
- **Parámetros:** --short: estado resumido.
- **Ejemplo de uso:** Verificar cambios antes de preparar archivos.

## `git diff --check`

```bash
git diff --check
```

- **Sirve para:** Comprueba errores de espacios en cambios sin stage.
- **Parámetros:** --check: informa errores de espacios.
- **Ejemplo de uso:** Validar cambios de documentación antes de commit.

## `git diff -- README.md`

```bash
git diff -- README.md
```

- **Sirve para:** Muestra cambios sin stage de un archivo.
- **Parámetros:** --: separa ruta de opciones.
- **Ejemplo de uso:** Revisar README antes de publicar.

## `git log --oneline -5`

```bash
git log --oneline -5
```

- **Sirve para:** Muestra hashes y mensajes recientes.
- **Parámetros:** --oneline: formato corto; -5: cinco entradas.
- **Ejemplo de uso:** Localizar un cambio anterior.

## `git branch --show-current`

```bash
git branch --show-current
```

- **Sirve para:** Muestra rama activa.
- **Parámetros:** --show-current: solo el nombre.
- **Ejemplo de uso:** Evitar commits en rama equivocada.

## `git switch -c docs/aruba-cx`

```bash
git switch -c docs/aruba-cx
```

- **Sirve para:** Crea una rama y cambia a ella.
- **Parámetros:** -c: crea nueva rama.
- **Ejemplo de uso:** Separar cambios de documentación de main.

## `git add Networking/Aruba/`

```bash
git add Networking/Aruba/
```

- **Sirve para:** Prepara cambios de una carpeta.
- **Parámetros:** Ruta: limita los archivos preparados.
- **Ejemplo de uso:** Incluir solo documentación Aruba.

## `git commit -m "docs: add Aruba CX reference"`

```bash
git commit -m "docs: add Aruba CX reference"
```

- **Sirve para:** Crea commit de los cambios preparados.
- **Parámetros:** -m: mensaje del commit.
- **Ejemplo de uso:** Guardar actualización validada.

## `git push -u origin docs/aruba-cx`

```bash
git push -u origin docs/aruba-cx
```

- **Sirve para:** Publica rama y configura seguimiento.
- **Parámetros:** -u: configura seguimiento; origin: remoto.
- **Ejemplo de uso:** Crear pull request a partir de la rama.

## `git fetch --prune origin`

```bash
git fetch --prune origin
```

- **Sirve para:** Descarga referencias y elimina tracking obsoleto.
- **Parámetros:** --prune: limpia referencias remotas obsoletas.
- **Ejemplo de uso:** Revisar cambios remotos sin fusionarlos.

> Git usa opciones nativas; los pipes son opcionales y no deben agregarse por costumbre. Evita comandos destructivos sin comprobar el estado.

[Git reference](https://git-scm.com/docs)
