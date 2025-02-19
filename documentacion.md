#  Obligatorio Taller de Servidores Linux, Febrero 2025

## Profesor

- Enrique Verdes

## Alumnos

- Agustin Neves (321438)
- Lucas Gonzalez (231346)

***

1. Verificar tiempo de actividad en lo servidores:

ansible -i inventory/inventory.ini all -m shell -a "uptime"

2. Instalar apache en servidores WEB.

ansible -i inventory/inventory.ini centos -m yum -a "name=httpd state=present" --become --ask-become-pass

3. Verificar uso de epsacio en disco de los servidores ubuntu

ansible -i inventory/inventory.ini all -m shell -a "df -h"

