# SkillBridge – Campus Peer Skill Exchange & Learning Portal

## Aim
To develop a Java-based web application that allows students to register, log in, publish skills they can teach, and manage those skills using a MySQL database.

## Abstract
SkillBridge is a campus peer-learning portal. It uses HTML/CSS for the interface, JSP for dynamic pages, Jakarta Servlets for request processing, JDBC for user registration/login, Hibernate for skill CRUD, and a separate Spring Boot REST API for skill resources.

## Objectives
1. Provide student registration and login.
2. Demonstrate HTTP GET and POST.
3. Maintain login state using HttpSession.
4. Connect Java to MySQL using JDBC and PreparedStatement.
5. Perform skill CRUD using Hibernate ORM.
6. Expose skill data through REST endpoints using JSON.

## Software Requirements
- JDK 17
- Apache NetBeans
- Apache Tomcat 11
- MySQL Server and MySQL Workbench
- Maven
- Postman (optional)

## Modules
1. Home page
2. Registration
3. Login and session management
4. Dashboard
5. Add/view/update/delete skills
6. Session information
7. ServletConfig demonstration
8. Spring Boot REST API

## Architecture
Browser → HTML/JSP → Jakarta Servlet → JDBC or Hibernate → MySQL.
A separate REST client communicates with Spring Boot Controller → Spring Data JPA/Hibernate → MySQL.

## Database Tables
- `users`: user profile and password hash
- `skills`: skills offered by users
- `skill_requests`: planned extension for peer learning requests
- `feedback`: planned extension for feedback

## Result
The application demonstrates registration/login, session tracking, skill CRUD, JDBC, Hibernate and REST API methods. The actual result must be verified by running the project locally and capturing screenshots.

## Security note
Passwords are hashed with BCrypt in the web module. This is a teaching project; production systems require additional security controls such as HTTPS, CSRF protection, robust authorization, rate limiting, safe secret management, and comprehensive validation.
