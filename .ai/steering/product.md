# MetroIsJustABus — Product Vision (`metro-web`)

## Value Proposition

MetroIsJustABus is a distributed system that supports an urban bus network and passenger services. **`metro-web`** is the single web application used by passengers and operational staff.

## Role of This Application

- Present network, schedule, ticket, disruption, occupancy, and subscription information from `metro-core`.
- Let passengers manage accounts, tickets, subscriptions, and notification preferences.
- Let operational staff maintain network and schedules, manage ticket types, register disruptions, and consult validations and occupancy (via role-based UI).
- Consume **synchronous HTTP APIs** from `metro-core`. Do not implement domain rules in the frontend.

## What This Product / App Is NOT

- Not the domain source of truth (that is `metro-core`).
- Not the notification delivery service (that is `metro-notifications` / messaging infrastructure).
- Not a real payment gateway UI beyond simulated purchase flows if required.
- Not a native mobile app in the initial scope.
- Not a place to embed backend business logic, persistence, or cross-component orchestration.

## Audience (UI)

1. **Passengers**: consult the network, accounts, tickets, subscriptions.
2. **Operational staff**: maintenance and operational views behind elevated permissions.
3. **Engineering team**: Angular SPA integrated with the distributed system and SDD process.

## Core UI Capabilities (from Milestone 1)

1. Network consultation reflecting known disruptions.
2. Ticket purchase (simulated if needed), account tickets, and related passenger flows.
3. Accounts, subscriptions, and notification preferences.
4. Operational screens for network, schedules, ticket types, disruptions, validations, and occupancy.
5. Graceful UX when unrelated backend capabilities fail (e.g. notifications down should not block network browsing).

## Scope Notes for This Repository (`metro-web`)

This repository hosts only the **Angular web client**. Backend, messaging, and notification services live in `metro-core` (and supporting infrastructure).

Canonical project statement: `docs/spec/metro-is-just-a-bus.md` (PDF in the same folder prevails on conflict). Align product decisions with `metro-core` steering when both exist.

## Success Criteria (frontend)

- UI behavior stays traceable to the project statement and agreed requirements.
- No domain logic duplicated in the client beyond presentation and UX.
- Auth and roles drive what the UI shows; the server remains the authority.
