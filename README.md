# Automatización de software para WSL

Este repositorio configura software de desarrollo en una distribución Ubuntu ya instalada en WSL. No instala ni configura un sistema Linux de escritorio completo.

## Inicio rápido

1. Instala Ubuntu en WSL y clona este repositorio dentro de la distribución.
2. Sigue el procedimiento de [ops/README.md](ops/README.md).

## Alcance

Los playbooks instalan paquetes APT y Snap, configuran `pyenv` y `tfenv`, habilitan Docker y preparan OpenSSH con claves públicas versionadas. El inventario está en [SOFTWARE.md](SOFTWARE.md) y los ajustes reproducibles en [CONFIGURACION.md](CONFIGURACION.md).

Los ajustes personales que no gestiona Ansible se documentan en [CONFIGURACION_MANUAL.md](CONFIGURACION_MANUAL.md).
