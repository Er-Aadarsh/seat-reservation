# Seat Reservation Service

A seat-reservation backend for high-demand on-sales. Its job is to stay correct under contention:
- no seat is ever sold twice
- the per-user seat limit holds
- retried requests are idempotent

Stack: Java 21, Spring Boot 4, PostgreSQL, Flyway, Micrometer/Prometheus.

## Build

```bash
./mvnw -DskipTests package
```

More docs (running locally with Docker, deploy, burst test) are added as the service is built.
