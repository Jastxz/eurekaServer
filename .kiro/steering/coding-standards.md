---
inclusion: always
---

# Coding Standards — eurekaServer

## Java / Spring Boot
- Spring Boot 3.x conventions
- Configuration in YAML (`application.yml`)
- Use `@EnableEurekaServer` annotation on main class
- No business logic in this service

## Build & Run
- Build: `./mvnw clean package`
- Run: `./mvnw spring-boot:run` or `java -jar target/*.jar`
- Docker: `docker build -t eureka-server .`
