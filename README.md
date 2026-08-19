# Hi there 👋 I'm Gabriel

Junior Backend Developer specializing in Java & Spring Boot.

[LinkedIn](https://linkedin.com/in/luque-gabriel) · [luquegabrielcv@gmail.com](mailto:luquegabrielcv@gmail.com)


## About Me

I build REST APIs with Java and Spring Boot, with authentication/authorization via JWT and OAuth 2.0, on PostgreSQL and MongoDB. I write unit tests with JUnit 5 and Mockito, containerize with Docker, and follow standard GitHub workflows. I've also worked with Node.js, .NET/C#, and Angular/TypeScript on the frontend side.

---

## Featured Project

**[HotelApp — Hotel Reservation Platform](https://github.com/LuqueGabriel01/HotelReservationApp)**

A hotel reservation system built as 7 independent Spring Boot microservices behind a single API gateway. Guests search availability, book and cancel rooms with email confirmations at each step; admins manage hotels, rooms, pricing and photos from a separate panel.

- Architecture: ms-gateway (JWT validation, routing, rate limiting) · ms-auth · ms-catalog · ms-booking · ms-availability · ms-notification · ms-agent
- Stack: Java 21, Spring Boot 4, Spring Security + JWT, PostgreSQL (database-per-service), Kafka, Redis, Docker Compose
- AI feature: ms-agent uses Google Gemini for room recommendations and a support chat, backed by Redis session state
- Event-driven: booking confirmations/cancellations flow through Kafka to a dedicated notification service (email via SMTP)
- Frontend: Angular client consuming the gateway
- CI/CD: automated code-quality and Docker build checks via GitHub Actions

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
