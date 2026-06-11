# Devops_7193

Práctica de creación y administración de un contenedor Nginx con Docker dentro de GitHub Codespaces.

## Paso 1: Verificar Docker

```bash
docker --version
```

> El comando correcto utiliza `--version`, sin tilde.

## Paso 2: Instalar Docker si no existe

Ejecute estos comandos solamente si el paso anterior indica que Docker no está instalado:

```bash
sudo apt update
sudo apt install docker.io -y
```

## Paso 3: Crear el contenedor

```bash
docker run -d --name servidor-nginx nginx
```

Docker descargará la imagen de Nginx y mostrará el identificador del contenedor.

## Paso 4: Verificar el contenedor activo

```bash
docker ps
```

Debe aparecer el contenedor `servidor-nginx` con estado `Up`.

## Paso 5: Ingresar al contenedor

```bash
docker exec -it servidor-nginx bash
```

También se puede reemplazar `servidor-nginx` por el ID mostrado en `docker ps`.

## Paso 6: Verificar el servicio Nginx

Estos comandos se ejecutan dentro del contenedor:

```bash
apt update
apt install curl -y
curl localhost
```

El resultado de `curl localhost` debe mostrar el código HTML de la página **Welcome to nginx!**.

## Paso 7: Salir y detener el contenedor

```bash
exit
docker stop servidor-nginx
```

Compruebe que se detuvo:

```bash
docker ps
```

## Volver a iniciar el contenedor

```bash
docker start servidor-nginx
```

## Evidencias requeridas

1. Repositorio `Devops_7193` creado en GitHub.
2. Codespace abierto en Visual Studio Code.
3. Resultado de `docker --version`.
4. Resultado de `docker run -d --name servidor-nginx nginx`.
5. Resultado de `docker ps` con el contenedor activo.
6. Terminal dentro del contenedor después de `docker exec`.
7. Resultado de `curl localhost` mostrando la página de Nginx.
8. Resultado de `docker stop servidor-nginx`.

## Observación

Si aparece un error relacionado con `/var/run/docker.sock` o indica que el daemon no está funcionando, el entorno actual no tiene activo el servicio Docker. En ese caso se debe crear un Codespace nuevo desde la rama `main` antes de continuar.
