# Mobile System Design for Senior and Staff Android Engineers

This repository is a practical tutorial for preparing for senior and staff-level Android and mobile system design interviews.

The focus is not only "how do I design an app screen?" It is how to reason about a complete mobile system: product requirements, client architecture, backend contracts, sync, offline behavior, performance, reliability, security, observability, rollout, and long-term maintainability.

## Topics Covered

- [Who This Is For](https://github.com/alokomkar/SystemDesign/tree/main#who-this-is-for)
- [What Makes Mobile System Design Different](https://github.com/alokomkar/SystemDesign/tree/main#what-makes-mobile-system-design-different)
- [Tutorial Roadmap](https://github.com/alokomkar/SystemDesign/tree/main#tutorial-roadmap)
- [Senior vs Staff Bar](https://github.com/alokomkar/SystemDesign/tree/main#senior-vs-staff-bar)
- [How To Use This Repo](https://github.com/alokomkar/SystemDesign/tree/main#how-to-use-this-repo)
- [Repository Structure](https://github.com/alokomkar/SystemDesign/tree/main#repository-structure)
- [Contributing](https://github.com/alokomkar/SystemDesign/tree/main#contributing)
- [Suggested Practice Problems](https://github.com/alokomkar/SystemDesign/tree/main#suggested-practice-problems)

## Who This Is For

- Android engineers preparing for senior, senior staff, or staff engineer interviews.
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

Senior-level design answers should show that you can turn ambiguous product behavior into clear client architecture, APIs, data models, and failure handling.

Staff-level design answers should additionally show that you can operate across the full system, not just within one codebase.

## Tutorial Roadmap

1. [System Design Basics](modules/01-system-design-basics.md)
2. [Mobile Moving Parts](modules/02-mobile-moving-parts.md)
3. [Functional Requirements](modules/03-functional-requirements.md)
4. [Non-Functional Requirements](modules/04-non-functional-requirements.md)
5. [Senior and Staff Design Answer Framework](modules/05-staff-answer-framework.md)
6. [Example: Offline-First Notes App](examples/offline-first-notes.md)
7. [Practice Scenario: WhatsApp Chats List and Chat Screen](examples/whatsapp-chat.md)
8. [Practice Scenario: WhatsApp Message Sync](examples/whatsapp-message-sync.md)
9. [Practice Scenario: Twitter Feed - Senior Engineer](examples/twitter-feed-senior.md)
10. [Practice Scenario: Twitter Feed - Staff Engineer](examples/twitter-feed-staff.md)
11. [Design Template](templates/mobile-system-design-template.md)

## Senior vs Staff Bar

A strong senior-level mobile system design answer demonstrates:

- Product clarity: you identify core users, flows, and edge cases.
- Mobile architecture depth: you design screens, state, persistence, networking, and background work coherently.
- API thinking: you define practical contracts with pagination, errors, retries, and versioning.
- Reliability basics: you handle offline, process death, retries, and duplicate operations.
- Performance awareness: you consider startup, scrolling, rendering, memory, battery, and app size.
- UI visualization: you can sketch the app surface, states, and transitions before diving into internals.
- Testing judgment: you identify useful unit, integration, UI, and manual test coverage.

A strong staff-level mobile system design answer adds:

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
6. Add UI wireframes for key screens and states where useful.
7. Plan offline, sync, caching, retries, and conflict handling.
8. Address security, privacy, abuse, observability, rollout, and testing.
9. Call out tradeoffs and future extensions.

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
│   ├── offline-first-notes.md
│   ├── twitter-feed-senior.md
│   ├── twitter-feed-staff.md
│   ├── whatsapp-chat.md
│   └── whatsapp-message-sync.md
├── templates/
│   └── mobile-system-design-template.md
└── diagrams/
    └── mobile-system-overview.md
```

## Contributing

Contributions are welcome. Any contributor can fork the repository, create a branch, and raise a pull request.

Contributor workflow:

```bash
git clone https://github.com/alokomkar/SystemDesign.git
cd SystemDesign
git checkout -b add-new-system-design-example
git add .
git commit -m "Add new mobile system design example"
git push origin add-new-system-design-example
```

Then open a pull request from your branch to the main repository.

Good PRs include:

- New mobile system design examples.
- Senior vs staff-level interview walkthroughs.
- UI wireframes that help readers visualize the app being designed.
- Better architecture diagrams or Mermaid flowcharts.
- Corrections that improve technical accuracy.
- Android-specific tradeoffs, APIs, storage models, or testing strategies.
- Improvements to existing examples for clarity, structure, or completeness.

Please keep contributions practical and explicit. The goal is to teach engineering judgment, not to collect buzzwords.

For example structure and contribution guidance, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Suggested Practice Problems

- [Design WhatsApp chats list and chat screen.](examples/whatsapp-chat.md)
- [Design WhatsApp message sync.](examples/whatsapp-message-sync.md)
- [Design Twitter feed - senior engineer.](examples/twitter-feed-senior.md)
- [Design Twitter feed - staff engineer.](examples/twitter-feed-staff.md)
- Design Google Photos upload and backup.
- Design Uber live ride tracking.
- Design Netflix downloads for offline playback.
- Design a mobile banking login and transaction flow.
- Design a food delivery order tracking experience.
- Design a real-time collaborative document app on mobile.
- Design a crash reporting SDK.
- Design mobile feature flagging and experimentation.
- Design push notifications at scale.
