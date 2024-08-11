# Microservicio - FastAPI & Mongo - Comentarios

Este proyecto es un microservicio de comentarios construido con FastAPI y MongoDB.

## Requisitos

- Python 3.7+
- MongoDB
- pip (Python package installer)

## Instalación

1. Clona el repositorio:
   ```sh
   git clone <URL_DEL_REPOSITORIO>
   cd <NOMBRE_DEL_REPOSITORIO>
   ```
2. Crea un entorno virtual:
    ```sh
    python3 -m venv venv
    ```
3. Activa el entorno virtual:
   ```sh
   venv\Scripts\activate
   ```

4. Instala las dependencias:
   ```sh
   pip install -r requirements.txt
   ```
   
## Configuración

Asegúrate de que MongoDB esté corriendo en localhost en el puerto 27017. Puedes cambiar la configuración de la base de datos en el archivo db.py.

## Ejecución
Para iniciar el servidor FastAPI, ejecuta:
   ```sh
   uvicorn main:app --reload
   ```
El servidor estará disponible en http://127.0.0.1:8000.

Endpoints
Obtener todos los comentarios
- URL: /comments
- Método: GET
- Descripción: Retorna todos los comentarios.

Obtener un comentario por ID
- URL: /comments/{comment_id}
- Método: GET
- Descripción: Retorna un comentario específico por su ID.

Crear un nuevo comentario
- URL: /comments
- Método: POST
- Descripción: Crea un nuevo comentario.

Actualizar un comentario
- URL: /comments/{comment_id}
- Método: PUT
- Descripción: Actualiza un comentario existente.

Eliminar un comentario
- URL: /comments/{comment_id}
- Método: DELETE
- Descripción: Elimina un comentario por su ID.

Estructura del Proyecto
- main.py: Punto de entrada de la aplicación.
- app/docs.py: Metadatos de la API.
- app/config/db.py: Configuración de la base de datos.
- app/models/comment.py: Modelo de datos para los comentarios.
- app/schemas/comment.py: Esquemas para serializar y deserializar comentarios.
- app/routes/comments.py: Rutas de la API para manejar comentarios.

### Dockerfile
 Para crear un Dockerfile que defina cómo construir la imagen de Docker para el microservicio:
 ```Dockerfile
 # Usar la imagen base de Python
 FROM python:3.7-slim
 # Establecer el directorio de trabajo en /app
 WORKDIR /app
 # Copiar los archivos necesarios al contenedor
 COPY . /app
 # Instalar las dependencias
 RUN pip install --no-cache-dir -r requirements.txt
 # Exponer el puerto 8000
 EXPOSE 8000
 # Comando para ejecutar la aplicación
 CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
 ```
 ### Docker Compose
 Luego, incluir este microservicio en un archivo `docker-compose.yml`:
 ```yaml
 version: '3.8'
 services:
  mongodb:
    image: mongo:latest
    container_name: mongodb
    ports:
      - "27017:27017"
    volumes:
      - mongo_data:/data/db
  fastapi_app:
    build: .
    container_name: fastapi_app
    ports:
      - "8000:8000"
    depends_on:
      - mongodb
 volumes:
  mongo_data
```
