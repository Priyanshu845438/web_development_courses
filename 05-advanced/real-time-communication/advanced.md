# Real-time advanced: recovery and scale

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

A two-client synchronization exercise.

## Lesson and lab

Connections fail, messages can be duplicated, and clients can fall behind. Specify ordering and delivery assumptions before designing recovery.

A database transaction and a separate event publish can fail independently. Study the transactional outbox pattern: write the domain change and an event record together; a worker publishes pending records. Consumers still need idempotency because delivery may repeat.

Exercise: diagram failure points between database commit, publish, receipt, and acknowledgement. For each, define whether the client retries, deduplicates, or refetches. Use an event ID and resource version; define retention limits and full-refresh behavior when replay history is unavailable.

Measure active connections, reconnect rate, delivery latency, queue depth, and dropped messages. Bound message sizes and queues to prevent slow consumers from exhausting memory. Recheck permissions after session expiry and role changes.

Deliver a recovery design and fault-injection results from a local environment. Explain how multiple server instances share events and why a shared broker alone does not guarantee exactly-once processing.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
