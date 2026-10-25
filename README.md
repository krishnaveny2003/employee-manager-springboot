# Employee Management System

## 1. Project Overview

The Employee Management System is a web-based application developed using Spring Boot, Java, MySQL, and Thymeleaf. It allows users to manage employee information through CRUD (Create, Read, Update, and Delete) operations.

This project was developed as part of Lab Sheet 05 to practise Spring Boot application development, database connectivity, form validation, and GitHub version control.

## 2. Technologies Used

- **Java** – Programming language
- **Spring Boot** – Backend application framework
- **Spring MVC** – Handles web requests
- **Spring Data JPA** – Database operations
- **MySQL** – Relational database
- **Thymeleaf** – Dynamic HTML templates
- **Lombok** – Reduces boilerplate Java code
- **Maven** – Dependency and project management
- **Git and GitHub** – Version control
- **Postman** – API testing, if REST endpoints are implemented

## 3. Features

- Register new employees
- View all employee records
- Update employee details
- Delete employee records
- Validate employee input
- Validate email format
- Prevent duplicate email addresses
- Validate phone number format
- Ensure salary is greater than zero
- Store employee records in a MySQL database

## 4. Employee Information

The system manages the following employee details:

- Employee ID
- Full Name
- Email
- Phone
- Department
- Salary

The employee ID is generated automatically by the database.

## 5. Project Structure

```text
employee-manager/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/example/employeemanager/
│       │       ├── EmployeeManagerApplication.java
│       │       ├── model/
│       │       │   └── Employee.java
│       │       ├── repository/
│       │       │   └── EmployeeRepository.java
│       │       ├── service/
│       │       │   └── EmployeeService.java
│       │       └── controller/
│       │           └── EmployeeController.java
│       └── resources/
│           ├── templates/
│           │   ├── employees.html
│           │   └── edit-employee.html
│           └── application.properties
├── pom.xml
├── mvnw
├── mvnw.cmd
├── .gitignore
└── README.md
```

## 6. Database Configuration

Create a MySQL database named `employee_db`.

```sql
CREATE DATABASE employee_db;
```

Configure the database connection in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/employee_db
spring.datasource.username=root
spring.datasource.password=

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

**Note:** Update the database username, password, and connection URL according to your local MySQL configuration. Do not commit real passwords or other secrets to GitHub.

## 7. How to Run the Project

### Prerequisites

- Java 17 or 21, matching the project configuration
- MySQL Server or XAMPP
- Maven Wrapper included in the project
- Git

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/employee-manager-springboot.git
   ```

2. Open the project folder:

   ```bash
   cd employee-manager-springboot
   ```

3. Start MySQL using XAMPP or your installed MySQL server.

4. Create the `employee_db` database.

5. Check the database configuration in `application.properties`.

6. Run the Spring Boot application on Windows:

   ```powershell
   .\mvnw.cmd spring-boot:run
   ```

7. Open the application in your browser:

   http://localhost:8080/employees

## 8. Testing

The following operations should be tested:

| Test Case | Expected Result |
|---|---|
| Submit an empty form | Validation errors are displayed |
| Enter an invalid email | Email validation error is displayed |
| Enter a five-digit phone number | Phone validation error is displayed |
| Enter salary as zero | Salary validation error is displayed |
| Register four employees | Employee records appear in the table |
| Register a duplicate email | Duplicate email is rejected |
| Update an employee | Updated information appears in the table |
| Delete an employee | Employee record is removed |
| Verify database records | MySQL records match the application |

Verify the database using:

```sql
USE employee_db;
SHOW TABLES;
DESCRIBE employees;
SELECT * FROM employees;
```

## 9. GitHub Workflow

The project uses Git for version control and a feature branch for CRUD implementation.

```bash
git switch -c feature/employee-crud
git add .
git commit -m "Add Employee CRUD functionality"
git push -u origin feature/employee-crud
```

Create a Pull Request on GitHub with `main` as the base branch and `feature/employee-crud` as the comparison branch. Review the changes and merge the Pull Request after verification.

## 10. Learning Outcomes

This project provides practical experience in:

- Developing a Spring Boot web application
- Implementing CRUD operations
- Connecting Java applications to MySQL
- Using Spring Data JPA and Lombok
- Validating user input
- Testing database operations
- Managing source code using Git and GitHub Pull Requests

## 11. Author

**Name:** YOUR_NAME  
**Student ID:** YOUR_STUDENT_ID  
**Course:** YOUR_COURSE_NAME  
**Repository:** https://github.com/YOUR_USERNAME/employee-manager-springboot
