# Proyecto Asociación Yambo

Este proyecto es una aplicación web para la **Asociación Yambo**, que incluye una sección pública y una intranet para la gestión de facturas, monitores y documentos. La aplicación utiliza **React** para el frontend y **Spring Boot** en el backend, con **autenticación mediante JWT**. Se despliega en contenedores Docker, pero también puede ejecutarse localmente sin Docker.

## Requisitos

*   Docker
*   Docker Compose
*   JDK 17 o superior (si no se usa Docker para el backend)
*   Node.js y NPM (si no se usa Docker para el frontend)
*   MariaDB (opcional, solo si se ejecuta sin Docker)

## Configuración de Variables de Entorno (sin Docker)

Para ejecutar el proyecto sin Docker, asegúrate de tener configuradas las siguientes variables de entorno tanto para el backend como para la base de datos.

1.  **Base de datos MySQL**: Crea una base de datos MySQL local e ingresa la configuración en el backend.
    
2.  **Variables de entorno para el backend**: Crea un archivo `.env` en la carpeta del backend (`/backend/app`) con el siguiente contenido:
    
```
SPRING_DATASOURCE_URL=jdbc:mariadb://localhost:3306/yambo_db
SPRING_DATASOURCE_USERNAME=db_user
SPRING_DATASOURCE_PASSWORD=db_password
JWT_SECRET=mysecretkey

# Configuración de directorios de subida de archivos
FILE_UPLOAD_DIR=/ruta/a/directorio/de/archivos
```


> **Nota**: Reemplaza `db_user`, `db_password`, `mysecretkey` y las rutas para los ficheros por tus propios valores de configuración.


3. **Frontend**: No necesita configuración de variables de entorno, a menos que se requiera una URL específica para el backend en el archivo de configuración de la API del frontend.

Instalación y Uso
-----------------

### Usando Docker

**1. Clona el repositorio**:

```bash
git clone https://github.com/cabrasky/web-yambo.git
cd web-yambo
```

**2. Actualiza el archivo `docker-compose.yml` (si es necesario)**:

Asegúrate de que el archivo `docker-compose.yml` tenga la configuración adecuada para tu entorno. Esto puede incluir ajustar las variables de entorno, los puertos o cualquier otro servicio adicional que requiera tu aplicación.

**3. Ejecuta los servicios**:

```bash
docker-compose up --build
```

### Sin Docker

**1. Clona el repositorio**:

```bash
git clone https://github.com/cabrasky/web-yambo.git
cd web-yambo
```

**2. Ejecuta los servicios**:

*   **Backend**: Sigue las instrucciones en la sección de backend.
*   **Frontend**: Sigue las instrucciones en la sección de frontend.