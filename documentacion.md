#  Obligatorio Taller de Servidores Linux, Febrero 2025

## Profesor

- Enrique Verdes

## Alumno

- Agustin Neves (321438)

***
## Tarea 1 - Verificación de conexión exitosa con el módulo ping de Ansible.  
**Ejecución del comando**  
```bash
ansible all -i inventory/inventory.ini -m ping  
```  
**Salida del comando**  
![Salida T1E1](/results/Tarea1/prueba%20comando%20ping%20en%20máquinas%20ansible.png)

# &nbsp;

## Tarea 2 - Ejecución de comandos AD-HOC

### 2.1. Verificar tiempo de actividad en los servidores:

**Ejecución del comando**  
```bash
ansible -i inventory/inventory.ini all -m shell -a "uptime"
```
**Salida del comando**  
![Salida T2E1](/results/Tarea2/Salida%20tarea%202%20ejercicio%201.png)

## &nbsp;

### 2.2. Instalar apache en servidores WEB.

**Ejecución del comando**
```bash
ansible -i inventory/inventory.ini centos -m yum -a "name=httpd state=present" --become --ask-become-pass
```
**Salida del comando**  
![Salida T2E1](/results/Tarea2/salida%20tarea%202%20ejercicio%202.png)

## &nbsp;

### 2.3. Verificar uso de espacio en disco de los servidores ubuntu

**Ejecución del comando**
```bash
ansible -i inventory/inventory.ini ubuntu -m shell -a "df -h"
```
**Salida del comando**  
![Salida T2E1](/results/Tarea2/salida_T2E3.png)

# &nbsp;

## Tarea 3 - Ejecución de playbooks (hardening.yml) y (webserver.yml)

**Ejecución del playbook webserver.yml**

```bash
ansible-playbook -i inventory/inventory.ini webserver.yml --ask-become-pass
```

**Salida del comando**  
![Salida T3E1](/results/Tarea3/results%20playbook%20websever.yml.JPG)

## &nbsp;

**Ejecución del playbook hardening.yml**

```bash
ansible-playbook -i inventory/inventory.ini hardening.yml --ask-become-pass
```

**Salida del comando**  
![Salida T3E1](/results/Tarea3/results%20playbook%20hardening.yml.JPG)









