#  Proyecto Ansible ORT 2025

Este es un pequeño proyecto de **Ansible** que ejecuta playbooks en distintos equipos.

## Requisitos

- Un equipo principal que actúe como **bastión**.
- Equipos **Slaves** que recibirán las tareas.
- Acceso **SSH** a los equipos de destino.

## Dependencias

Es necesario instalar la colección de módulos **Ansible Posix** para ejecutar los playbooks correctamente.  
Aquì se encuentra el [sitio oficial](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html).

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
