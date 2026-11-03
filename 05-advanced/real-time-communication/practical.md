# Real-time practical: synchronized task status

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

A persistent API and real-time fundamentals.

## Lesson and lab

Keep the database as the source of truth; use events to notify clients that data changed. Start with two tabs connected to your local application.

Define an event envelope such as `{"type":"task.updated","taskId":"123","version":2}`. After an authorized database update succeeds, send an event only to users permitted to see that task. The client can refetch the task through the authorized API.

1. Connect two tabs as the same test user and show connection status.
2. Update a task in one tab; verify the other refreshes its view.
3. Disconnect the second tab, make changes, reconnect, and refetch current state.
4. Send the same event twice and ensure it does not create duplicate tasks.
5. Connect as a different user and verify no private event is received.

Record expected and observed behavior. Authentication at connection time does not replace authorization for subscriptions and messages. Test expired sessions, invalid payloads, and repeated reconnects. Use bounded retry delay with jitter and clean up connections when components unmount.

Deliver event contracts and a two-client demonstration. Extension: detect missed versions and trigger resynchronization instead of assuming event delivery is complete.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
