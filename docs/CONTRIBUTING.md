# Contributing to the Platform

Thank you for your interest in contributing! We welcome contributions from developers of all skill levels.

This document outlines the guidelines and step-by-step instructions for setting up your local environment, working on issues, and submitting Pull Requests (PRs).

---

## 1. Repository Architecture

This project is structured as a monorepo containing three core applications and shared tooling:


```

.
├── backend/    # Core REST API (Java / Spring Boot)
├── clientapp/  # Public Web Application & Form Builder (Angular)
├── adminapp/   # Admin & Analytics Dashboard (Flutter Cross-Platform)
├── docker/     # Local development services (PostgreSQL, Redis, Mailpit)
├── docs/       # Architecture Decision Records (ADRs) & API specifications
└── Makefile    # Developer task automation runner

```

---

## 2. Prerequisites

Before getting started, ensure you have the following installed on your machine:

| Component | Technology | Minimum Version | Required For |
| :--- | :--- | :--- | :--- |
| **Docker Engine** | Docker & Compose | 24.0+ | Database & local services |
| **Java SDK** | JDK OpenJDK / Temurin | 17+ / 21+ | `backend/` development |
| **Node.js** | Node.js & npm | v18+ (LTS) | `clientapp/` development |
| **Flutter SDK** | Flutter & Dart | 3.19+ (Stable) | `adminapp/` development |
| **Make** | GNU Make | Pre-installed on Linux/macOS | Root command orchestration |

---

## 3. Local Development Setup

### Step 1: Clone the Repository
```bash
git clone [https://github.com/your-org/your-repo.name.git](https://github.com/your-org/your-repo.name.git)
cd your-repo-name

```

### Step 2: Start Infrastructure Dependencies

Spin up the local database (PostgreSQL), caching (Redis), and email testing tool (Mailpit):

```bash
make dev-db

```

* **PostgreSQL Admin Port:** `5432`
* **Mailpit UI:** `http://localhost:8025`

### Step 3: Launch the Backend (`backend/`)

The backend uses Maven Wrapper, so you do not need Maven pre-installed.

```bash
make dev-backend

```

* **API Base URL:** `http://localhost:8080/api/v1`
* **Swagger API Docs:** `http://localhost:8080/swagger-ui.html`

### Step 4: Launch the User Web App (`clientapp/`)

In a new terminal tab:

```bash
make dev-client

```

* **Angular Web App:** `http://localhost:4200`


---

## 4. Branch & Git Strategy

We follow a simplified **Trunk-Based / Feature-Branch** workflow:

1. **Main Branch:** `main` (Production-ready code).
2. **Branch Naming Conventions:**
* `feat/short-description` for new features.
* `fix/short-description` for bug fixes.
* `docs/short-description` for documentation updates.
* `refactor/short-description` for code improvements.



### Creating a Branch

```bash
git checkout main
git pull origin main
git checkout -b feat/add-form-analytics-chart

```

---

## 5. Coding Standards & Linting

Please run tests and format checks before opening a Pull Request:

### Backend (Spring Boot)

Follow standard Java Google/Spring formatting conventions.

```bash
cd backend
./mvnw clean test

```

### Client App (Angular)

Ensure ESLint checks and Jasmine unit tests pass.

```bash
cd clientapp
npm run lint
npm run test -- --watch=false

```

### Running All Test Suites

From the project root:

```bash
make test-all

```

---

## 6. Submitting a Pull Request (PR)

1. **Push your branch to GitHub:**
```bash
git push origin feat/add-form-analytics-chart

```


2. **Open a PR** against the `main` branch.
3. **Fill out the PR Template:** Explain *what* changes were made and *why*.
4. **CI Checks:** Ensure all automated GitHub Actions checks pass:
* `CI - Backend`
* `CI - ClientApp`
* `CI - AdminApp`


5. **Code Review:** At least one maintainer review is required before merging.

---

## 7. Reporting Bugs & Requesting Features

* **Found a Bug?** Open a [GitHub Issue](https://www.google.com/search?q=https://github.com/your-org/your-repo-name/issues) using the **Bug Report** template. Include reproduction steps, expected behavior, and environment details.
* **Want a Feature?** Submit a [GitHub Issue](https://www.google.com/search?q=https://github.com/your-org/your-repo-name/issues) using the **Feature Request** template to discuss your proposal with maintainers before starting work.

Thank you for helping us build an incredible open-source platform!
