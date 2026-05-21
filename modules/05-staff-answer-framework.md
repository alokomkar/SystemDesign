# 05. Staff-Level Design Answer Framework

Use this framework to answer mobile system design questions in interviews.

## 1. Clarify the Problem

Start with scope.

Good prompts:

- Who are the users?
- What platforms are in scope?
- What is the primary user journey?
- Is this consumer, enterprise, regulated, or internal?
- Are we designing only the mobile client or the end-to-end system?
- Are offline writes required?
- Is real-time behavior required?

## 2. Define Requirements

Separate requirements.

Functional:

- User actions.
- Data operations.
- Notifications.
- Offline behavior.
- Cross-device behavior.
- Admin/support behavior.

Non-functional:

- Performance.
- Reliability.
- Security.
- Privacy.
- Scalability.
- Accessibility.
- Battery.
- Observability.
- Release safety.

## 3. Establish Constraints and Assumptions

Examples:

- Android first, iOS later.
- Millions of monthly active users.
- Users may be offline for hours.
- Backend APIs already exist.
- Must support app versions up to 12 months old.
- P95 screen load under 1 second on cached data.
- Sensitive data must be encrypted locally.

Say assumptions out loud and make them easy to revise.

## 4. Draw the High-Level Architecture

Include:

- Mobile app.
- API gateway or BFF.
- Domain services.
- Database.
- Cache.
- Object storage or CDN.
- Push service.
- Analytics and observability.
- Feature flag or remote config service.

For mobile, also include:

- Local database.
- In-memory state.
- Background worker.
- Sync engine.
- Secure storage.
- Notification handler.

## 5. Define Data Model and API Shape

Cover:

- Core entities.
- Entity ownership.
- IDs.
- Timestamps and versions.
- Pagination.
- Delta tokens.
- Idempotency keys.
- Error model.
- Backward compatibility.

Staff-level detail: explain which fields are server-authoritative and which are client-derived.

## 6. Design Client State

Clarify:

- What is cached?
- What is persisted?
- What is kept only in memory?
- What is the source of truth?
- How does UI observe state?
- How are pending writes represented?
- How does logout clear state?

Example state categories:

- Server-confirmed data.
- Locally pending data.
- Failed-but-retryable data.
- Draft data.
- Derived UI state.

## 7. Handle Offline, Sync, and Conflict Resolution

Discuss:

- Read cache policy.
- Write queue.
- Retry policy.
- Idempotency.
- Conflict detection.
- Conflict resolution.
- Resync strategy.
- Corruption recovery.

Conflict strategies:

- Last-write-wins.
- Server-wins.
- Client-wins.
- Field-level merge.
- Manual user resolution.
- Domain-specific rules.

Pick the simplest strategy that satisfies the product requirement.

## 8. Address Failure Modes

Examples:

- Backend unavailable.
- Push delayed or dropped.
- App killed mid-operation.
- User logs out with pending writes.
- Token expires during sync.
- Duplicate request reaches backend.
- Old client calls new API.
- Local database migration fails.

Explain mitigation and user experience.

## 9. Cover Security and Privacy

Mention:

- Auth flow.
- Token storage.
- Encryption.
- Permission prompts.
- Sensitive logs.
- Data deletion.
- API authorization.
- Abuse prevention.

Reminder: the mobile client is not trusted. Enforce important rules on the server.

## 10. Cover Observability and Rollout

Include:

- Metrics.
- Logs.
- Traces.
- Crash reporting.
- Feature flags.
- Staged rollout.
- Kill switches.
- Dashboards by app version.
- Alerts.

This is a strong staff-level differentiator.

## 11. Close With Tradeoffs

Summarize:

- What you optimized for.
- What you deliberately did not solve.
- What would change at higher scale.
- What you would build next.

Good endings sound like engineering judgment, not a list of buzzwords.

## Interview Answer Skeleton

Use this structure:

```text
I will first clarify the scope, then separate functional and non-functional requirements.
After that I will propose an end-to-end architecture, with a deeper focus on the mobile client, sync, failure handling, and rollout.

Assumptions:
- ...

Functional requirements:
- ...

Non-functional requirements:
- ...

High-level architecture:
- ...

Client architecture:
- ...

Data and APIs:
- ...

Offline and sync:
- ...

Failure modes:
- ...

Security and privacy:
- ...

Observability and rollout:
- ...

Tradeoffs:
- ...
```

