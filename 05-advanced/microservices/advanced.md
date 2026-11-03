# Microservices advanced: distributed tradeoffs

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

Service boundary exercise and database transactions.

## Lesson and lab

A local ACID transaction cannot automatically make writes across independent services atomic. Define business invariants and use explicit recovery when operations span boundaries.

For task creation plus notification, task creation can succeed while notification is pending. Model pending, delivered, and failed states. For operations needing compensation, describe the compensating action and what happens if it also fails. Compensation is not identical to rolling back a database transaction.

Exercise: write an architecture decision record with context, options, chosen boundary, costs, and reversal plan. Include timeouts, retry budgets, idempotency keys, schema compatibility, tracing identifiers, and ownership of incident response.

Simulate a slow dependency and verify bounded resource use. Avoid retry amplification across several layers. Test an older consumer against an additive event schema change. Separate deployment success from end-to-end health.

Deliver the decision record and failure matrix. Prefer retaining a modular monolith if no measurable benefit justifies separate deployments, network failure handling, and operational overhead.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
