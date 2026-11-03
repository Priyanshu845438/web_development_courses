# Microservices practical: test a service boundary

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

A tested monolithic task application; this lesson is optional.

## Lesson and lab

Begin with a modular monolith. Identify a notification module that can fail without losing a task. Define its input contract and keep it out of the task database transaction's external network calls.

1. Implement an in-process notification interface and a fake adapter.
2. Write contract tests for valid, invalid, and duplicate event inputs.
3. Optionally run a second local process for notifications with its own storage.
4. Add a bounded timeout and test the notification process being unavailable.
5. Record how failed notifications are retried without duplicating effects.

Do not split user identity, tasks, and persistence simply to increase service count. A boundary is useful when independent ownership, scaling, or reliability needs justify the operational cost.

Deliver a sequence diagram, contract examples, failure test, and a comparison against the monolith. Explain which data each component owns. Extension: implement an outbox with a unique event ID and prove duplicate delivery does not send duplicate notifications.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
