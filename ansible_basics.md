## 1. ¿Qué es Ansible y por qué es "sin agente" (agentless)? 

Ansible es un motor open source que sirve para automatizar tareas y procesos informaticos en equipos e infraestructuras distribuidas.
Es del modelo agent-less, es decir que no requiere que se instale ningun software ni programa en las máquinas
que vamos a empezar a controlar, facilitando las configuraciones. Este usa SSH para conectarse a las máquinas.

## &nbsp;

## 2. Explica la diferencia entre un comando ad-hoc y un playbook. 

Un comando **ad-hoc** sirve para ejecutar una tarea sencilla o unica, sin necesidad de tener que escribir un playbook.
Estos se utilizan cuando se quiera ejecutar algo puntual y sin guardar la configuración.  

A su vez, un **playbook** es un archivo yaml que contiene una serie de tareas, pasos y/o configuraciones de manera organizada.
Estos se usan normalmente cuando es una tarea repetitiva o que se va a ejecutar varias veces.

## &nbsp;

## 3. ¿Qué es la idempotencia y por qué es importante en Ansible? 

Ansible nos va a llevar los equipos hasta el estado que le solicitemos, y en caso de que ya esté en este estado
No realizará ninguna tarea, ni hará ni un cambio. Esto es la idempotencia.

## &nbsp;

## 4. ¿Cómo funcionan los handlers y cuándo deberías usarlos? 

Los handlers son tareas especiales que se ejecutan cuando son llamados por otras tareas (notify: nombre).
Normalmente se ejecutan si pasa algo en la tarea, o si es algun cambio que requiera hacer otra cosa, como reiniciar o actualizar.
Se ejecutan al final de los playbooks, cuando se completan todas las tareas.
 
## 5. ¿Cómo verificas errores de sintaxis en un playbook de Ansible? 

Ansible de forma nativa tiene el comando **--syntax-check** que nos dirá si encuentra algun error de sintaxis en nuestro playbook.
Se usaría así:

```bash
ansible-playbook -i (inventario) (playbook.yml) --syntax-check
```  
## &nbsp;

***

# Referencias
-La chica de Sistemas, (2024) ANSIBLE: LA REINA DE LA AUTOMATIZACIÓN
[Link](https://www.youtube.com/watch?v=yB7oWJbMd3A)

Lanpixel, (29 de diciembre de 2022) [GUÍA] Automatizando nuestra red con Ansible y Mikrotik v7
[Link](https://lanpixel.com/blog/guia-automatizando-nuestra-red-con-ansible-y-mikrotik-v7/#Idempotencia_en_Ansible)

***

## Desafios encontrados





