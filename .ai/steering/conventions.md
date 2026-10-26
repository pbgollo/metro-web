# Conventions — Metro Web

## Project layout

- Application code under `src/app/`
- Prefer **standalone** components (Angular 22 default style)
- Use the Angular CLI to scaffold components, services, guards, and routes
- Keep feature code grouped by domain feature when the app grows (e.g. `network/`, `tickets/`, `auth/`, `ops/`)

## Naming (Angular modern style)

- Prefer intent-based names over role suffixes where the skill guide applies (see `.agents/skills/angular-developer/references/naming-conventions.md`)
- Files and selectors should stay consistent within a feature
- Services: clear domain purpose (`TicketApi`, `AuthSession`, …)

## Components and templates

- Prefer signal inputs/outputs for new components
- Use control flow in templates: `@if`, `@for`, `@switch`
- Keep components focused: present UI and wire to services/resources; avoid fat “god” components
- After generating nontrivial UI code, run `ng build` and fix errors before continuing

## State and HTTP

- Prefer Signals for UI state
- Use `HttpClient` / `httpResource` for API access; centralize base URL and auth headers via interceptors or config
- Do not call RabbitMQ or talk to the database from the browser
- Map HTTP errors to user-visible messages; do not leak raw stack traces

## Auth and roles

- Store tokens securely according to the chosen SPA pattern (avoid XSS-prone storage mistakes)
- Use route guards for authenticated and role-restricted areas (`client` / passenger vs `master` / ops as defined by the API)
- UI hiding is not authorization — the API enforces permissions

## Forms

- New forms: prefer Signal Forms (Angular 22+)
- Validate on the client for UX; never rely on client validation alone

## Testing

- Unit tests with Vitest (`*.spec.ts`)
- Prefer testing behavior users care about over implementation details
- Add tests when introducing non-trivial services, guards, or pipes

## Styling

- Keep styles scoped to components unless a shared theme/tokens layer is introduced
- Prefer a single coherent visual system; avoid one-off layouts that fight the rest of the app

## Agent / skill guidance

- For Angular how-to details, follow `.agents/skills/angular-developer/SKILL.md` and its references
- Always check the installed Angular major before applying version-specific APIs
