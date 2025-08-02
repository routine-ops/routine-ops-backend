# Contributing to routine-ops-backend

Thank you for your interest in contributing to **routine-ops-backend**! Please follow these guidelines to ensure a smooth and consistent workflow.

## 1. Code of Conduct
All contributors must adhere to our [Code of Conduct](CODE_OF_CONDUCT.md). Any form of harassment or discrimination will not be tolerated.

## 2. Getting Started
1. **Fork** the repository on GitHub.  
2. **Clone** your fork locally:
   ```bash
   git clone git@github.com:<your-username>/routine-ops-backend.git
   cd routine-ops-backend
   ```
3. **Install prerequisites** (Java 21, Maven, Docker).  
4. **Setup configuration**:
   - Copy `application.example.yml` to `application.yml` and fill in your DB credentials and any profile-specific settings.
5. **Build** and **run**:
   ```bash
   mvn clean package
   docker-compose up --build
   ```

## 3. Branching Strategy
- Create feature branches off `main` using your Kanban/JIRA ID:
  - **Feature:** `feature/<JIRA-ID>-short-description`  
    e.g., `feature/ROUT-123-implement-user-auth`
  - **Bugfix:** `bugfix/<JIRA-ID>-short-description`  
    e.g., `bugfix/ROUT-124-fix-nullpointer`
  - **Chore:** `chore/<JIRA-ID>-description`  
    e.g., `chore/ROUT-125-update-dependencies`

## 4. Code Style & Conventions
- **Java:** Follow the [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html).
- **Formatting:** Use Maven’s `formatter-maven-plugin` to autoformat code.
- **Linting:** Enabled via `mvn verify` (includes Checkstyle and SpotBugs).

## 5. Writing Tests
- **Unit Tests:** Write JUnit 5 tests for all new code.  
- **Integration Tests:** Use Testcontainers for PostgreSQL tests.  
- **BDD Scenarios:** Create Cucumber features under `src/test/resources/features` and step definitions in `src/test/java`.
- Run all tests with:
  ```bash
  mvn clean verify
  ```

## 6. Pull Requests
1. **Open an issue** using our [Issue Template](.github/ISSUE_TEMPLATE/development.yml).  
2. **Branch off** for your issue.  
3. **Commit** with clear messages (`feat:`, `fix:`, `chore:` prefixes).  
4. **Push** and **open a PR** against `main`.  
5. **Reference** the issue in your PR (`Closes #<issue-number>`).  
6. **Await review**; address feedback promptly.

## 7. Continuous Integration
- Our GitHub Actions pipeline runs on every PR to:
  - **Compile & Package** via Maven
  - **Run Tests** (unit, integration, BDD)
  - **Static Analysis** (Checkstyle, SpotBugs)
- Ensure your PR passes all checks before requesting merge.

## 8. Releases & Versioning
- We follow [Semantic Versioning](https://semver.org/).  
- Label PRs with `major`, `minor`, or `patch` for automated changelog generation.  

## 9. Security
Report security issues privately to **security@routine-ops.com**; do not use public issues.

---

We appreciate your contributions—thank you for making **routine-ops-backend** better! 🚀
