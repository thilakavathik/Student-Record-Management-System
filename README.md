# Spring Boot CRUD Application

A basic Java web application built using **Spring Boot** that performs CRUD (Create, Read, Update, Delete) operations on data stored in a relational database.

## Features

* Create new records
* Retrieve all records
* Retrieve a record by ID
* Update existing records
* Delete records
* RESTful API endpoints for CRUD operations

## Technologies Used

* **Java**
* **Spring Boot**
* **Spring MVC**
* **Spring Data JPA**
* **Hibernate**
* **MySQL**
* **Maven**

## Project Structure

```text
src/
 └── main/
     ├── java/
     │   └── com.example.project/
     │       ├── controller/
     │       ├── service/
     │       ├── repository/
     │       └── entity/
     │
     └── resources/
         └── application.properties
```

### Layers

* **Entity** – Represents the database table and its fields.
* **Repository** – Handles database operations using Spring Data JPA.
* **Service** – Contains the application's business logic.
* **Controller** – Handles HTTP requests and provides REST API endpoints.

## API Operations

| Method | Endpoint          | Description       |
| ------ | ----------------- | ----------------- |
| POST   | `/api/items`      | Create a new item |
| GET    | `/api/items`      | Get all items     |
| GET    | `/api/items/{id}` | Get an item by ID |
| PUT    | `/api/items/{id}` | Update an item    |
| DELETE | `/api/items/{id}` | Delete an item    |

## How to Run

### 1. Clone the repository

```bash
git clone <repository-url>
cd <project-folder>
```

### 2. Configure the database

Update `application.properties` with your MySQL database details:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/your_database
spring.datasource.username=your_username
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### 3. Build the project

```bash
mvn clean install
```

### 4. Run the application

```bash
mvn spring-boot:run
```

The application will start on:

```text
http://localhost:8080
```

## Example

A POST request can be sent to:

```text
POST /api/items
```

with JSON data such as:

```json
{
  "name": "Example Item",
  "description": "Sample item"
}
```

The application processes the request through the **Controller → Service → Repository → Database** flow.

## Future Improvements

* Add input validation
* Add exception handling
* Add Spring Security authentication
* Add API documentation using Swagger/OpenAPI
* Add unit and integration tests
