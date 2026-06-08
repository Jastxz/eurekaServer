---
inclusion: always
---

# Architecture — eurekaServer

## Stack
- **Framework:** Spring Boot + Spring Cloud Netflix Eureka Server
- **Language:** Java
- **Build:** Maven (mvnw wrapper)
- **CI:** Woodpecker CI (`.woodpecker.yaml`)
- **Container:** Dockerfile

## Purpose
Service discovery server for microservices architecture. Other microservices (microNeural, microPrimeNumbers, microTracking, microGateway, micro-adversarial-search) register here.

## Module Boundaries (from graphify: 8 nodes, 2 communities)
- Minimal codebase: Spring Boot application class + Eureka configuration
- `src/main/` — Application entry + `application.yml` config
- `src/test/` — Integration tests

## Dependency Rules
- This service has NO business logic — it is infrastructure only
- Do not add domain-specific code here
- Configuration via `application.yml` / `application.properties`
- Other microservices depend on this being available — it is the registry
