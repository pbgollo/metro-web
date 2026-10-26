# Metro Web

Web application for **MetroIsJustABus** (passengers and operational staff). Architecture notes and local commands are in `README.md`.

## What to read when

- **Default (build / design / UI code):** read [`.ai/steering/`](.ai/steering/) first. Do not invent requirements that contradict it.
- **Milestone, delivery, grading, or “are we aligned with the statement?”:** read [`docs/spec/metro-is-just-a-bus.md`](docs/spec/metro-is-just-a-bus.md) (milestones, evaluation criteria, full constraints). If it conflicts with the PDF in the same folder, the PDF prevails.
- **Passenger/ops flows or API contracts while coding:** steering + the Technical Description of the statement as needed. Skip deadlines and grading unless the user asks about a delivery.

## Steering (SDD)

Permanent project context:
- [`.ai/steering/product.md`](.ai/steering/product.md) — product and UI scope
- [`.ai/steering/tech-stack.md`](.ai/steering/tech-stack.md) — stack and rationale
- [`.ai/steering/conventions.md`](.ai/steering/conventions.md) — Angular and UI patterns
- [`.ai/steering/principles.md`](.ai/steering/principles.md) — non-negotiable rules

## Specification

Full course statement (v1.0, 2026-09-29): [`docs/spec/metro-is-just-a-bus.md`](docs/spec/metro-is-just-a-bus.md). Identical copy in `metro-core/docs/spec/`; when updating, update both.

This application is one component of the distributed system; notifications and other supporting services live outside this repository.
