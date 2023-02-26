# Ejemplo de uso de Ansible con roles y ficheros de inventario 

## Fichero de inventario

- Los ficheros de inventario deben estar en el directorio ansible/inventory.
- Debe existir un fichero por entorno.

## Uso de roles de Ansible
Los playbooks de ansible (provision.yml, deploy.yml, etc.) hacen uso de distintos roles que están ubicados en el directorio "roles".
Estos roles siguen una estructura estándar, que está pensada para que sean reutilizables, por lo que podemos crear nuevos playbooks que hagan uso de estos roles.

Todos los comandos son y deben ser idempotentes, lo que significa que se puede lanzar tantas veces como sea necesario y el resultado final siempre será el mismo.

## Aprovisionar una máquina de forma inicial
Para aprovisionar una máquina recién creada se deberá lanzar el siguiente comando:

`ansible-playbook -i inventory/staging.yml provision.yml`


## Lanzar comandos específicos
Podemos usar tags para lanzar solamente ciertas tareas

`ansible-playbook -i inventory/staging.yml provision.yml --tags "install-composer"`
