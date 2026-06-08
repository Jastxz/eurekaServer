---
inclusion: fileMatch
fileMatchPattern: "dockerfile,Dockerfile,docker-compose*,.woodpecker*"
---

# Deployment — eurekaServer

## CI/CD
- Woodpecker CI pipeline defined in `.woodpecker.yaml`
- Builds Docker image and deploys

## Docker
- `dockerfile` at repo root
- Build: `docker build -t eureka-server .`
- Runs on default Eureka port 8761

## Local
- `./mvnw spring-boot:run`
- Must be started BEFORE other microservices
