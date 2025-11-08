# Employee Leave Management System

A Spring Boot web application for managing employee leave requests with role-based access for Employees, Managers, and HR/Admin.

## Features
- Authentication with roles: EMPLOYEE, MANAGER, HR, ADMIN
- Employees: apply for leave, upload documents, view balances and requests
- Managers: approve/reject with comments, email notifications
- HR: calendar view of approved leaves, export Excel/XML reports
- MySQL database with seeded demo data

## Technology
- Java 17, Spring Boot 3
- Spring Security, Spring Data JPA, Thymeleaf
- MySQL Database, Apache POI (Excel), JAXB (XML)

## Database Configuration
- **Host**: bytexldb.com
- **Port**: 5051
- **Database**: db_44346685g
- **Username**: user_44346685g
- **Password**: p44346685g

## Quick Start

### Prerequisites
- Java 17+
- Maven 3.9+ (or use included Maven Wrapper)

### Run
```bash
# Using Maven Wrapper (recommended)
mvnw.cmd spring-boot:run

# Or using Maven (if installed)
mvn spring-boot:run
```
Open `http://localhost:8080` (you will be redirected to login).

### Demo Users
- admin / admin123 (ADMIN, HR)
- manager1 / manager123 (MANAGER)
- employee1 / employee123 (EMPLOYEE)

## File Uploads
Uploaded documents are stored under the `uploads/` directory in the project root. They are referenced from leave requests and can be served via `/files/{filename}`.

## Reports
- Excel: `/reports/excel` -> downloads `leaves.xlsx`
- XML: `/reports/xml` -> downloads `leaves.xml`

## Notes
- Emails are logged/simulated in dev. Configure SMTP in `application.properties` for real emails.
- Leave days are calculated as all days inclusive between start and end.
- Database tables are automatically created on first run.

## Build JAR
```bash
mvnw.cmd clean package
java -jar target/leave-management-0.0.1-SNAPSHOT.jar
```

