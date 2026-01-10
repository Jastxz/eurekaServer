# Eureka Server

Service Discovery Server based on Netflix Eureka, built with Spring Boot.

## Overview

This project serves as a registry for microservices, allowing them to find and communicate with each other without hardcoding hostnames and ports. It is a critical component in the microservices architecture.

## Tech Stack

- **Java:** 21
- **Spring Boot:** 4.0.1
- **Spring Cloud:** 2025.1.0

## Prerequisites

- JDK 21 or higher
- Maven 3.8+ (optional, wrapper provided)
- Docker (optional, for containerization)

## Getting Started

### Running Locally

1.  Clone the repository.
2.  Run with Maven:
    ```bash
    ./mvnw spring-boot:run
    ```
    Or if you have Maven installed:
    ```bash
    mvn spring-boot:run
    ```

The server will start on port `8761`. Access the dashboard at [http://localhost:8761](http://localhost:8761).

### Running with Docker

1.  Build the image:
    ```bash
    docker build -t eureka-server .
    ```
2.  Run the container:
    ```bash
    docker run -p 8761:8761 eureka-server
    ```

## Configuration

- **Port:** 8761
- **Self Preservation:** Disabled by default (suitable for development/testing).
- **Standalone:** Configured not to register with itself.

## CI/CD Pipeline

The project uses [Woodpecker CI](https://woodpecker-ci.org/) for continuous integration and deployment.

**Pipeline Steps:**

1.  **Build:** Compiles the project using Maven.
2.  **Docker Push:** Builds the Docker image and pushes it to GitHub Container Registry (GHCR).
3.  **Deploy:** Pulls the new image and updates the service using Docker Compose on the target server.
