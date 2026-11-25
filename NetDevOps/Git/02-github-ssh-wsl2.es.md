---
tags: [git, github, ssh, wsl2, netdevops]
validation: reference
---

# Autenticación SSH de GitHub desde WSL2 — paso a paso

[🇬🇧 English](02-github-ssh-wsl2.md) · [🇨🇴 Español](02-github-ssh-wsl2.es.md) · [↩ Git](README.es.md)

**Plataforma:** Ubuntu u otra distribución Linux en WSL2, Bash, OpenSSH y Git. Estos pasos configuran Linux dentro de WSL2, no OpenSSH de Windows. Usa tu usuario normal de WSL, no root, y una frase de contraseña para la llave privada.

## 1. Revisar herramientas y llaves existentes

```bash
git --version
ssh -V
ls -la ~/.ssh
```

- **Sirve para:** Confirmar Git/OpenSSH y verificar si ya hay llaves SSH.
- **Parámetros:** `--version`: versión de Git; `-V`: versión de SSH (V mayúscula); `ls -la`: listado detallado con archivos ocultos; `~/.ssh`: carpeta SSH del usuario Linux.
- **Ejemplo de uso:** Evitar sobrescribir una llave existente. Si la carpeta no existe, es normal al configurar SSH por primera vez.

## 2. Generar una llave Ed25519 dedicada (solo si hace falta)

```bash
mkdir -p ~/.ssh
chmod 700 ~/.ssh
ssh-keygen -t ed25519 -C "tu-correo@example.com" -f ~/.ssh/id_ed25519_github
```

- **Sirve para:** Crear un par de llaves SSH específico para GitHub desde WSL2.
- **Parámetros:** `mkdir -p`: crear carpeta si falta; `chmod 700`: acceso exclusivo del propietario; `-t ed25519`: algoritmo; `-C`: comentario identificador (reemplazar el correo); `-f`: ruta de las llaves.
- **Ejemplo de uso:** Tener una identidad SSH propia para hacer `git push` desde Ubuntu WSL2. Define una frase de contraseña segura. **Si el archivo ya existe, no lo sobrescribas: reutiliza la llave o escoge otro nombre.**
- **Seguridad:** `id_ed25519_github` es la llave **privada**; `id_ed25519_github.pub` es la **pública**. Nunca subas, copies en chats ni publiques la privada.

## 3. Cargar la llave en ssh-agent de WSL2

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519_github
ssh-add -l
```

- **Sirve para:** Iniciar el agente SSH, cargar la llave y listar sus identidades.
- **Parámetros:** `ssh-agent -s`: imprime configuración del agente; `eval`: aplica la configuración al shell actual; `ssh-add`: carga la llave; `-l`: muestra huellas de llaves cargadas.
- **Ejemplo de uso:** Autenticarse sin reintroducir la frase de contraseña en cada operación Git. Puede ser necesario volver a cargarla en otra sesión WSL.

## 4. Registrar únicamente la llave pública en GitHub

```bash
cat ~/.ssh/id_ed25519_github.pub
```

- **Sirve para:** Mostrar la llave pública (normalmente comienza por `ssh-ed25519`).
- **Parámetros:** `cat`: muestra el contenido; `.pub`: identifica la llave pública, **no** la privada.
- **Ejemplo de uso:** Copiar toda la línea pública y entrar a **GitHub → Settings → SSH and GPG keys → New SSH key**. Seleccionar **Authentication Key**, asignar un nombre como `WSL2-Ubuntu` y guardar.
- **Referencia oficial:** https://docs.github.com/es/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

## 5. Asociar la llave a github.com (recomendado si es dedicada)

Crear o editar `~/.ssh/config` (por ejemplo, con `vim ~/.ssh/config`) y agregar:

```sshconfig
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_github
    IdentitiesOnly yes
```

Proteger el archivo:

```bash
chmod 600 ~/.ssh/config
chmod 600 ~/.ssh/id_ed25519_github
```

- **Sirve para:** Elegir la llave SSH al conectar con GitHub desde WSL2.
- **Parámetros:** `IdentityFile`: ruta de llave privada; `IdentitiesOnly yes`: restringe identidades ofrecidas; `chmod 600`: lectura/escritura solo del propietario.
- **Precaución:** Si ya existe un bloque `Host github.com`, editarlo en vez de duplicarlo con opciones contradictorias. Si ya funciona otra llave, no necesitas crear una nueva.

## 6. Probar la autenticación SSH

```bash
ssh -T git@github.com
```

- **Sirve para:** Comprobar que GitHub reconoce la llave.
- **Parámetros:** `-T`: no asigna terminal interactiva; `git@github.com`: usuario y servidor SSH de GitHub.
- **Ejemplo de uso:** Una respuesta exitosa reconoce tu usuario y explica que GitHub no ofrece shell interactivo; el código de salida **1** puede ser normal en esta prueba.
- **Seguridad:** En la primera conexión, **comprueba la huella SSH publicada oficialmente por GitHub** antes de aceptar la llave del servidor; no aceptes huellas desconocidas.
- **Referencias oficiales:** https://docs.github.com/es/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection y https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints

## 7. Configurar el remoto SSH en el repositorio local

Ejecutar dentro de la carpeta **local del simulador RHCSA**:

```bash
git remote -v
git remote set-url rhcsa_simulator git@github.com:andersonmavi30/rhcsa_simulator.git
git remote -v
git ls-remote rhcsa_simulator HEAD
```

- **Sirve para:** Revisar remotos, actualizar la URL SSH de `rhcsa_simulator` y confirmar acceso de lectura.
- **Parámetros:** `remote -v`: URLs de fetch/push; `remote set-url`: cambiar URL de remoto existente; `rhcsa_simulator`: nombre local del remoto; `ls-remote … HEAD`: consultar la referencia HEAD remota sin clonar ni modificarla.
- **Ejemplo de uso:** Verificar acceso al repositorio RHCSA Simulator con la nueva autenticación SSH de WSL2.
- **Importante:** Si `git remote -v` muestra solamente `origin`, reemplaza `rhcsa_simulator` por `origin` en ambos comandos. El nombre del repositorio no es necesariamente el remoto. Si no existe remoto, usa `git remote add origin git@github.com:andersonmavi30/rhcsa_simulator.git`.
- **Referencia oficial:** https://git-scm.com/docs/git-remote

## Solución rápida de problemas

- **Permission denied (publickey):** verificar `ssh-add -l`, que esté registrada la llave **.pub**, y `~/.ssh/config`; ejecutar `ssh -vT git@github.com` (`-v`: diagnóstico detallado).
- **No such remote:** revisar el nombre real con `git remote -v`.
- **Host key verification failed:** comprobar la huella publicada por GitHub y el archivo `~/.ssh/known_hosts`; no desactivar la verificación.
- **Funciona en Windows pero falla en WSL2:** WSL2 tiene su propia carpeta Linux `~/.ssh` y agente SSH, salvo que se configure su uso compartido.

> Guía de referencia; no se ejecutó en el WSL2 del usuario. Nunca publiques llaves privadas, tokens ni secretos personales en Git.
