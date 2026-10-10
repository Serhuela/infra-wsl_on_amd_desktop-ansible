# Operación en WSL

Ejecuta estos comandos desde la raíz del repositorio, dentro de la distribución Ubuntu de WSL.

## Preparación

Instala Ansible y sus colecciones:

```bash
sudo apt update && sudo apt upgrade
sudo apt install ansible
ansible-galaxy collection install -r ansible/requirements.yml
```


## Ejecutar los playbooks

Ejecuta los playbooks en este orden:

```bash
ansible-playbook -i localhost, -c local ansible/configure-passwordless-sudo.yml -K
ansible-playbook -i localhost, -c local ansible/install-apt-packages.yml
ansible-playbook -i localhost, -c local ansible/install-snap-packages.yml
ansible-playbook -i localhost, -c local ansible/configure-development-tools.yml
ansible-playbook -i localhost, -c local ansible/configure-docker.yml
ansible-playbook -i localhost, -c local ansible/configure-ssh.yml
```

La primera ejecución de `configure-passwordless-sudo.yml` solicita la contraseña actual para crear la regla. Después, `sudo` y los playbooks con privilegios no vuelven a solicitarla.

Antes de ejecutar `configure-ssh.yml`, añade al menos una clave pública con extensión `.pub` a `rsc/authorized_keys/`. El playbook permite SSH solo al usuario que lo ejecuta y solo con esas claves.

Abre una sesión nueva de WSL después de ejecutar `configure-docker.yml` para que el grupo `docker` se aplique al usuario.
