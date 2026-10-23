# Local Development Environment

## Host-Port Assignments

These are the proposed host ports for this project. They were available during
the initial check on 2026-10-23; availability must be rechecked when a service
is introduced.

| Component | Host port | Planned use |
|---|---:|---|
| Spring Boot API | 18081 | REST API |
| PostgreSQL | 15439 | Local database access |
| MQTT | 11883 | Vehicle messaging |
| MQTT WebSockets | 19003 | Optional browser-compatible messaging |
| Kafka | 19092 | Event processing |
| MinIO API | 19000 | OTA object storage |
| MinIO console | 19001 | Local object-storage console |
| React dashboard | 15173 | Web development server |
| Python AI API | 18082 | AI service API |

## Networking Rules

- Do not stop or reconfigure unrelated project services to free a port.
- Check port availability before enabling a component.
- Prefer private Docker-network communication between containers.
- Publish host ports only when local access is required.
- Bind development-only services to loopback where practical.
- Keep credentials and environment-specific secrets out of version control.
- Container-internal ports may differ from host-published ports.

## Resource Awareness

Start only the services needed for the current milestone. Avoid running the
entire planned stack on the development laptop simultaneously unless required.
