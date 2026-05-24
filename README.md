# Student Management System

A Spring Boot backend project I built from scratch over the past month. 
Started with basic CRUD, then added proper authentication and security 
as I learned more. Still improving it.

---

## The Journey

I started this project in April 2026 with just basic student CRUD operations 
using Spring Boot and MySQL. Once that was working, I wanted to make it more 
realistic — so I added Spring Security with JWT authentication and role-based 
access control in May. Small steps, but each one taught me something new.

---

## What It Does

- Store and manage student records in a MySQL database
- Login system — you get a JWT token after logging in
- Two roles: Admin (full access) and Student (view only)
- All passwords are BCrypt encrypted — never stored as plain text
- Clean layered code — Controller handles requests, Service has logic, 
  Repository talks to DB

---

## Tech Stack

- Java 17
- Spring Boot 3.2
- Spring Security
- JWT (JSON Web Token)
- Spring Data JPA + Hibernate
- MySQL
- Maven

---

## Project Structure
src/main/java/com/example/student/
├── config/         → Spring Security configuration
├── controller/     → AuthController, StudentController
├── dto/            → AuthRequest, AuthResponse
├── entity/         → Student, User
├── repository/     → StudentRepository, UserRepository
├── security/       → JwtAuthFilter, JwtService
└── service/        → StudentService, StudentServiceImpl

---

## Running Locally

You need Java 17, MySQL and Maven installed.

```bash
# Clone
git clone https://github.com/vikash2004-star/student-management-system.git

# Create database in MySQL
CREATE DATABASE student_db;

# Add your credentials in application.properties
spring.datasource.username=your_username
spring.datasource.password=your_password

# Run
mvn spring-boot:run
```

Runs on `http://localhost:8080`

---

## API Reference

### Public Routes


GET    /api/students       →  View all students     (Admin + Student)
GET    /api/students/{id}  →  View one student      (Admin + Student)
POST   /api/students       →  Add new student       (Admin only)
PUT    /api/students/{id}  →  Update student        (Admin only)
DELETE /api/students/{id}  →  Delete student        (Admin only)



## What I Learned

Honestly the Security part was confusing at first — understanding how 
the JWT filter intercepts every request, validates the token, and sets 
the authentication in SecurityContext took me a while. But once it 
clicked, it made complete sense. BCrypt hashing, stateless sessions, 
role-based access — all of it came together in this project.
