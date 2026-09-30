
# Project Title

A brief description of what this project does and who it's for

# 🚀 Spring Boot Project

This is a backend application built with [Spring Boot](https://spring.io/projects/spring-boot).

## 📦 Project Structure

src/
└── main/
├── java/ # Source code
└── resources/ # Configuration files
└── test/ # Unit and integration tests


## ⚙️ Technologies Used

- Java 21+ (ou ta version)
- Spring Boot 3.x
- Spring Web
- Spring Data JPA
- H2 / MySQL / PostgreSQL (selon ta config)
- Maven ou Gradle

## ▶️ Getting Started

### Prerequisites

- JDK 21+
- Maven 3.8+ / Gradle
- IDE (IntelliJ, VS Code, etc.)

### Run with Maven 


./mvnw spring-boot:run


### Run with Gradle 

./gradlew bootRun

Configuration
Configure your database and application settings in:

properties
Copier
Modifier

src/main/resources/application.properties

Or if using profiles:

application-dev.properties
application-prod.properties


🧪 Running Tests
bash

./mvnw test