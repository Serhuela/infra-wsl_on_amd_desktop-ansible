# Playbooks de Ansible

Los playbooks se ejecutan contra la propia distribución Ubuntu de WSL, con `localhost` y conexión local.

| Archivo | Responsabilidad | Requisitos |
| --- | --- | --- |
| [`install-apt-packages.yml`](install-apt-packages.yml) | Actualiza APT e instala el inventario de paquetes. | Privilegios de `sudo` |
| [`configure-development-tools.yml`](configure-development-tools.yml) | Instala o actualiza `tfenv` e inicializa `pyenv` en Bash. | `git` y `pyenv` instalados |
| [`configure-docker.yml`](configure-docker.yml) | Habilita Docker y añade al usuario actual al grupo `docker`. | Docker instalado y `systemd` activo |
| [`configure-ssh.yml`](configure-ssh.yml) | Autoriza las claves versionadas y restringe OpenSSH a autenticación por clave pública. | OpenSSH instalado, `systemd` activo y al menos una clave `.pub` en [`../rsc/authorized_keys/`](../rsc/authorized_keys/) |
| [`requirements.yml`](requirements.yml) | Declara `ansible.posix`, necesaria para gestionar las claves SSH. | Instalar con `ansible-galaxy` |

El orden de ejecución y los comandos están en [../ops/README.md](../ops/README.md).
