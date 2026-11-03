# Capstone: a multi-user task board

[Guide](COURSE-GUIDE.md) · [Tracker](PROGRESS.md)

Build a task board with title, status, optional due date, and task ownership. Use React/TypeScript, a Node HTTP API, and one primary database. PostgreSQL is a reasonable relational exercise; MongoDB is an alternative to justify, not an additional required datastore.

## Deliver incrementally

1. **Static interface:** semantic form, empty state, responsive list, keyboard focus.
2. **Local interaction:** create/edit/delete/filter, input validation, stable task identifiers.
3. **HTTP API:** documented routes, validation, pagination, predictable errors, request tests.
4. **Persistence and identity:** migrations, authentication, server-side ownership checks, logout.
5. **Reliability:** loading/error/empty states, critical automated tests, measured performance.
6. **Release:** documented configuration, CI checks, HTTPS deployment, health checks, restore drill.

## Acceptance scenarios

| Scenario | Expected result |
| --- | --- |
| Empty or whitespace title | Rejected by UI and server without creating a record |
| Valid task submitted | Appears once and remains after refresh |
| User B requests User A's task | No task data returned and no mutation allowed |
| Missing/expired identity | Request rejected; UI offers a recovery path |
| Network failure during save | Honest error state; unsaved work remains recoverable |
| Invalid pagination | Bounded validation error; no unbounded query |
| Keyboard-only navigation | All controls reachable with visible focus and useful labels |
| Fresh database | Documented migrations create the expected schema |
| Restore exercise | Backup restores into a separate database and records can be verified |

## Submission evidence

Provide source, setup instructions, runtime versions, schema diagram, API examples, test commands/results, and an explanation of important tradeoffs. Include screenshots at narrow and wide widths, a keyboard review, measured performance before/after one change, and a release/rollback note. Label local checks separately from live deployment evidence.

## Review

Use the guide's 10-point rubric. A cross-user data leak, exposed secret, or destructive untested migration blocks release even if the total score is high. Add one optional feature only after core scenarios pass: offline read-only access, real-time updates, or a small component library. Explain what you deliberately deferred.
