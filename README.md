# SDV-CVI-OTA-Core

**Connected Vehicle Intelligence & OTA Platform**

An evolving software platform for connected-vehicle telemetry, vehicle health
monitoring, software-update lifecycle management, and fleet intelligence.

The platform is designed around a modular Java/Spring Boot backend, with
supporting vehicle simulation, messaging, a web dashboard, an Android companion
application, a Linux OTA agent, and an advisory AI service introduced
incrementally as the architecture evolves.

## Project Status

- **Current milestone:** v0.0.1 — Project Foundation
- **Architecture:** Modular monolith initially
- **Deployment scope:** Local development and simulated vehicles

This project is under active development. Features, release status, and
operational capabilities will be documented according to verified
implementation and test evidence.

## Objectives

- Manage registered vehicles and their software inventory.
- Ingest and persist simulated vehicle telemetry.
- Process vehicle events and identify health conditions.
- Manage OTA packages, campaigns, eligibility, and update lifecycle state.
- Provide secure APIs and fleet visibility interfaces.
- Evaluate vehicle-health anomalies through an advisory AI service.
- Demonstrate automated testing, reproducible builds, and CI/CD practices.

## Architecture Principles

1. Start with a modular monolith; introduce distributed services only when
   justified by concrete requirements.
2. Use PostgreSQL as the initial persistent source of truth.
3. Use MQTT for vehicle messaging and introduce Kafka for asynchronous event
   processing when required.
4. Store OTA package binaries separately from relational metadata.
5. Separate authentication, authorization, auditability, and package
   authenticity verification from ordinary application business logic.
6. Keep AI-generated findings advisory. AI must not authorize OTA deployments
   or control vehicle functions.
7. Treat vehicle devices and OTA operations as simulated until explicitly
   documented otherwise.
8. Add automated tests, observability, failure handling, and security controls
   alongside the features they protect.
9. Document limitations honestly; a prototype does not imply OEM certification
   or compliance with automotive standards.

## Technology Direction

| Area | Planned technology |
|---|---|
| Backend | Java, Spring Boot, Maven |
| Database | PostgreSQL, Flyway |
| Messaging | Eclipse Mosquitto MQTT; Kafka where justified |
| Web application | React, TypeScript, Vite |
| Android application | Kotlin, Jetpack Compose |
| Linux OTA agent | C++, CMake, GoogleTest |
| AI service | Python, FastAPI, scikit-learn |
| Local infrastructure | Docker, Docker Compose |
| Quality and delivery | JUnit, Mockito, Testcontainers, GitHub Actions |

Specific versions and dependencies will be pinned and verified as components
are introduced.

## Local Development Ports

The initial host-port assignments are documented in
[`docs/development/local-environment.md`](docs/development/local-environment.md).
Ports must be checked before starting new services.

## Documentation

- [Architecture overview](docs/architecture/architecture-overview.md)
- [Local development environment](docs/development/local-environment.md)
- [Development workflow](docs/development/development-workflow.md)
- [Architecture decision records](docs/decisions/)

## Releases

Releases will be tagged only after their documented acceptance criteria,
automated checks, and required demonstrations have passed.

The initial target is `v0.0.1`, the project foundation. Vehicle management is
the next functional milestone, targeted for `v0.1.0`.
