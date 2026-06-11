# Devops_7193

Proyecto de práctica para crear y abrir un contenedor de desarrollo en GitHub Codespaces con una base de datos PostgreSQL.

## Componentes

- Contenedor de desarrollo basado en Ubuntu.
- Base de datos PostgreSQL 16.
- Base de datos: `devops_db`.
- Usuario: `devops_user`.
- Contraseña de práctica: `devops_7193`.
- Tabla inicial: `estudiantes`.

> Las credenciales incluidas son únicamente para esta práctica académica.

## Abrir el contenedor en Codespaces

1. En la página principal del repositorio, presione el botón verde **Code**.
2. Seleccione la pestaña **Codespaces**.
3. Presione **Create codespace on main**.
4. Espere mientras GitHub prepara el entorno y levanta los contenedores.
5. Cuando aparezca Visual Studio Code en el navegador, espere a que termine la configuración inicial.

## Verificar la base de datos

Primero compruebe que PostgreSQL acepta conexiones:

```bash
pg_isready -h database -p 5432 -U devops_user -d devops_db
```

El resultado esperado es `database:5432 - accepting connections`.

Después conéctese a la base de datos:

```bash
psql -h database -U devops_user -d devops_db
```

Cuando solicite la contraseña, escriba:

```text
devops_7193
```

Dentro de PostgreSQL, ejecute:

```sql
SELECT * FROM estudiantes;
```

Debe aparecer el registro `Estudiante Demo`. Para salir escriba:

```text
\q
```

## Archivos principales

- `.devcontainer/devcontainer.json`: configuración utilizada por Codespaces.
- `docker-compose.yml`: definición del entorno y PostgreSQL.
- `database/init.sql`: creación de la tabla y datos iniciales.

## Evidencias del proceso

Capture las siguientes pantallas para el informe:

1. Repositorio `Devops_7193` creado en GitHub.
2. Pestaña **Codespaces** con la opción **Create codespace on main**.
3. Pantalla de creación y carga del Codespace.
4. Codespace abierto en Visual Studio Code desde el navegador.
5. Resultado de `pg_isready` indicando que PostgreSQL acepta conexiones.
6. Resultado de `SELECT * FROM estudiantes;` mostrando el registro almacenado.
7. Estructura final de archivos del repositorio.

## Volver a abrir el contenedor

Ingrese al repositorio, pulse **Code**, abra **Codespaces** y seleccione el Codespace existente. No es necesario crear uno nuevo cada vez.
