# Microservicios Grupo 4

Este proyecto es una arquitectura basada en microservicios desarrollada para la materia de Desarrollo Web Avanzado. Cada microservicio está implementado con diferentes tecnologías y lenguajes, permitiendo la gestión de autenticación, comentarios, posts y más.

## Estructura del Proyecto

- **autenticacion/**: Microservicio de autenticación basado en Django y Django REST Framework.
- **auth/**: Microservicio de autenticación con Node.js, Express y MongoDB usando JWT.
- **comentarios/**: Microservicio de comentarios construido con FastAPI y MongoDB.
- **CRUD-Posts/**: Microservicio para gestión de posts (CRUD) en Python.
- **gestionpost/**: Microservicio para gestión de posts en Java (Spring Boot).

## Tecnologías Utilizadas
- Python (Django, FastAPI)
- Node.js (Express, JWT, MongoDB)
- Java (Spring Boot)
- Docker y Docker Compose

## Ejecución con Docker Compose
Para levantar los servicios principales, utiliza:

```sh
docker-compose up --build
```

Puedes modificar los archivos `docker-compose.yml` para agregar o quitar servicios según lo requieras.

## Microservicios

### 1. Autenticación (Django)
Ubicación: `autenticacion/`
Permite la gestión de usuarios y autenticación vía API REST.

### 2. Auth (Node.js)
Ubicación: `auth/`
Autenticación con JWT y almacenamiento de usuarios en MongoDB.

### 3. Comentarios (FastAPI)
Ubicación: `comentarios/`
Permite la gestión de comentarios, conectando con MongoDB.

### 4. CRUD-Posts (Python)
Ubicación: `CRUD-Posts/`
Permite la gestión de posts (crear, leer, actualizar, eliminar).

### 5. GestionPost (Java)
Ubicación: `gestionpost/`
Microservicio para la gestión de posts usando Spring Boot.

## Requisitos Generales
- Docker
- Python 3.7+
- Node.js 12+
- Java 11+

Consulta los README de cada microservicio para instrucciones específicas de instalación y ejecución.
