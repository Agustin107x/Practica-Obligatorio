#  Obligatorio Taller de Servidores Linux ORT 2025, Febrero

This is a small project using **Ansible - Playbooks** that runs tasks on some machines.

## Requirements

- A primary server called **bastion** which will execute the playbooks.
- **Slaves** machines that will receive the tasks.
- Acces via **SSH** to slaves machines. 

## Dependencies

Its neccesary to install the module collection **Ansible Posix** to execute the playbooks correctly.    
Oficial documentation [here](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html).

And also is needed the module **community.general.ufw** for manage firewall with UFW  
Oficial documentation [here](https://docs.ansible.com/ansible/latest/collections/community/general/ufw_module.html).

## Installation

1. The **first step** is cloning the repository.

```bash
git clone https://github.com/Agustin107x/Practica-Obligatorio.git
cd Practica-Obligatorio
```

and then, **modify** the file inventory.ini (./inventory/inventory.ini) with the hostname and IPs of slaves.

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

2. And the **second** step is to verify in the playbook webserver.yml that the IP is the same as our centos machine

```ini
- name: Add domain name to hosts
ansible.builtin.lineinfile:
path: /etc/hosts
line: "192.168.2.10 www.ejemplo.com.uy" ##Here 
state: present
delegate_to: localhost
connection: local
```  

3. It is necessary to use ssh-copy-id in bastion with the sysadmin user and the ip of the slave machines
for example:  

```bash
ssh-copy-id sysadmin@192.168.2.10  
``` 

## Installation of dependencies
To install the necessary dependencies, execute:

```bash
ansible-galaxy install -r collections/requirements.yml
```

## Execute playbooks.

To run **web_setup.yml**:
```bash
ansible-playbook -i inventory/inventory.ini web_setup.yml --ask-become-pass
```

To run **hardening.yml**:
```bash
ansible-playbook -i inventory/inventory.ini hardening.yml --ask-become-pass
```

## Asumptions
- Git and Ansible is installed in bastion    
- SSH is installed and enabled in all machines.

## License

[MIT](https://choosealicense.com/licenses/mit/)
