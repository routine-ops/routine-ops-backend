# routine-ops-backend

**Spring Boot backend microservice** powering Routine-Ops. It encapsulates core business logic for user and plan management, handles CRUD operations for users, generates and schedules daily and monthly routines, aggregates ingredient data, and exposes RESTful APIs for both frontend and third-party integrations.

## 🔧 Tech Stack
- **Language:** Java 21
- **Framework:** Spring Boot 3.2
- **Build Tool:** Maven
- **Database:** PostgreSQL
- **ORM:** Hibernate 6
- **Containerization:** Docker
- **Testing:** JUnit 5, Testcontainers, Cucumber (for BDD)
- **CI/CD:** GitHub Actions

## 🚀 Getting Started

### Prerequisites
- Java 21 SDK
- Maven 3.8+
- Docker & Docker Compose
- PostgreSQL instance (local or container)

### Clone & Setup
```bash
git clone git@github.com:routine-ops/routine-ops-backend.git
cd routine-ops-backend
```

### Configure Environment
1. Copy `application.example.yml` to `application.yml` and set:
   ```yaml
   spring:
     datasource:
       url: jdbc:postgresql://localhost:5432/routine_ops
       username: your_user
       password: your_password
   ```
2. (Optional) Set additional profiles in `application-prod.yml` for production.

### Build & Run Locally
```bash
mvn clean package
java -jar target/routine-ops-backend-0.1.0.jar
```

### Docker Compose
```bash
docker-compose up --build
```

## 📦 API Endpoints
| Method | Endpoint                         | Description                                   |
| ------ | -------------------------------- | --------------------------------------------- |
| GET    | `/api/users`                     | List all users                                |
| POST   | `/api/users`                     | Create a new user                             |
| GET    | `/api/plans/{userId}`            | Fetch monthly plan for a user                 |
| POST   | `/api/plans/{userId}`            | Upload and trigger a new plan for a user      |
| GET    | `/api/ingredients/week`          | Get weekly aggregated ingredient list         |
| GET    | `/api/ingredients/{date}`        | Get daily ingredient list for a specific date |

## 🛠️ Features
- **Plan Scheduling:** Monthly and daily routines
- **Ingredient Aggregation:** Weekly and daily lists
- **User Management:** CRUD APIs for users and plans
- **Integration Testing:** Real PostgreSQL via Testcontainers

## 🤝 Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on setting up, testing, and submitting PRs.

## 📄 License
See `PROPRIETARY_LICENSE.md` for usage terms. Feel free to reach out at licensing@routine-ops.com.
