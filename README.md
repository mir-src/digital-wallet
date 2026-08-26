# Enterprise Digital Wallet RESTful API

A high-performance, transactional financial ledger engine built with **Java 21** and **Spring Boot 3**. Designed to handle secure user account management, concurrent currency transfers, and real-time exchange rate integrations.

---

## Technical Highlights

* **Thread-Safe Transfers:** Uses pessimistic database locking (`PESSIMISTIC_WRITE`) and `@Transactional` boundaries to eliminate race conditions and double-spending.
* **Schema Versioning:** Managed via **Flyway** migration scripts rather than dynamic ORM generation.
* **Resilient Integrations:** Fetches live rates using Spring's `RestClient` with automatic fallbacks and **Redis** caching.
* **Stateless Security:** Secured with **Spring Security**, **JWT** tokens, and **BCrypt** password hashing.
* **Fully Containerized:** One-command local development setup using **Docker Compose**.

---

## Tech Stack

* **Language & Framework:** Java 21, Spring Boot 3 (Web, JPA, Security)
* **Databases & Cache:** PostgreSQL, Redis, Flyway
* **DevOps & Testing:** Docker, Docker Compose, JUnit 5, Mockito, Testcontainers
* **Documentation:** OpenAPI 3.0 / Swagger UI

---

## Core API Endpoints

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/v1/auth/register` | Register a new user |
| `POST` | `/api/v1/auth/login` | Authenticate and retrieve JWT token |
| `GET` | `/api/v1/accounts` | Fetch wallet balance for authenticated user |
| `POST` | `/api/v1/accounts` | Open a new currency wallet |
| `POST` | `/api/v1/transfers` | Initiate an atomic ledger transfer |

---

## Quick Start

### Run with Docker

```bash
# Clone the repository
git clone [https://github.com/your-username/digital-wallet-api.git](https://github.com/your-username/digital-wallet-api.git)
cd digital-wallet-api

# Start Postgres, Redis, and Application API
docker compose up --build -d