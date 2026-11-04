# SkillBridge — Corrected Mini-Project

## Requirements
- JDK 17
- Apache NetBeans with Maven support
- Apache Tomcat 11 for `SkillBridgeWeb`
- MySQL Server and MySQL Workbench
- Postman (for REST API testing)

## Project folders
- `SkillBridgeWeb`: JSP, Jakarta Servlets, JDBC registration/login, session tracking, Hibernate skill CRUD.
- `SkillBridgeAPI`: Spring Boot REST API for skill CRUD.
- `database.sql`: schema.

## 1. Create the database
Open MySQL Workbench, open `database.sql`, and execute the script.

## 2. Configure database credentials
For `SkillBridgeWeb`, edit:
- `SkillBridgeWeb/src/main/java/com/skillbridge/util/DBConnection.java`
- `SkillBridgeWeb/src/main/resources/hibernate.cfg.xml`

For `SkillBridgeAPI`, edit:
- `SkillBridgeAPI/src/main/resources/application.properties`

Use the same MySQL username/password in all three places. Do not commit real credentials to a public repository.

## 3. Build and run the web application
1. Open `SkillBridgeWeb` as a Maven project in NetBeans.
2. Confirm the project JDK is 17.
3. Configure Tomcat 11 in NetBeans.
4. Right-click the project and choose **Clean and Build**.
5. Run/deploy it to Tomcat.
6. Open `http://localhost:8080/SkillBridgeWeb/`.

## 4. Test the web application
1. Register a new account. The password is hashed using BCrypt.
2. Log in using that account.
3. Open Session Information.
4. Add a skill.
5. View the skills list.
6. Update or delete a skill you own.
7. Verify rows in MySQL Workbench.

## 5. Build and run the API
1. Open `SkillBridgeAPI` as a separate Maven project.
2. Set the database credentials in `application.properties`.
3. Run `com.skillbridge.api.SkillBridgeApiApplication`.
4. The API uses port 8081.
5. Test `http://localhost:8081/api/skills`.

## API test examples
GET all:
`GET http://localhost:8081/api/skills`

POST:
`POST http://localhost:8081/api/skills`
Header: `Content-Type: application/json`
```json
{
  "userId": 1,
  "skillName": "Python",
  "category": "Programming",
  "level": "Intermediate",
  "description": "Python fundamentals"
}
```

PUT:
`PUT http://localhost:8081/api/skills/1`
```json
{
  "userId": 1,
  "skillName": "Advanced Python",
  "category": "Programming",
  "level": "Advanced",
  "description": "Advanced Python concepts"
}
```

DELETE:
`DELETE http://localhost:8081/api/skills/1`

## Important notes
- Tomcat 11 requires Jakarta APIs (`jakarta.servlet.*`), not old `javax.servlet.*`.
- The web app and API are separate processes but use the same MySQL database.
- BCrypt password hashes are stored; the application does not store plain-text passwords.
- This is a learning project, not a production-ready security design. A production deployment also needs CSRF protection, HTTPS, robust validation, authorization policies, rate limiting, secure secret management, and proper error pages.
