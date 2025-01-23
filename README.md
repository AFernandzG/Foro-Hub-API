# ForoHub API 📚
<p align="center"> 
</p>

<p align="left">
   <img src="https://img.shields.io/github/stars/AFernandzG?style=social">
  <img src="http://img.shields.io/static/v1?label=STATUS&message=TERMINADO&color=ORANGE&style=for-the-badge" /> 
  <img src="https://img.shields.io/badge/language-Java-007396?style=for-the-badge"/> 
  <img src="https://img.shields.io/badge/framework-Spring%20Boot-6DB33F?style=for-the-badge"/> 
  <img src="https://img.shields.io/badge/database-MySQL-4479A1?style=for-the-badge"/> 
</p>

## Descripción del Proyecto

Esta aplicación es una API RESTful desarrollada como parte del desafío final del programa Oracle Next Education junto con Alura LATAM. ForoHub permite la gestión completa de foros de discusión, permitiendo a los usuarios realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) sobre temas y respuestas.

Además, ForoHub incorpora un sistema robusto de autenticación y autorización para restringir el acceso a la información, garantizando la seguridad y privacidad de los datos. La aplicación utiliza una base de datos para la persistencia de datos y sigue las mejores prácticas del modelo REST, asegurando un diseño eficiente y escalable.

---

## Estructura del Proyecto 📂

```plaintext
src
 ├── main
 │   ├── java/
 |   |    └── com/alura/foro/hub/api
 │   │         ├── controller           -> REST controllers.
 │   │         ├── domain               -> JPA Entities repositoriesn and data transfer Objects.
 │   │         └── infra                
 │   │              ├── errores         -> Error handlers, security and docs.
 │   │              ├── security        
 │   │              ├── service         -> Business Logic.
 │   │              └── sprincdoc
 │   └── resources
 │       ├── application.properties     -> Configuration app.
 │       └── db.migration.sql           -> Scripts SQL and migration with flyway (optional).
 └── test
     └── java/com/alura/foro/hub/api          -> Units Test and Integration.
```
## Requisitos 📋
- **Java 17 o superior**
- **Spring Boot**
- **Hibernate**
- **Flyway** (opcional para migraciones de base de datos)

---
## Endpoints Principales 🚀
### Usuarios 👥
- **Crear Usuario**
  - **Método**: POST
  - **URL**: /users
  - **Descripción**: Registra un nuevo usuario en la base de datos.
  - **Cuerpo de la Solicitud**:

```json   
   {
    "username": "johndoe",
    "password": "password123",
    "profileType": "USER"
    }
```
- ### Listar Todos los Usuarios*
  - **Método**: GET
  - **URL**: `/users/all`
  - **Descripción**: Enumera todos los usuarios independientemente de su estado.

---
## Autenticación 🔐
- ### Autenticar Usuario
  - **Método**: POST
  - **URL**: `/login`
  - **Descripción**: Autentica al usuario con las credenciales proporcionadas y genera un token JWT para el acceso.
  - **Cuerpo de la Solicitud**:

```json
   {
    "email": "usuario@example.com",
    "clave": "password123"
    }
```
---
## Respuestas 💬
- ### Crear Respuesta
  - **Método**: POST
  - **URL**: `/answers`
  - **Descripción**: Registra una nueva respuesta en la base de datos, vinculada a un usuario y tema existente.
  - **Cuerpo de la Solicitud**:

```json
{
  "message": "Esta es una respuesta ejemplo.",
  "usuarioId": 5,
  "topicoId": 3
}
```
- ### Listar Respuestas por Tema
- Método: GET
- URL: /answers/topic/{topicId}
- Descripción: Lee todas las respuestas del tema dado.

---
## Temas 📑
- ### Crear Tema
  - **Método**: POST
  - **URL**: `/topics`
  - **Descripción**: Registra un nuevo tema en la base de datos, vinculado a un usuario y curso existentes.
  - **Cuerpo de la Solicitud**:
```json
{
  "title": "Nuevo Tema",
  "message": "Contenido del tema",
  "userid": 1,
  "courseid": 2
}

```
- ### Listar Todos los Temas
  - **Método**: GET
  - **URL**: `/topics/all`
  - **Descripción**: Lee todos los temas independientemente de su estado.
- ### Obtener Solución de Tema
  - **Método**: GET
  - **URL**: /topics/{id}/solution
  - **Descripción**: Lee la respuesta del tema marcada como su solución.

---
## Configuración 🛠️
**Configura la aplicación editando el archivo `application.properties` en el directorio `src/main/resources`.**

---
## Migraciones de Base de Datos 🗄️
**Si estás utilizando Flyway para las migraciones, asegúrate de colocar tus scripts SQL en `src/main/resources/db.migration.sql`.**

---
### 📝 Licencia
**Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo `LICENSE` para obtener más información.**

---
**¡Gracias por usar ForoHub API! Si tienes alguna pregunta o sugerencia, no dudes en contactar.** 😊

---
## ✒️ Autores 

[<img src="https://avatars.githubusercontent.com/u/173502397?s=400&u=c06b4e605c8212c5e9640a90ded8fd7ba11b6d3f&v=4" width=115><br><sub>Antonio Fernandez</sub>](https://github.com/AFernandzG)

---
