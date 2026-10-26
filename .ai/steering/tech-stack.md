# Tech Stack — MetroIsJustABus (`metro-web`)

## System position

| Component | Role | Technology |
| --- | --- | --- |
| `metro-web` | Single web app (passengers + ops) | **Angular 22** (this repo) |
| `metro-core` | Domain APIs + source of truth | C# / .NET 10 |
| `metro-notifications` | Notification delivery | Separate backend service |
| RabbitMQ | Async messaging | Infrastructure (not used directly by the SPA) |

The SPA talks to **`metro-core` over HTTP/JSON**. It does not connect to RabbitMQ or PostgreSQL.

## This repository (`metro-web`)

### Framework
- **Angular** `^22.2` (standalone components, modern CLI)
- **TypeScript** `~6.0`
- **RxJS** `~7.8`
- **Build:** `@angular/build` / Angular CLI `^22.2`
- **Package manager:** npm

**Why Angular:** Course/team SPA choice; strong routing, DI, and typed HTTP for a multi-role transit UI.

### UI and state (preferred direction)
- **Reactivity:** Angular **Signals** (`signal`, `computed`, `linkedSignal`, `resource` / `httpResource` where appropriate)
- **Forms:** Prefer **Signal Forms** for new forms (Angular 22+); match existing patterns if already introduced otherwise
- **HTTP:** `provideHttpClient`, `HttpClient`, interceptors; prefer `httpResource` for read-heavy signal-based data when it fits
- **Routing:** Angular Router with guards for authenticated / role-based areas
- **Testing:** Vitest (`ng test`), jsdom
- **Formatting:** Prettier

**Why signals-first:** Aligns with current Angular defaults and the project Angular developer skill guidance; less boilerplate than heavy RxJS-only UI state for new screens.

### Backend contract
- Consumes `metro-core` REST APIs under `api/v1/...`
- Auth via JWT (access token; refresh flow as implemented by the API)
- Treat API `ApiResult`-style payloads and HTTP status codes as the contract; map them to UI states (loading / error / empty / success)

### Packaging (expected)
- Local: `ng serve` / `ng build`
- Containerization and CI will follow the project DevOps plan; keep the app buildable as a static SPA served behind a reverse proxy or similar

## Versions (majors — this repo)

Angular 22 · TypeScript 6 · RxJS 7 · Vitest 5 · Prettier 3

Exact versions live in `package.json` and change; keep the **reasons** above accurate when bumping majors.

## Related repos

- **`metro-core`:** APIs, domain, planned notifications host — see that repo’s `.ai/steering/`
- Canonical statement: `docs/spec/metro-is-just-a-bus.md`
