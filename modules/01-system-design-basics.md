# 01. System Design Basics

System design is the process of turning an ambiguous product goal into a technical architecture that satisfies real constraints.

At senior and staff levels, the goal is not to produce one perfect diagram. The goal is to show structured reasoning, good judgment, and awareness of failure modes.

## Core Questions

Every design conversation should answer:

- What are we building?
- Who uses it?
- What must it do?
- What quality bars must it meet?
- What are the main constraints?
- What can fail?
- What tradeoffs are acceptable?
- How will we evolve it over time?

## Functional vs Non-Functional Requirements

Functional requirements describe behavior.

Examples:

- Users can send a message.
- Users can view order status.
- Users can upload photos.
- Users can search nearby restaurants.
- Users can log in using biometrics.

Non-functional requirements describe quality attributes.

Examples:

- App launch must be fast.
- Data must be encrypted at rest.
- The system must work offline.
- The app must consume minimal battery.
- Push notifications must arrive reliably.
- The system must tolerate backend outages.

Good design answers separate these early because they drive different architecture choices.

## Common System Components

Most mobile systems include:

- Mobile app: UI, navigation, local state, business logic, persistence, networking, background work.
- Backend services: domain APIs, orchestration, authorization, validation, business rules.
- Data stores: relational databases, document stores, object storage, caches, search indexes.
- Event systems: queues, streams, pub/sub, analytics events, notification events.
- Delivery infrastructure: CDN, image/video resizing, edge caching.
- Identity and auth: login, session management, tokens, device trust, account recovery.
- Observability: logs, metrics, traces, crash reports, client telemetry.
- Release systems: CI/CD, feature flags, staged rollout, app store releases, kill switches.

## Design Process

Use this flow:

1. Clarify scope.
2. Identify users and critical journeys.
3. Define requirements.
4. Estimate scale where relevant.
5. Propose high-level architecture.
6. Deep dive into the hardest parts.
7. Discuss failure modes.
8. Discuss tradeoffs.
9. Cover rollout, monitoring, and evolution.

## Mobile-Specific Thinking

For mobile, always ask:

- What happens with no network?
- What happens with slow network?
- What happens when the app is backgrounded or killed?
- What happens across app upgrades?
- What happens on old OS versions or low-memory devices?
- What data is safe to persist locally?
- What can be changed server-side without an app update?
- What needs a kill switch?

## Senior-Level Signal

A junior answer often describes only the happy path.

A senior answer usually includes component boundaries, APIs, and data flow.

Senior-level signal includes:

- Clear product scope.
- Screen-level flows.
- Client architecture.
- Data model and API contracts.
- Offline and error handling.
- Performance and testing considerations.

## Staff-Level Signal

A staff answer adds:

- Product and operational tradeoffs.
- Failure recovery.
- Migration strategy.
- Observability.
- Release safety.
- Cross-team ownership.
- Long-term maintainability.
