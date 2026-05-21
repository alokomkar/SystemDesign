# 04. Non-Functional Requirements

Non-functional requirements define the quality bar of the system.

For staff-level mobile interviews, this is where you show maturity. Many failures in mobile systems happen because teams under-design reliability, performance, privacy, rollout, or observability.

## Performance

Key mobile performance dimensions:

- Cold start time.
- Warm start time.
- Screen render latency.
- Scroll smoothness.
- API latency.
- Image loading speed.
- Local database query time.
- Memory usage.
- App size.
- Battery impact.

Design tactics:

- Lazy initialization.
- Local caching.
- Pagination.
- Image resizing and caching.
- Avoiding main-thread blocking.
- Background prefetch when appropriate.
- Compact API payloads.
- Startup-critical path reduction.

## Reliability

Mobile reliability includes client and backend failure handling.

Consider:

- Network failures.
- Backend timeouts.
- Partial writes.
- Duplicate requests.
- App crashes.
- Process death during a write.
- Corrupted local cache.
- Push delivery failure.
- Clock skew.
- Old app versions.

Design tactics:

- Idempotency keys.
- Retry with exponential backoff and jitter.
- Offline queue with durable persistence.
- Server-side deduplication.
- Local state reconciliation.
- Health checks and circuit breakers.
- Kill switches for broken features.

## Availability

Availability is not only server uptime.

For users, availability means the app can still provide useful behavior.

Examples:

- Cached feed works during outage.
- Draft messages are preserved.
- Payment status can be recovered.
- Upload resumes after network returns.
- Critical flows degrade gracefully.

## Scalability

Mobile scale has several dimensions:

- Users.
- Devices per user.
- API requests per active session.
- Push volume.
- Media upload/download volume.
- Analytics event volume.
- App versions in the wild.
- Geographic distribution.

Common tactics:

- CDN for media.
- Backend pagination and filtering.
- Delta sync instead of full sync.
- Batch APIs where useful.
- Event ingestion pipelines.
- Rate limiting.
- Version-aware API contracts.

## Consistency

Mobile systems often trade strict consistency for availability and responsiveness.

Common models:

- Strong consistency for payments, auth, inventory, and sensitive state.
- Eventual consistency for feeds, likes, read receipts, and cached profile data.
- Local optimistic updates for responsiveness.
- Server reconciliation for correctness.

Key questions:

- Which state must never be wrong?
- Which state can be temporarily stale?
- How is pending state represented?
- How are conflicts shown or resolved?

## Security

Mobile security requirements include:

- TLS for network communication.
- Certificate pinning where justified.
- Secure token storage.
- Token expiration and rotation.
- Least-privilege API scopes.
- App integrity checks where appropriate.
- Root/jailbreak risk handling for sensitive apps.
- Protection against replay and duplicate requests.
- Sensitive data redaction in logs.

Avoid storing secrets in the app binary. The client cannot be fully trusted.

## Privacy

Privacy is a first-class architectural concern.

Consider:

- Data minimization.
- Runtime permissions.
- Purpose limitation.
- Consent.
- Data deletion.
- Location precision.
- Contact/photo access.
- Analytics opt-out.
- PII redaction.
- Regional compliance.

Mobile-specific privacy issue: device data can be more personal than backend data because it may include location, contacts, media, sensors, or nearby devices.

## Battery and Resource Usage

Battery is part of user trust.

Watch:

- Background location.
- Long-running foreground services.
- Wake locks.
- Frequent polling.
- Large uploads on cellular.
- Excessive analytics events.
- Inefficient sync loops.

Prefer event-driven updates, batching, constraints-based work, and adaptive polling.

## Accessibility

Mobile systems should support:

- Screen readers.
- Dynamic font size.
- Color contrast.
- Touch target sizing.
- Reduced motion.
- Keyboard and switch access where relevant.
- Content descriptions.

Accessibility requirements can affect component choices and testing strategy.

## Observability

Mobile observability should be segmented by:

- App version.
- OS version.
- Device model.
- Locale.
- Country.
- Network type.
- Experiment variant.
- Feature flag state.

Useful signals:

- Crash-free users.
- ANR rate.
- Startup time percentiles.
- API failure rate.
- Sync failure rate.
- Push open rate.
- Local database error rate.
- Battery-related background work failures.

## Maintainability

Staff-level design should consider team scale.

Ask:

- Which teams own which services?
- How are API contracts versioned?
- How do mobile and backend teams coordinate releases?
- Can the design support multiple product surfaces?
- Is the architecture testable?
- How do we migrate from old behavior to new behavior?

## Non-Functional Requirements Checklist

- Performance.
- Reliability.
- Availability.
- Scalability.
- Consistency.
- Security.
- Privacy.
- Battery.
- Accessibility.
- Observability.
- Maintainability.
- Release safety.
- Backward compatibility.
- Cost.

