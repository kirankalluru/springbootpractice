# Spring Boot CRUD Application (Without DTO)

This is a **simple Spring Boot CRUD application** built using  
**Spring Boot + Spring Data JPA + MySQL**,  
where the **Entity is used directly** in Controller, Service, and Repository  
(**no DTO layer**).

This project is designed for:
- Beginners learning Spring Boot
- College / academic projects
- Understanding end-to-end backend flow clearly

---

## 🚀 Tech Stack Used

- Java 17+
- Spring Boot
- Spring Web
- Spring Data JPA (Hibernate)
- MySQL
- Maven
- Postman (for testing APIs)

---

## 📁 Project Structure (Without DTO)

springbootpractice
│
├── src/main/java/com/example/demo
│ ├── DemoApplication.java
│ │
│ ├── controller
│ │ └── StudentController.java
│ │
│ ├── service
│ │ └── StudentService.java
│ │
│ ├── repository
│ │ └── StudentRepository.java
│ │
│ └── entity
│ └── Student.java
│
├── src/main/resources
│ └── application.properties
│
└── pom.xml

yaml
Copy code

---

## 🧠 Architecture Flow

Client (Postman / Frontend)
↓
Controller
↓
Service
↓
Repository
↓
MySQL Database

less
Copy code

- **Controller** handles HTTP requests
- **Service** contains business logic
- **Repository** interacts with the database
- **Entity** represents the database table

---

## 🧱 Entity Explanation

`Student.java` represents a **database table**.

```java
@Entity
public class Student {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private String email;
}
Each object = one row in DB

@Id = Primary Key

@GeneratedValue = Auto-increment ID

⚙️ Database Configuration
application.properties

properties
Copy code
server.port=8080

spring.datasource.url=jdbc:mysql://localhost:3306/springboot_crud
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
Hibernate automatically creates tables based on entities.

🔥 CRUD APIs Available
➕ Create Student
bash
Copy code
POST /students
Request Body

json
Copy code
{
  "name": "Kiran",
  "email": "kiran@gmail.com"
}
📖 Get All Students
bash
Copy code
GET /students
🔍 Get Student by ID
bash
Copy code
GET /students/{id}
Example:

bash
Copy code
GET /students/1
✏️ Update Student
bash
Copy code
PUT /students/{id}
Request Body

json
Copy code
{
  "name": "Updated Name",
  "email": "updated@gmail.com"
}
❌ Delete Student
bash
Copy code
DELETE /students/{id}
