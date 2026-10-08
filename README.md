<h1 align="center">Gabriel Luque</h1>

<p align="center">
  <strong>Junior Backend Developer · Java &amp; Spring Boot</strong>
</p>

I build Java backends: secure REST APIs, event-driven microservices and real-time services, backed by tests, static analysis and a setup anyone can run with Docker Compose.

<p align="center">
  <a href="https://luquegabriel01.github.io"><img src="https://img.shields.io/badge/Portfolio-4B5563?style=for-the-badge&logo=githubpages&logoColor=white" alt="Portfolio"></a>
  <a href="https://www.linkedin.com/in/luque-gabriel/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:luquegabrielcv@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

## About Me

- **Backend:** REST APIs with Java and Spring Boot, JWT and OAuth 2.0 authentication/authorization, on PostgreSQL, MySQL and MongoDB
- **Quality:** unit tests with JUnit 5 and Mockito, static analysis and GitHub Actions workflows
- **Delivery:** containerized with Docker and Docker Compose
- **Also:** Angular/TypeScript on the frontend side, plus Node.js and .NET/C#

## Projects

### [HotelApp — Hotel Reservation Platform](https://github.com/LuqueGabriel01/HotelReservationApp)

> Hotel booking system split into 7 Spring Boot microservices behind a single API gateway. Guests search availability and book or cancel rooms with email confirmations; admins manage hotels, rooms, pricing and photos from a separate panel.

[![Backend repo](https://img.shields.io/badge/Backend-repo-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/LuqueGabriel01/HotelReservationApp)
[![Frontend repo](https://img.shields.io/badge/Frontend-repo-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SihaoCheng123/InntryFront)

**Key decisions**
- **Single entry point:** JWT validation, routing and rate limiting live in the gateway, in one place.
- **Database per service:** each service owns its PostgreSQL database. Trade-off: no cross-service joins.
- **Events for notifications:** booking confirmations and cancellations go through Kafka to a notification service (email via SMTP), so the booking flow doesn't depend on email delivery.
- **AI as an isolated service:** the agent service uses Google Gemini for room recommendations and a support chat, with session state in Redis, separate from the booking core.

**Delivery:** Angular client consuming the gateway · GitHub Actions checks code quality and Docker builds · **Also:** Spring Security + JWT

![Java, Spring, Maven, PostgreSQL, Kafka, Redis, Docker, Angular](https://skillicons.dev/icons?i=java,spring,maven,postgresql,kafka,redis,docker,angular)

---

### [menuFlow — Restaurant Management API](https://github.com/LuqueGabriel01/menuFlow)

> REST API that takes a restaurant from table to bill: QR-code tables, dining sessions, a multi-language menu with allergens, kitchen workflow and invoicing. Built to practice a complete API design: domain modeling, security, testing and Docker deployment.

[![Code repo](https://img.shields.io/badge/Code-repo-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/LuqueGabriel01/menuFlow)
![Next: demo frontend](https://img.shields.io/badge/Next-demo%20frontend-6B7280?style=flat-square)

**Key decisions**
- **Two login paths:** staff sign in with credentials and get their real role; customers scan the table's QR and get a limited `ROLE_USER` token, with no account needed. A table can only order while its session is open.
- **Stateless JWT with role-based access** (`ADMIN`, `CASHIER`, `CHEF`, `KITCHEN`, `USER`) enforced per endpoint.
- **Explicit order flow** (`PENDING → IN_PROGRESS → READY → SERVED → CLOSED`), with the kitchen queue separated from the general active-orders view.
- **Consistent API contract:** every response uses the same envelope, and errors return a structured body with validation details.
- **No secrets in the repo:** configuration references environment variables and `.env` is never committed.

**Proof:** JUnit 5 + Mockito (service tests and `@WebMvcTest` controller tests) · GitHub Actions on every push/PR (tests against MySQL, Docker image build) · per-module docs and ER diagram · Swagger UI · **Also:** Spring Data JPA, Spring Security + JWT

![Java, Spring, Maven, MySQL, Docker](https://skillicons.dev/icons?i=java,spring,maven,mysql,docker)

---

### [Spring Boot Chat Backend — Real-Time Chat](https://github.com/LuqueGabriel01/spring-boot-chat-backend)

> Frontend-agnostic chat backend: live broadcast, typing indicator and recent message history when a client joins.

[![Code repo](https://img.shields.io/badge/Code-repo-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/LuqueGabriel01/spring-boot-chat-backend)

**Key decisions**
- **Documented messaging contract:** fixed destinations and topics with typed payloads, plus a client usage example in the README.
- **Private history channel:** history is published on a per-client topic, and client ids are validated against a strict pattern.
- **Server-side truth:** the server sets each message's id and timestamp and persists only real messages, not join events.
- **Configurable by environment:** allowed origins and history size.

**Proof:** JUnit 5 + Mockito · Docker Compose with persistent MongoDB · health check via Spring Actuator · **Also:** WebSocket (STOMP + SockJS)

![Java, Spring, Maven, MongoDB, Docker](https://skillicons.dev/icons?i=java,spring,maven,mongodb,docker)

---

### [FleetControl — Fleet Management Platform](https://github.com/fredymcfly/Equipo-01-Proyecto-Bytes-Colaborativos)

> Team project built in a 2-week Scrum sprint: a fleet management backend with 9 microservices (vehicles, drivers, routes, maintenance, fuel, alerts and an executive dashboard).

[![Code repo](https://img.shields.io/badge/Code-repo-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/fredymcfly/Equipo-01-Proyecto-Bytes-Colaborativos)
![Status: in development, release expected mid-October 2026](https://img.shields.io/badge/Status-In%20development-F59E0B?style=flat-square)

**My contribution:** [describe here the services and areas you built]

**Key decisions**
- **Centralized auth:** the JWT is issued by `ms-auth` and validated by every domain service; calls between services (OpenFeign) are authenticated with an internal key.
- **Resilience:** Resilience4j on inter-service calls.
- **Versioned schema:** PostgreSQL with Flyway migrations.
- **Runs with no external APIs:** a seeder generates reproducible demo data (configurable seed and history length) on startup.

**Also:** Spring Cloud Gateway · OpenFeign · Testcontainers · release expected mid-October 2026

![Java, Spring, PostgreSQL, Docker](https://skillicons.dev/icons?i=java,spring,postgresql,docker)

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
