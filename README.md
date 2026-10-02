# Seat Reservation Service

A seat-reservation backend for high-demand on-sales. Its job is to stay correct under contention:
- no seat is ever sold twice
- the per-user seat limit holds
- retried requests are idempotent

Stack: Java 21, Spring Boot 4, PostgreSQL 16, Flyway, Micrometer/Prometheus.

## Run locally (Docker)

Requires only Docker.

```bash
docker compose up --build
curl localhost:8080/actuator/health
```

The same `Dockerfile` is used for the cloud deployment.
Configuration comes from environment variables:

| Variable      | Default                                  |
|---------------|------------------------------------------|
| `DB_URL`      | `jdbc:postgresql://localhost:5432/seats` |
| `DB_USER`     | `seats`                                  |
| `DB_PASSWORD` | `seats`                                  |
| `PORT`        | `8080`                                   |

## Build without Docker

Requires JDK 21.

```bash
./mvnw -DskipTests package
```

More docs (deploy, burst test) are added as the service is built.
