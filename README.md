#  Obligatorio Taller de Servidores Linux ORT 2025, Febrero

This is a small project using **Ansible - Playbooks** that runs tasks on some machines.

## Requirements

- A primary server called **bastión** which will execute the playbooks.
- Slaves machines that will receive the tasks.
- Acces via SSH to slaves machines. 

## Dependencies

Its neccesary to install the module collection **Ansible Posix** to execute the playbooks correctly.    
Oficial documentation [here](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html).

## Installation

The first step is cloning the repository.

```bash
git clone https://github.com/Agustin107x/Practica-Obligatorio.git
cd Practica-Obligatorio
```

and then, modify the file inventory.ini (./inventory/inventory.ini) with the hostname and IPs of slaves.

```ini
[centos]
centos-srv ansible_host=192.168.2.10  # Replace with real IP and Hostname 

[ubuntu]
ubuntu-srv ansible_host=192.168.2.30  # Replace with real IP and Hostname 
[linux:children]
centos
ubuntu

[linux:vars]
ansible_user=sysadmin  # Change if you want to use other user.

[webserver]
centos-srv  # Replace if neccesary
```

## Installation of dependencies
To install the necessary dependencies, execute:

```bash
ansible-galaxy install -r collections/requirements.yml
```

## Ejecución de playbooks.

## License

[MIT](https://choosealicense.com/licenses/mit/)
