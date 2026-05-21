# 02. Mobile Moving Parts

Mobile architecture sits between user experience, device constraints, platform rules, and backend systems.

This module lists the moving parts you should naturally consider in a mobile system design interview.

## Client Application Layers

Typical Android layers:

- UI layer: screens, navigation, rendering, accessibility, input handling.
- Presentation layer: view models, state holders, reducers, UI state mapping.
- Domain layer: business rules, use cases, validation, orchestration.
- Data layer: repositories, local database, network sources, cache policy.
- Platform layer: permissions, notifications, background work, sensors, storage, media, location.
- Infrastructure layer: logging, analytics, experimentation, dependency injection, config, crash reporting.

Common Android tools:

- Kotlin and coroutines for asynchronous work.
- Jetpack Compose or Views for UI.
- ViewModel for lifecycle-aware state.
- Room or SQLDelight for local storage.
- WorkManager for deferrable background work.
- Retrofit/Ktor/OkHttp for networking.
- DataStore or EncryptedSharedPreferences for lightweight preferences.
- Paging for incremental list loading.

## App Lifecycle

Mobile systems must handle lifecycle transitions:

- Cold start.
- Warm start.
- Foreground to background.
- Process death.
- Configuration changes.
- OS-initiated background restrictions.
- App upgrade.
- Login/logout/account switch.

Design implication: important user state should not live only in memory.

## Networking

Mobile networks are unreliable by default.

Consider:

- Timeouts.
- Retries with backoff.
- Idempotency keys.
- Request cancellation.
- Pagination.
- Partial responses.
- Compression.
- Network reachability.
- Offline queues.
- Captive portals.
- Metered networks.

Avoid assuming that request order equals server processing order.

## Local Storage

Local persistence supports speed, offline behavior, and resilience.

Common storage categories:

- Durable app data: Room/SQLite.
- Preferences and flags: DataStore.
- Secure secrets: Android Keystore-backed storage.
- Media/files: app-specific storage or scoped storage.
- Caches: bounded and evictable.

Key questions:

- What data is source of truth?
- What data can be stale?
- What data must be encrypted?
- What data must be removed on logout?
- What data survives app reinstall?

## Sync

Sync is one of the most important mobile design topics.

Patterns:

- Pull-to-refresh.
- Periodic background sync.
- Push-triggered sync.
- Read-through cache.
- Write-through cache.
- Offline write queue.
- Delta sync.
- Full resync.

Hard questions:

- How do we detect changes?
- How do we handle conflicts?
- What is the ordering guarantee?
- How do we avoid duplicate writes?
- How do we recover from a corrupted local state?

## Push Notifications

Push is not guaranteed delivery.

Design for:

- Token registration and refresh.
- Notification preferences.
- Topic or user targeting.
- Deep links.
- Permission prompts.
- Collapse keys.
- Silent push limitations.
- Backend fallback when delivery fails.
- Observability for sent, delivered, opened, and acted-on notifications.

## Media

Media-heavy apps need special treatment.

Consider:

- Upload resumability.
- Compression and transcoding.
- Thumbnail generation.
- CDN delivery.
- Progressive loading.
- Memory pressure.
- Disk cache size.
- Background upload limits.
- EXIF stripping for privacy.

## Authentication

Mobile auth is more than login.

Consider:

- Access tokens and refresh tokens.
- Token rotation.
- Secure storage.
- Biometric unlock.
- Device binding.
- Account recovery.
- Logout and remote session revocation.
- Multi-account behavior.
- Step-up auth for sensitive actions.

## Observability

Mobile observability must cover client-side behavior.

Track:

- Crash-free sessions.
- ANR rate.
- App startup time.
- Screen render time.
- API latency from client perspective.
- Network error rate.
- Battery-sensitive background work.
- Local database errors.
- Sync queue depth.
- Feature adoption.
- Funnel conversion.

## Release and Operations

Mobile releases are slow to fully propagate.

You need:

- Feature flags.
- Remote config.
- Staged rollout.
- Kill switches.
- Backward-compatible APIs.
- Version-aware backend behavior.
- Forced upgrade policy for critical issues.
- Monitoring by app version, OS version, device class, country, and network type.

