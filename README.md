#  Obligatorio Taller de Servidores Linux ORT 2025, Febrero

This is a small project using **Ansible - Playbooks** that runs tasks on some machines.

## Requirements

- A primary server called **bastión** which will execute the playbooks.
- Slaves machines that will receive the tasks.
- Acces via SSH to slaves machines. 

## Dependencies

Its neccesary to install the module collection **Ansible Posix** to execute the playbooks correctly.    
Oficial documentation [here](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html).

## Instalación

Clonamos el repositorio:

```bash
git clone https://github.com/Agustin107x/Practica-Obligatorio.git
cd Practica-Obligatorio
```
Luego, modificamos el archivo inventory.ini (./inventory/inventory.ini) con los hostnames e IPs de nuestros equipos Slaves:

```ini
[centos]
centos-srv ansible_host=192.168.2.10  # Reemplazar con la IP y Hostname real

[ubuntu]
ubuntu-srv ansible_host=192.168.2.30  # Reemplazar con la IP y Hostname real

[linux:children]
centos
ubuntu

[linux:vars]
ansible_user=sysadmin  # Cambiar si se usa otro usuario

[webserver]
centos-srv  # Reemplazar si es necesario.
```

## Instalación de dependencias
Para instalar las dependencias necesarias, ejecutar:

```bash
ansible-galaxy install -r collections/requirements.yml
```

## Ejecución de playbooks.

## License

[MIT](https://choosealicense.com/licenses/mit/)
