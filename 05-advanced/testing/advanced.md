# Testing advanced: reliable signals

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

Unit, API integration, and browser tests.

## Lesson and lab

Choose tests by risk. Ownership enforcement deserves database-backed tests; formatting a label usually does not need a full browser run. Coverage measures executed code, not correctness.

Investigate a flaky test by recording seed data, timestamps, network events, and execution order. Replace fixed sleeps with observable conditions. Control clocks for expiration tests, isolate database state, and avoid shared mutable fixtures. Retrying may gather evidence but must not hide a recurring defect.

Exercise: build a matrix for task creation, expired identity, concurrent updates, timeout, and database failure. Assign each scenario to the lowest layer that can prove the behavior. Introduce one deliberate regression and confirm the relevant test fails.

Run fast checks before expensive browser checks in CI. Preserve failure logs and screenshots without secrets. For visual tests, stabilize fonts and data. For load tests, define workload, concurrency, duration, error threshold, and latency distribution; use an authorized disposable environment.

Deliver a risk-based test plan and a flaky-test investigation. Explain which external dependencies are mocked and which failure modes those mocks cannot prove.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
