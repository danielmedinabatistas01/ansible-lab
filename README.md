# Práctica Ansible - Automatización de servidores Ubuntu

## 1. Objetivo de la práctica

El objetivo de esta práctica es aprender a utilizar Ansible para automatizar tareas en varios servidores Ubuntu mediante contenedores Docker.

Se crearon dos servidores Ubuntu 24.04 utilizando Docker Compose y se configuró Ansible para administrarlos directamente mediante la conexión Docker.

El playbook permite obtener información de los servidores, crear directorios y archivos, utilizar ciclos (`loop`) y ejecutar condiciones (`when`).

## 2. Tecnologías utilizadas

- Docker Desktop
- Docker Compose
- Ubuntu 24.04
- WSL2
- Ansible
- Colección community.docker

## 3. Estructura del proyecto

```text
ansible-lab/
├── docker-compose.yml
├── inventory.ini
├── playbook.yml
└── README.md
```

## 4. Comandos para iniciar los contenedores

Desde la terminal, ubicarse dentro de la carpeta del proyecto y ejecutar:

```bash
docker compose up -d
```

Para comprobar que los contenedores estén ejecutándose:

```bash
docker ps
```

## 5. Configuración de Ansible

Para comprobar la conexión con los dos servidores:

```bash
ansible docker -i inventory.ini -m ping
```

Ambos servidores deben responder correctamente con `pong`.

## 6. Ejecución del Playbook

Para ejecutar las tareas automatizadas:

```bash
ansible-playbook -i inventory.ini playbook.yml
```

El playbook realiza las siguientes tareas:

1. Mostrar el nombre del servidor.
2. Mostrar el sistema operativo.
3. Crear el directorio `/tmp/ansible-demo`.
4. Crear el archivo `info.txt` con información del servidor.
5. Crear los directorios `logs`, `backup` y `config` mediante un loop.
6. Mostrar un mensaje únicamente cuando el sistema operativo sea Ubuntu.

## 7. Resultados obtenidos

La ejecución se completó correctamente en los dos servidores Ubuntu.

- server1: `failed=0`
- server2: `failed=0`

Se verificó la creación del directorio principal, el archivo `info.txt` y los tres directorios solicitados.

## 8. Evidencia de ejecución

A continuación se incluye la captura de pantalla de la ejecución exitosa del playbook.

**[Insertar aquí la captura de pantalla de Ansible]**

## 9. Conclusión

Mediante esta práctica se aprendió a utilizar Ansible para automatizar tareas en varios servidores Ubuntu utilizando Docker como entorno de ejecución.

También se practicó el uso de inventarios, playbooks, ciclos y condiciones para administrar los servidores de manera centralizada.

<img width="872" height="319" alt="image(20261117-055936)" src="https://github.com/user-attachments/assets/65ca165c-c0b3-45c6-a4e0-f252b29a8585" />
