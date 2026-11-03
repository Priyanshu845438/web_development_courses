# API fundamentals: contracts before controllers

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

HTTP, JavaScript async functions, and basic Express routing.

## Lesson and lab

An API contract defines inputs, outputs, errors, and permissions. Design a task resource before implementing handlers.

| Operation | Request | Success |
| --- | --- | --- |
| List owned tasks | GET /api/tasks?limit=20 | 200 with items and pagination information |
| Create task | POST /api/tasks | 201 with created task and Location header |
| Read task | GET /api/tasks/:id | 200 with owned task |
| Update task | PATCH /api/tasks/:id | 200 with updated task |
| Delete task | DELETE /api/tasks/:id | 204 with no body |

Validate content type, body shape, string length, allowed status values, identifiers, and bounded pagination. Treat all client fields as untrusted. Derive ownership from authenticated server context, never from a submitted owner ID.

Use 400 for malformed or invalid requests under this course's convention, 401 for missing/invalid authentication, 403 for forbidden actions, 404 for missing resources (also an intentional concealment option), and 409 for conflicts. Document the convention consistently. An error response can be `{"error":{"code":"INVALID_TITLE","message":"Title is required"}}`; do not return database details or stack traces.

GET should not mutate business state. PUT conventionally replaces a resource; PATCH changes selected fields. Retrying creation may produce duplicates, so use a documented idempotency mechanism when the product requires safe retries. CORS controls browser access to responses; it does not authenticate callers.

Exercise: write request/response examples for each route, including an invalid title and another user's ID. Implement the happy path in memory, then add validation and authorization tests before persistence. Explain which behavior changes when the server restarts. GraphQL is an optional alternative, not a prerequisite for a good REST contract.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
