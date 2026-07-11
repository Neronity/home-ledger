# Home Ledger Backend

Spring Boot REST API for Home Ledger.

## Planned Stack

- Java 26
- Spring Boot 3.x
- Maven
- Spring Web
- Spring Data JPA / Hibernate
- PostgreSQL
- Flyway
- Validation
- Actuator

## Local Commands

Run tests from the `backend/` directory:

```powershell
./mvnw.cmd test
```

Run the backend locally:

```powershell
./mvnw.cmd spring-boot:run
```

The backend expects PostgreSQL to be available locally. From the repository root, start PostgreSQL with:

```powershell
docker compose up -d
```

Default backend URL:

```text
http://localhost:8080
```

Actuator health endpoint:

```text
http://localhost:8080/actuator/health
```

## Package Organization

The backend should use feature-oriented packages:

```text
io.github.neronity.homeledger
  transaction/
  category/
  summary/
  common/
```

Implementation will be added in later issues.
