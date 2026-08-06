# Configuración reproducible de WSL

Los playbooks de [`ansible/`](ansible/) son la fuente de verdad de estos ajustes. Los ajustes personales no automatizados están en [CONFIGURACION_MANUAL.md](CONFIGURACION_MANUAL.md).

## Requisitos de la distribución

- Ubuntu se ejecuta dentro de WSL.

## Ajustes aplicados

- APT actualiza los paquetes instalados antes de instalar el inventario definido en el playbook.
- `pyenv` se inicializa en Bash y `tfenv` se instala en `~/.tfenv`, con un enlace en `~/.local/bin`.
- Docker se habilita e inicia mediante `systemd`; el usuario que ejecuta Ansible se añade al grupo `docker`.
- OpenSSH se habilita e inicia mediante `systemd`. Solo permite al usuario que ejecuta Ansible autenticarse con las claves públicas de [`rsc/authorized_keys/`](rsc/authorized_keys/), y rechaza el acceso de `root`, las contraseñas y la autenticación interactiva.
