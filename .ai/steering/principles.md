# Principles — MetroIsJustABus (`metro-web`)

1. This app is a **client only**. Domain rules, persistence, and cross-service orchestration belong in backends — not in Angular services that reinvent the core.

2. **`metro-core` is the source of truth.** The UI displays and submits; it does not redefine ticket validity, schedules, or occupancy.

3. **Authorize on the server.** Guards and hidden menus improve UX; they are not security. Always assume the API will reject unauthorized calls.

4. **Fail partially in the UX.** If notifications or another unrelated capability is down, network consultation and other available features must still work.

5. **Do not invent UI features** that contradict `docs/spec/metro-is-just-a-bus.md` or steering. If scope is unclear, it is out of scope until decided and documented.

6. Prefer **signals-first, standalone, CLI-scaffolded** patterns consistent with Angular 22 and the project Angular skill — not a parallel legacy style.

7. Keep **passenger and ops** in one app, separated by routes and roles — not by duplicating business logic in two frontends.

8. Treat API contracts as explicit: typed models, clear error states, no silent swallowing of failed requests that leave the UI inconsistent.

9. Accessibility and clarity matter for a public transit UI: meaningful labels, keyboard use, and readable empty/error states.

10. Align with `metro-core` steering when product or contract decisions span both repos; update both specs if the shared statement changes.
