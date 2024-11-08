
# Configuración de Contenedores para Odoo 17 y PostgreSQL

Este repositorio contiene la configuración para levantar contenedores de **Odoo 17** y **PostgreSQL** usando Docker. Sigue las instrucciones a continuación para configurar el entorno y ejecutar los contenedores.

## Requisitos

Para ejecutar los contenedores, asegúrate de tener instalados los siguientes programas:

1. **Docker**: Herramienta para ejecutar contenedores. Descárgala e instálala desde [Docker](https://www.docker.com/get-started).
2. **Docker Compose**: Herramienta para definir y ejecutar aplicaciones multicontenedor. En la mayoría de instalaciones modernas, Docker Compose viene incluido con Docker Desktop, pero también se puede instalar por separado si usas Docker en Linux.

### Instalación de Docker y Docker Compose

#### En Windows o macOS
1. Descarga **Docker Desktop** desde la página oficial de Docker: [Docker Desktop](https://www.docker.com/products/docker-desktop).
2. Sigue las instrucciones de instalación en la página de Docker. Asegúrate de habilitar **Docker Compose** durante la instalación.

#### En Linux
1. Ejecuta los siguientes comandos en la terminal para instalar Docker:
   ```bash
   sudo apt update
   sudo apt install docker.io -y
   docker --version
   ```
2. Instala Docker Compose:
   ```bash
   sudo apt install docker-compose -y
   docker-compose --version
   ```
3. Asegúrate de que el servicio Docker esté activo:
   ```bash
   sudo systemctl start docker
   sudo systemctl enable docker
   sudo systemctl status docker
   ```

## Uso

### 1. Clona el Repositorio
Clona este repositorio en tu máquina local e ingresa a la carpeta del proyecto:

```bash
git clone https://github.com/vjmoreno/odoo-17-docker
cd odoo-17-docker
```

### 2. Levanta los Contenedores

Para iniciar los contenedores de Odoo y PostgreSQL, ejecuta:

```bash
./run.sh
```

Esto iniciará los contenedores en segundo plano.

### 3. Acceso a Odoo

Una vez que los contenedores estén levantados, puedes acceder a Odoo desde tu navegador web en la siguiente dirección:

```plaintext
http://localhost:8069
```
### 4. Dar de baja los contenedores

```bash
docker-compose down
```
Esto eliminará los contenedores de Odoo y PostgreSQL, pero conservará la base de datos, configuraciones de Odoo, módulos y logs.

## Solución de Problemas Comunes

1. **Permisos de Docker en Linux**: Si recibes un error de permisos al ejecutar Docker, intenta agregar tu usuario al grupo `docker`:

   ```bash
   sudo usermod -aG docker $USER
   ```

   Luego cierra sesión y vuelve a iniciar sesión para que los cambios surtan efecto.

2. **Problemas con el puerto 8069**: Si el puerto 8069 está en uso, puedes cambiarlo en el archivo `docker-compose.yml`.
