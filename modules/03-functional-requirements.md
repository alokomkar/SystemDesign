# 03. Functional Requirements

Functional requirements define what the product must do.

In interviews, clarify functional requirements before jumping into architecture. Mobile system design problems often sound simple until you identify the full user journey.

## Requirement Categories

### User Journeys

Define the main flows:

- Onboarding.
- Login.
- Browse.
- Create.
- Edit.
- Delete.
- Share.
- Search.
- Sync.
- Notify.
- Recover from error.

For each journey, ask what happens when the app is offline, backgrounded, updated, or used across multiple devices.

### Data Operations

Identify:

- What entities exist?
- Who can create them?
- Who can read them?
- Who can update them?
- Who can delete them?
- Are deletes soft or hard?
- Is history required?
- Does the client need full objects or partial projections?

### Real-Time Behavior

Ask whether the system needs:

- Live updates.
- Typing indicators.
- Presence.
- Streaming progress.
- Location updates.
- Collaborative editing.
- Push-driven refresh.

Real-time requirements strongly affect backend protocols, battery consumption, and lifecycle handling.

### Offline Behavior

Clarify:

- Can users read cached data offline?
- Can users create or edit offline?
- Which actions must be blocked offline?
- How are pending changes shown?
- How are conflicts resolved?
- How long can offline data remain valid?

### Cross-Device Behavior

Many mobile systems span phones, tablets, web, and wearables.

Ask:

- Is the account state shared across devices?
- Should changes propagate immediately?
- Are device-specific preferences separate?
- How are concurrent edits handled?
- Does logout on one device affect others?

### Notifications

Clarify:

- What events notify users?
- Are notifications transactional or promotional?
- Do users control preferences?
- Are quiet hours required?
- What deep link should open?
- What happens if the app data is stale when opened?

### Search and Discovery

Ask:

- What fields are searchable?
- Is search local, remote, or hybrid?
- Are suggestions required?
- Is ranking personalized?
- Is search available offline?
- Are filters and sorting required?

### Admin, Trust, and Abuse

Staff-level answers should include non-happy-path product operations:

- Reporting content.
- Blocking users.
- Moderation.
- Fraud detection.
- Rate limiting.
- Audit history.
- Customer support tooling.

## Functional Requirements Checklist

Use this during practice:

- Primary users and roles.
- Critical user journeys.
- Entity model.
- CRUD operations.
- Permissions and access control.
- Offline read behavior.
- Offline write behavior.
- Sync behavior.
- Search behavior.
- Notifications.
- Cross-device behavior.
- Error recovery.
- Admin/support operations.
- Version compatibility.

## Example: Food Delivery Order Tracking

Functional requirements might include:

- User can view active order status.
- User can see courier location on a map.
- User receives push notifications for status changes.
- User can contact support.
- User can cancel before a cutoff state.
- Restaurant can update preparation status.
- Courier can update pickup and delivery status.
- System records complete order state history.

Mobile-specific questions:

- How often should location update?
- Does the app need tracking when backgrounded?
- What if push arrives before the app has the latest order state?
- What if the user opens the order from notification deep link?
- What if status updates arrive out of order?

