# 💻 Aplicación Java Spring Boot — Sistema de Clientes

Aplicación desarrollada con **Spring Boot** y **SQL Server**, como parte de la **prueba técnica**.  
Permite realizar operaciones básicas de **gestión de clientes (CRUD)**.

---

## ⚙️ Tecnologías utilizadas

- **Java 17**
- **Spring Boot 3.x**
- **Spring Data JPA**
- **Maven**
- **Microsoft SQL Server**
- **Lombok** (para reducir código boilerplate)
- **Postman** (para pruebas de endpoints)

---

## 🏗️ Estructura del proyecto

clientes/
├── src/
│ └── main/
│ ├── java/com.evaluacion.clientes
│ │ ├── Cliente.java
│ │ ├── ClienteRepository.java
│ │ ├── ClienteController.java
│ │ └── ClientesApplication.java
│ └── resources/
│ ├── application.yml
│ └── static/
├── pom.xml
└── HELP.md
---

## 🗃️ Configuración de base de datos

Asegúrate de tener creada la base de datos **clientes** antes de ejecutar el proyecto.  
Puedes obtener los scripts desde este repositorio:  
👉 [Base de Datos — Prueba Técnica](https://github.com/Santi1316/Base-de-Datos)

### Configuración (`application.yml`):

```properties
spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=clientes;encrypt=true;trustServerCertificate=true
spring.datasource.username=sa
spring.datasource.password=123456
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
🚀 Ejecución del proyecto
Desde IntelliJ o VS Code:
Abre el proyecto como Maven Project.

Espera a que se descarguen las dependencias.

Ejecuta la clase principal:

ClientesApplication.java
Desde la terminal:
mvn spring-boot:run
La aplicación se iniciará en:
👉 http://localhost:8080

📡 Endpoints disponibles
➕ Agregar un cliente
POST /agregar

Ejemplo JSON:

{
  "nombre": "Santiago Santana",
  "correo": "santiago@example.com",
  "telefono": "3001112233"
}
Respuesta (200 OK):

{
  "id": 1,
  "nombre": "Santiago Santana",
  "correo": "santiago@example.com",
  "telefono": "3001112233"
}
📋 Listar todos los clientes
GET /listar

Respuesta (200 OK):

[
  {
    "id": 1,
    "nombre": "Juan Pérez",
    "correo": "juan@example.com",
    "telefono": "3001234567"
  },
  {
    "id": 2,
    "nombre": "Ana Gómez",
    "correo": "ana@example.com",
    "telefono": "3019876543"
  }
]
🧩 Clases principales
🧱 Cliente.java
Entidad que representa la tabla CLIENTES en la base de datos.

🗃️ ClienteRepository.java
Extiende JpaRepository para realizar operaciones CRUD automáticamente.

🌐 ClienteController.java
Controlador REST con los endpoints /agregar y /listar.

🚀 ClientesApplication.java
Clase principal con el método main() que levanta el servidor Spring Boot.

🧰 Dependencias destacadas (pom.xml)

<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>

    <dependency>
        <groupId>com.microsoft.sqlserver</groupId>
        <artifactId>mssql-jdbc</artifactId>
        <version>12.6.1.jre17</version>
    </dependency>

    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <optional>true</optional>
    </dependency>
</dependencies>
🧪 Pruebas rápidas con Postman
Inicia el proyecto.

Abre Postman.

Crea una colección llamada Clientes API.

Agrega las siguientes peticiones:

GET http://localhost:8080/listar

POST http://localhost:8080/agregar
con cuerpo raw JSON.

👤 Autor
Santiago Santana
📧 santi1316
🔗 GitHub - Santi1316
