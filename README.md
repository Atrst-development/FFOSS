# FFOSS - Forms Free Open Source Software

FFOSS is an open-source platform designed for forms replies and management, featuring a robust Spring Boot REST API backend and a responsive Angular web application.

---

## 🏗️ Repository Architecture

This project is structured as a monorepo:

```text
.
├── backend/    # Core REST API (Java / Spring Boot 3.x)
├── clientapp/  # Public Web Application & Form Builder (Angular)
├── docker/     # Local development services (PostgreSQL, Redis, Mailpit)
├── docs/       # Architecture Decision Records (ADRs) & documentation
└── Makefile    # Developer task automation runner
```

---

## ⚙️ Tech Stack

- **Backend:** Java 21+, Spring Boot 3.x, Spring Data JPA, Spring Web, PostgreSQL
- **Frontend:** Angular, TypeScript
- **Infrastructure:** Docker & Docker Compose

---

## 🚀 Getting Started

### Prerequisites

- **Java SDK:** JDK 21+
- **Node.js:** v18+ (LTS) & npm
- **Docker & Docker Compose:** For local database and services
- **GNU Make:** For root command orchestration

### 1. Clone the Repository

```bash
git clone https://github.com/Atrst-development/FFOSS.git
cd FFOSS
```

### 2. Start Infrastructure

```bash
make dev-db
```

### 3. Run the Backend (`backend/`)

```bash
make dev-backend
```
- API Base URL: `http://localhost:8080/api/v1`
- Swagger UI: `http://localhost:8080/swagger-ui.html`

### 4. Run the Client App (`clientapp/`)

In a new terminal:
```bash
make dev-client
```
- Web Application: `http://localhost:4200`

---

## 🧪 Testing

- **Backend Tests:**
  ```bash
  cd backend
  ./mvnw test
  ```
- **Client App Tests:**
  ```bash
  cd clientapp
  npm test
  ```
- **All Tests:**
  ```bash
  make test-all
  ```

---

## 🤝 Contributing

Please read [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) for details on our code of conduct, git workflow, and pull request submission guidelines.
