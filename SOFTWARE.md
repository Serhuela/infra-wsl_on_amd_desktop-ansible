# Software gestionado en WSL

Inventario del software instalado o configurado por los playbooks de este repositorio. Las versiones las determina la distribución Ubuntu configurada en WSL.

## Paquetes APT

| Finalidad | Paquetes |
| --- | --- |
| Automatización y utilidades | `ansible`, `curl`, `git`, `gh`, `make`, `zip` |
| Contenedores | `docker.io`, `docker-buildx`, `docker-compose-v2` |
| Acceso remoto | `openssh-server` |
| Python y compilación | `pyenv`, `build-essential`, `libssl-dev`, `zlib1g-dev`, `libbz2-dev`, `libreadline-dev`, `libsqlite3-dev`, `libncurses-dev`, `xz-utils`, `tk-dev`, `libxml2-dev`, `libxmlsec1-dev`, `libffi-dev`, `liblzma-dev`, `libzstd-dev` |

## Herramientas configuradas desde sus repositorios oficiales

| Herramienta | Ubicación | Gestión |
| --- | --- | --- |
| tfenv | `~/.tfenv` y `~/.local/bin/tfenv` | Clonada y actualizada desde `tfutils/tfenv`, rama `master`; sus binarios se añaden al `PATH` de Bash |

`pyenv` se inicializa en `~/.bashrc`. La lista completa y fuente de verdad de los paquetes APT es `ansible/install-apt-packages.yml`.
