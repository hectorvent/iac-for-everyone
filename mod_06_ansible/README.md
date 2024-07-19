# Ansible, administrar y configurar 

0- Ejecutar docker imagen donde tenemos ansible instalado
```
docker run --rm -it -v $PWD:/iac -w /iac hectorvent/iac-for-everyone bash
```

1- Ansible ad hoc 
```shell
## comando ad hoc simple
ansible localhost -a "pwd"
```

```shell
# Ejecutando un modulo en especifico
 ansible localhost -m setup
```

```shell
# Ejecutando un modulo en especifico
ansible localhost -m setup -a "filter=ansible_selinux"
```

2- Ansible playbook

Un playbook no es mas que un documento yaml, este agrupa todas la tareas. Esto tiene muchas ventajas, como: Versionar, no agrupar comandos o tareas, etc. 

Veremos:
* Playbooks en código
* Variables
* Plantillas
* Modulos
* Roles
* Handlers



