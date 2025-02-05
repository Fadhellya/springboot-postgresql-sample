# Employee Management REST API

## Overview
This project provides a simple Employee Management REST API built using **Spring Boot** and **Java 8**. The API allows you to perform CRUD (Create, Read, Update, Delete) operations on Employee data.

## Prerequisites
- **Java 8**
- **Spring Boot**
- **PostgreSQL**
- **Maven**


## Environment Variables
Ensure the following environment variables are set before running the application:

```env
DB_HOST=your-database-host
DB_PORT=5432
DB_NAME=your-db-name
SPRING_DATASOURCE_USERNAME=your-db-username
SPRING_DATASOURCE_PASSWORD=your-db-password
```

## Database Configuration (Spring Data Source)

```properties
spring.datasource.url=jdbc:postgresql://${DB_HOST}:${DB_PORT}/${DB_NAME}
spring.datasource.username=${SPRING_DATASOURCE_USERNAME}
spring.datasource.password=${SPRING_DATASOURCE_PASSWORD}

# Hibernate Properties
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.hibernate.ddl-auto=update
```

## API Endpoints

### Get All Employees
**Request:**
```http
GET /api/v1/employees
```
**Response:**
```json
[
  {
    "id": 1,
    "firstName": "John",
    "lastName": "Doe",
    "emailId": "john.doe@example.com"
  }
]
```

### Get Employee by ID
**Request:**
```http
GET /api/v1/employees/{id}
```
**Response:**
```json
{
  "id": 1,
  "firstName": "John",
  "lastName": "Doe",
  "emailId": "john.doe@example.com"
}
```

### Create Employee
**Request:**
```http
POST /api/v1/employees
Content-Type: application/json
```
**Body:**
```json
{
  "firstName": "Jane",
  "lastName": "Smith",
  "emailId": "jane.smith@example.com"
}
```
**Response:**
```json
{
  "id": 2,
  "firstName": "Jane",
  "lastName": "Smith",
  "emailId": "jane.smith@example.com"
}
```

### Update Employee
**Request:**
```http
PUT /api/v1/employees/{id}
Content-Type: application/json
```
**Body:**
```json
{
  "firstName": "Jane",
  "lastName": "Doe",
  "emailId": "jane.doe@example.com"
}
```
**Response:**
```json
{
  "id": 2,
  "firstName": "Jane",
  "lastName": "Doe",
  "emailId": "jane.doe@example.com"
}
```

### Delete Employee
**Request:**
```http
DELETE /api/v1/employees/{id}
```
**Response:**
```json
{
  "deleted": true
}
```

For any issues, feel free to open an issue or contribute to the project!
