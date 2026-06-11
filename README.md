# Devops_7193

Práctica para crear un contenedor PostgreSQL mediante Docker dentro de GitHub Codespaces.

## Componentes

- GitHub Codespaces como entorno de trabajo.
- Docker y Docker Compose.
- Contenedor `devops_postgres`.
- PostgreSQL 16.
- Base de datos `devops_db`.
- Usuario `devops_user`.
- Contraseña de práctica `devops_7193`.
- Tabla inicial `estudiantes`.

> Las credenciales son únicamente para esta práctica académica.

## Abrir Codespaces

1. En el repositorio, presione **Code**.
2. Abra la pestaña **Codespaces**.
3. Cree o abra el Codespace de la rama `main`.
4. Espere hasta que Visual Studio Code termine de cargar.

## Comprobar Docker Compose

Ejecute:

```bash
docker --version
docker compose version
```

Si aparece `docker: unknown command: docker compose`, instale el complemento:

```bash
sudo apt update
sudo apt install docker-compose-v2 -y
```

Luego repita `docker compose version`.

## Crear el contenedor con Docker

En la terminal ejecute:

```bash
docker compose up -d
```

Docker descargará PostgreSQL y creará el contenedor. Compruebe su estado con:

```bash
docker compose ps
docker ps
```

El contenedor `devops_postgres` debe aparecer con estado `healthy`.

## Consultar la base de datos

Ejecute la consulta desde el contenedor:

```bash
docker exec devops_postgres psql -U devops_user -d devops_db -c "SELECT * FROM estudiantes;"
```

Debe aparecer el registro `Estudiante Demo`.

Para abrir la consola interactiva de PostgreSQL:

```bash
docker exec -it devops_postgres psql -U devops_user -d devops_db
```

Para salir escriba `\q`.

## Administrar el contenedor

```bash
docker compose stop
docker compose start
docker compose down
```

## Archivos principales

- `.devcontainer/devcontainer.json`: configura Docker en Codespaces.
- `docker-compose.yml`: define el contenedor PostgreSQL.
- `database/init.sql`: crea la tabla y el registro inicial.

## Evidencias del proceso

1. Repositorio `Devops_7193` creado.
2. Opción para crear el Codespace.
3. Codespace abierto en Visual Studio Code.
4. Instalación y versión de Docker.
5. Instalación y versión de Docker Compose.
6. Ejecución de `docker compose up -d`.
7. Resultado de `docker ps` con `devops_postgres` activo.
8. Resultado de la consulta `SELECT * FROM estudiantes;`.

## Volver a abrir el entorno

Entre al repositorio, pulse **Code**, abra **Codespaces** y seleccione el Codespace existente. Después ejecute `docker compose up -d` para asegurar que PostgreSQL esté iniciado.
