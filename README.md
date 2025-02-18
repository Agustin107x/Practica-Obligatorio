# Finalidad

Este es un documento de practica para el obligatorio del Taller de Servidores Linux, Facultad ORT 2025

## Tarea 2

2.1 Verifica el tiempo de actividad (uptime) en todos los servidores. 
```bash
ansible -i inventory/inventory.ini all -m shell -a "uptime"
```
2.2 Instala apache en los servidores web. 
```bash
test
```
2.3 Recupera el uso de espacio en disco de los servidores ubuntu. 
```bash
ansible -i inventory/inventory.ini all -m shell -a "df -f"
```

## Usage

```
Test
```

## Test

Texto de ejemplo
