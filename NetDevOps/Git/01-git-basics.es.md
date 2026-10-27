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


## `git add README.md`

```bash
git add README.md
```

- **Sirve para:** Prepara cambios de un solo archivo.
- **Parámetros:** README.md: archivo concreto; usa `git add .` solo si todos los cambios son deseados.
- **Ejemplo de uso:** Preparar únicamente el documento revisado.

## `git checkout -b docs/docker`

```bash
git checkout -b docs/docker
```

- **Sirve para:** Crea una rama nueva y cambia a ella.
- **Parámetros:** -b: crea y selecciona la rama nueva.
- **Ejemplo de uso:** Editar Docker sin afectar directamente main.

## `git checkout main`

```bash
git checkout main
```

- **Sirve para:** Cambia a una rama local existente.
- **Parámetros:** main: rama destino; los cambios locales no deben generar conflictos.
- **Ejemplo de uso:** Volver a main antes de fusionar cambios.

## `git checkout -d HEAD~1`

```bash
git checkout -d HEAD~1
```

- **Sirve para:** Inspecciona el commit anterior en modo detached HEAD; no elimina ramas.
- **Parámetros:** -d / --detach: desacopla HEAD; HEAD~1: commit anterior.
- **Ejemplo de uso:** Revisar una revisión anterior y regresar con `git switch main`.
- **Precaución:** No trabajes permanentemente sin crear una rama.

## `git branch`

```bash
git branch
```

- **Sirve para:** Lista ramas locales e identifica la activa.
- **Parámetros:** Sin argumentos: enumera ramas locales.
- **Ejemplo de uso:** Comprobar que docs/docker existe.

## `git branch -d docs/docker`

```bash
git branch -d docs/docker
```

- **Sirve para:** Elimina una rama local ya fusionada.
- **Parámetros:** -d: eliminación segura; docs/docker: rama destino.
- **Ejemplo de uso:** Limpiar una rama luego de fusionarla.
- **Precaución:** Cambia de rama y confirma la fusión primero.

## `git merge --no-ff docs/docker`

```bash
git merge --no-ff docs/docker
```

- **Sirve para:** Fusiona la rama revisada con la rama actual.
- **Parámetros:** --no-ff: crea commit de merge; docs/docker: rama origen.
- **Ejemplo de uso:** Desde main, fusionar cambios aprobados de Docker.
- **Precaución:** Resuelve conflictos y valida antes de publicar.

## `git push`

```bash
git push
```

- **Sirve para:** Publica la rama actual en su remoto configurado.
- **Parámetros:** Sin opciones: requiere upstream o configuración de push.
- **Ejemplo de uso:** Publicar commits posteriores a `git push -u origin docs/docker`.

## `gh auth login --web`

```bash
gh auth login --web
```

- **Sirve para:** Inicia sesión en GitHub con GitHub CLI desde el navegador; Git no tiene comando `git login`.
- **Parámetros:** gh: GitHub CLI instalado aparte; --web: autenticación en navegador.
- **Ejemplo de uso:** Autenticarse en un equipo nuevo antes del primer push.
- **Precaución:** Selecciona integración Git HTTPS cuando pregunte; nunca publiques credenciales.

## `gh auth status`

```bash
gh auth status
```

- **Sirve para:** Comprueba qué cuenta de GitHub está autenticada.
- **Parámetros:** status: muestra estado de autenticación de GitHub CLI.
- **Ejemplo de uso:** Verificar que el login funcionó antes del push.

## `gh auth setup-git`

```bash
gh auth setup-git
```

- **Sirve para:** Configura Git para usar el gestor de credenciales de GitHub CLI.
- **Parámetros:** setup-git: registra gh como gestor de autenticación Git.
- **Ejemplo de uso:** Resolver solicitudes de credenciales HTTPS tras `gh auth login` si falta integración.
- **Precaución:** Úsalo solo en un equipo confiable; requiere GitHub CLI.

> **Git login:** no existe `git login`; usa `gh auth login --web` (GitHub CLI), SSH o un gestor de credenciales. `git checkout -d` desacopla HEAD; `git branch -d` elimina una rama local fusionada.

> Git usa opciones nativas; los pipes son opcionales y no deben agregarse por costumbre. Evita comandos destructivos sin comprobar el estado.

[Git reference](https://git-scm.com/docs)
