# Architecture Overview

## Current Stage

The initial release establishes repository conventions and architecture
direction. No vehicle-management, telemetry, OTA, or AI functionality is
claimed until implemented and tested.

## Architectural Approach

Begin with a modular monolith. Keep domain responsibilities separated in code
without introducing independently deployed backend services prematurely.

Initial backend domain boundaries:

- Vehicle management
- Telemetry ingestion and normalization
- Vehicle health and diagnostics
- OTA package and campaign management
- Shared security, persistence, and observability capabilities

These are planned boundaries, not a claim that all modules already exist.

## Data and Messaging

- PostgreSQL is the initial source of truth for persistent application data.
- Flyway manages database schema evolution.
- MQTT is the planned vehicle-message transport.
- Kafka will be introduced when durable asynchronous processing, replay, or
  independent consumers justify its operational cost.
- OTA binaries will be stored separately from relational metadata.

## OTA Trust and Safety

Package integrity checks alone do not establish publisher authenticity.
The OTA design must specify trusted signing keys, signature verification,
authorization, compatibility checks, and safe update-state transitions.

Initial device interactions are simulated. The platform does not claim to
flash production ECUs or control a physical vehicle.

## AI Boundary

The planned AI service produces advisory findings and measurable evaluations.
It does not grant deployment permission, replace deterministic safety checks,
or directly control vehicle functions.

## Security and Standards

Security requirements are introduced throughout development, not deferred to a
single final phase. Automotive standards and projects may inform design
decisions, but compliance will not be claimed without supporting evidence.
