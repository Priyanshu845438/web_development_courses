# PWA advanced: updates and data boundaries

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

A working manifest, service worker, and offline exercise.

## Lesson and lab

A service worker can continue controlling an open page after a new worker is installed. Treat updates as a lifecycle problem, not just a cache-name change. Use HTTPS in deployment; localhost is suitable for development.

Design a cache policy per resource: versioned public assets may use cache-first; frequently changing public content may need network-first or revalidation. Do not automatically cache authenticated API responses or write requests. Offline task editing needs an explicit queue, conflict rules, and a visible sync status; begin with read-only offline support.

Exercise: deploy version A in a local test environment, keep a tab open, then publish version B. Observe installation, waiting, activation, and control changes. Add an update notice and test refresh behavior. Do not force activation blindly when old pages and new assets may be incompatible.

Test first visit offline, repeat visit offline, unavailable assets, quota failures, and logout followed by offline access. Remove only caches owned by your application. Deliver a cache inventory, update strategy, and test evidence from browser developer tools. Explain why offline success is not proof that queued changes reached the server.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
