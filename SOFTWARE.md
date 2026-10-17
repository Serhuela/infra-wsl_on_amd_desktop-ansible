# Software gestionado en WSL

Inventario del software instalado o configurado por los playbooks de este repositorio. Las versiones de los paquetes APT las determina la distribución Ubuntu configurada en WSL.

## Paquetes APT

| Finalidad | Paquetes |
| --- | --- |
| Automatización y utilidades | `ansible`, `awscli`, `curl`, `git`, `gh`, `jq`, `make`, `ripgrep`, `zip` |
| Gestión de paquetes Snap | `snapd` |
| Contenedores | `docker.io`, `docker-buildx`, `docker-compose-v2` |
| Java y Groovy | `openjdk-21-jdk`, `groovy` |
| Node.js y gestión de paquetes JavaScript | `nodejs`, `npm` |
| Acceso remoto | `openssh-server` |
| Python y compilación | `pyenv`, `build-essential`, `libssl-dev`, `zlib1g-dev`, `libbz2-dev`, `libreadline-dev`, `libsqlite3-dev`, `libncurses-dev`, `xz-utils`, `tk-dev`, `libxml2-dev`, `libxmlsec1-dev`, `libffi-dev`, `liblzma-dev`, `libzstd-dev` |

## Paquetes Snap

| Herramienta | Paquete | Canal |
| --- | --- | --- |
| [CLI de Bitwarden](https://bitwarden.com/help/cli/) | `bw` | `latest/stable` |

Snap gestiona las actualizaciones.

## Herramientas configuradas desde sus repositorios oficiales

| Herramienta | Ubicación | Gestión |
| --- | --- | --- |
| tfenv | `~/.tfenv` y `~/.local/bin/tfenv` | Clonada y actualizada desde `tfutils/tfenv`, rama `master`; sus binarios se añaden al `PATH` de Bash |

`pyenv` se inicializa en `~/.bashrc`. La lista completa y fuente de verdad de los paquetes APT es `ansible/install-apt-packages.yml`.
