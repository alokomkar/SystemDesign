# Mobile System Design for Android Staff Engineers

This repository is a practical tutorial for preparing for staff-level Android and mobile system design interviews.

The focus is not only "how do I design an app screen?" It is how to reason about a complete mobile system: product requirements, client architecture, backend contracts, sync, offline behavior, performance, reliability, security, observability, rollout, and long-term maintainability.

## Who This Is For

- Android engineers preparing for senior staff or staff engineer interviews.
- Mobile leads who want a repeatable system design framework.
- Backend or full-stack engineers who want to understand mobile-specific constraints.
- Engineers designing mobile experiences that must work under real-world device, network, privacy, and scale constraints.

## What Makes Mobile System Design Different

Mobile clients run in an environment the system does not fully control.

- Devices vary by OS version, memory, CPU, battery, storage, screen size, OEM behavior, and background execution limits.
- Networks are intermittent, slow, metered, high-latency, or captive.
- Users expect fast startup, smooth interaction, offline continuity, low battery usage, and safe data handling.
- App releases are slow compared with backend deploys because users may not update immediately.
- Client bugs can be expensive because rollback is harder than server rollback.
- Privacy, platform policy, and permission models are part of the architecture.

Staff-level design answers should show that you can operate across this full system, not just within one codebase.

## Tutorial Roadmap

1. [System Design Basics](modules/01-system-design-basics.md)
2. [Mobile Moving Parts](modules/02-mobile-moving-parts.md)
3. [Functional Requirements](modules/03-functional-requirements.md)
4. [Non-Functional Requirements](modules/04-non-functional-requirements.md)
5. [Staff-Level Design Answer Framework](modules/05-staff-answer-framework.md)
6. [Example: Offline-First Notes App](examples/offline-first-notes.md)
7. [Design Template](templates/mobile-system-design-template.md)

## The Staff Engineer Bar

A strong staff-level mobile system design answer demonstrates:

- Product judgment: you clarify goals, users, constraints, and success metrics.
- Systems thinking: you reason across client, backend, data, infra, release, and operations.
- Mobile depth: you understand lifecycle, offline behavior, app size, battery, threading, storage, permissions, and platform limits.
- Tradeoff clarity: you can compare options and explain why one choice fits the requirements.
- Reliability mindset: you design for failure, rollback, observability, and gradual rollout.
- Technical leadership: you identify ownership boundaries, migration paths, and team execution risks.

## How To Use This Repo

For each design problem:

1. Clarify the problem and users.
2. Separate functional requirements from non-functional requirements.
3. Define the mobile client responsibilities.
4. Define backend/API responsibilities.
5. Design data models and state transitions.
6. Plan offline, sync, caching, retries, and conflict handling.
7. Address security, privacy, abuse, observability, rollout, and testing.
8. Call out tradeoffs and future extensions.

Use the [template](templates/mobile-system-design-template.md) to practice complete answers.

## Repository Structure

```text
.
├── README.md
├── modules/
│   ├── 01-system-design-basics.md
│   ├── 02-mobile-moving-parts.md
│   ├── 03-functional-requirements.md
│   ├── 04-non-functional-requirements.md
│   └── 05-staff-answer-framework.md
├── examples/
│   └── offline-first-notes.md
├── templates/
│   └── mobile-system-design-template.md
└── diagrams/
    └── mobile-system-overview.md
```

## Hosting on GitHub

The simplest publishing path is to create a GitHub repository and push this folder as-is. GitHub renders Markdown files directly, including Mermaid diagrams.

Suggested repo name:

```text
mobile-system-design-android-staff-engineer
```

Basic setup:

```bash
git init
git add .
git commit -m "Add mobile system design tutorial"
git branch -M main
git remote add origin git@github.com:<your-user>/mobile-system-design-android-staff-engineer.git
git push -u origin main
```

Optional: enable GitHub Pages with the repository root as the source if you want a browsable tutorial site.

## Suggested Practice Problems

- Design WhatsApp message sync.
- Design Google Photos upload and backup.
- Design Uber live ride tracking.
- Design Netflix downloads for offline playback.
- Design a mobile banking login and transaction flow.
- Design a food delivery order tracking experience.
- Design a real-time collaborative document app on mobile.
- Design a crash reporting SDK.
- Design mobile feature flagging and experimentation.
- Design push notifications at scale.
