#  Obligatorio Taller de Servidores Linux, Febrero 2025

## Profesor

- Enrique Verdes

## Alumnos

- Agustin Neves (321438)
- Lucas Gonzalez (231346)

***

## Tarea 2 - Ejecución de comandos AD-HOC

### 1. Verificar tiempo de actividad en los servidores:

**Ejecución del comando**
```bash
ansible -i inventory/inventory.ini all -m shell -a "uptime"
```
**Salida del comando**
![Salida T2E1](/images/Tarea2/Salida%20tarea%202%20ejercicio%201.png)

### 2. Instalar apache en servidores WEB.

**Ejecución del comando**
```bash
ansible -i inventory/inventory.ini centos -m yum -a "name=httpd state=present" --become --ask-become-pass
```
**Salida del comando**
![Salida T2E1](/images/Tarea2/salida%20tarea%202%20ejercicio%202.png)


### 3. Verificar uso de epsacio en disco de los servidores ubuntu

**Ejecución del comando**
```bash
ansible -i inventory/inventory.ini all -m shell -a "df -h"
```
**Salida del comando**
![Salida T2E1](/images/Tarea2/salida%20tarea%202%20ejercicio%203.png)

## Fin



