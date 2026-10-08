# Hi there 👋 I'm Gabriel

Junior Backend Developer specializing in Java & Spring Boot.

[LinkedIn](https://linkedin.com/in/luque-gabriel) · [luquegabrielcv@gmail.com](mailto:luquegabrielcv@gmail.com)


## About Me

I build REST APIs with Java and Spring Boot, with authentication/authorization via JWT and OAuth 2.0, on PostgreSQL and MongoDB. I write unit tests with JUnit 5 and Mockito, containerize with Docker, and follow standard GitHub workflows. I've also worked with Node.js, .NET/C#, and Angular/TypeScript on the frontend side.

---
## Projects

### [HotelApp — Hotel Reservation Platform](https://github.com/LuqueGabriel01/HotelReservationApp)

Hotel booking system split into 7 Spring Boot microservices behind a single API gateway. Guests search availability and book or cancel rooms with email confirmations; admins manage hotels, rooms, pricing and photos from a separate panel.

**Key decisions**
- **Single entry point:** JWT validation, routing and rate limiting live in the gateway, in one place.
- **Database per service:** each service owns its PostgreSQL database. Trade-off: no cross-service joins.
- **Events for notifications:** booking confirmations and cancellations go through Kafka to a notification service (email via SMTP), so the booking flow doesn't depend on email delivery.
- **AI as an isolated service:** the agent service uses Google Gemini for room recommendations and a support chat, with session state in Redis, separate from the booking core.

**Delivery:** Angular client consuming the gateway · GitHub Actions checks code quality and Docker builds
**Stack:** Java 21 · Spring Boot 4 · Spring Security + JWT · PostgreSQL · Kafka · Redis · Docker Compose


### [menuFlow — Restaurant Management API](https://github.com/LuqueGabriel01/menuFlow)

REST API that takes a restaurant from table to bill: QR-code tables, dining sessions, a multi-language menu with allergens, kitchen workflow and invoicing. Built to practice a complete API design: domain modeling, security, testing and Docker deployment.

**Key decisions**
- **Two login paths:** staff sign in with credentials and get their real role; customers scan the table's QR and get a limited `ROLE_USER` token, with no account needed. A table can only order while its session is open.
- **Stateless JWT with role-based access** (`ADMIN`, `CASHIER`, `CHEF`, `KITCHEN`, `USER`) enforced per endpoint.
- **Explicit order flow** (`PENDING → IN_PROGRESS → READY → SERVED → CLOSED`), with the kitchen queue separated from the general active-orders view.
- **Consistent API contract:** every response uses the same envelope, and errors return a structured body with validation details.
- **No secrets in the repo:** configuration references environment variables and `.env` is never committed.

**Proof:** JUnit 5 + Mockito (service tests and `@WebMvcTest` controller tests) · GitHub Actions on every push/PR (tests against MySQL, Docker image build) · per-module docs and ER diagram · Swagger UI
**Next:** demo frontend
**Stack:** Java 21 · Spring Boot · Spring Data JPA · MySQL 8 · Spring Security + JWT · Docker Compose

### [Spring Boot Chat Backend — Real-Time Chat](https://github.com/LuqueGabriel01/spring-boot-chat-backend)

Frontend-agnostic chat backend: live broadcast, typing indicator and recent message history when a client joins.

**Key decisions**
- **Documented messaging contract:** fixed destinations and topics with typed payloads, plus a client usage example in the README.
- **Private history channel:** history is published on a per-client topic, and client ids are validated against a strict pattern.
- **Server-side truth:** the server sets each message's id and timestamp and persists only real messages, not join events.
- **Configurable by environment:** allowed origins and history size.

**Proof:** JUnit 5 + Mockito · Docker Compose with persistent MongoDB · health check via Spring Actuator
**Stack:** Java 21 · Spring Boot 4 · WebSocket (STOMP + SockJS) · MongoDB 8

### [FleetControl — Fleet Management Platform](https://github.com/fredymcfly/Equipo-01-Proyecto-Bytes-Colaborativos)

**Status:** in development, release expected mid-October 2026

Team project built in a 2-week Scrum sprint: a fleet management backend with 9 microservices (vehicles, drivers, routes, maintenance, fuel, alerts and an executive dashboard).

**My contribution:** [describe here the services and areas you built]

**Key decisions**
- **Centralized auth:** the JWT is issued by `ms-auth` and validated by every domain service; calls between services (OpenFeign) are authenticated with an internal key.
- **Resilience:** Resilience4j on inter-service calls.
- **Versioned schema:** PostgreSQL with Flyway migrations.
- **Runs with no external APIs:** a seeder generates reproducible demo data (configurable seed and history length) on startup.

**Stack:** Java 17 · Spring Boot 3 · Spring Cloud Gateway · PostgreSQL · OpenFeign · Testcontainers · Docker Compose

---

## Stack

**Backend**

![My Skills](https://skillicons.dev/icons?i=java,spring,maven,mysql,postgresql,mongodb,docker,kafka)

**Frontend**

![My Skills](https://skillicons.dev/icons?i=html,css,ts,angular,tailwind)

<br/>

**Tools & Others**

![My Skills](https://skillicons.dev/icons?i=git,github,linux,aws,postman,idea,vscode,c)


---

## Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/luque-gabriel)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:luquegabrielcv@gmail.com)
