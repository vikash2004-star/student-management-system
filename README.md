# Student Management System

A RESTful backend application built with Java 17, Spring Boot and MySQL.

## Tech Stack
- Java 17
- Spring Boot 3.2
- Spring Data JPA + Hibernate
- MySQL
- Maven

## Features
- Complete CRUD operations on Student data
- Layered Architecture (Controller → Service → Repository)
- RESTful APIs tested with Postman
- Proper HTTP status codes and exception handling
- ## How to Run Locally
1. Clone this repo
2. Create MySQL database: `CREATE DATABASE student_db;`
3. Update `application.properties` with your DB credentials
4. Run: `mvn spring-boot:run`
5. API runs at: `http://localhost:8080`
