# Course guide

[Home](README.md) · [All lessons](MODULES.md) · [Setup](SETUP.md) · [Progress](PROGRESS.md)

## Choose your starting point

New to programming? Start with foundations. Already comfortable with files, terminals, HTTP, and Git? Demonstrate the foundation checkpoint, then start HTML. Know JavaScript? Build the frontend checkpoint before skipping to backend. Skipping reading is reasonable; skipping evidence hides gaps.

## Suggested 32-week schedule

| Weeks | Study | Evidence before moving on |
| --- | --- | --- |
| 1–2 | Computer fundamentals and web basics | Trace DNS → HTTPS → response → rendered page using browser tools |
| 3–4 | Git | Branch, commit, resolve a practice conflict, and explain a diff |
| 5 | HTML | Semantic task form with labels, headings, and keyboard access |
| 6–7 | CSS | Responsive layout with visible focus and no narrow-screen overflow |
| 8–9 | JavaScript | Add, edit, filter, and delete tasks; validate input; debug failures |
| 10 | TypeScript | Model tasks and validate unknown input without unsafe casts |
| 11–12 | Build tools, then React | Rebuild the interface using components and predictable state |
| 13–14 | Node.js | Explain async I/O; separate application logic from server startup |
| 15–16 | Express | Route requests, validate bodies, and return consistent errors |
| 17–18 | API design and authentication concepts | Specify API contracts; prototype access checks using test identities |
| 19–20 | SQL, then authentication integration | Persist users/tasks; migrate schema; verify cross-user isolation |
| 21–22 | MongoDB comparison and state management | Explain storage choice and distinguish server state from UI state |
| 23–24 | Testing and performance | Cover critical failures and record a measured improvement |
| 25–28 | PWA, real-time, CSS architecture; optional microservices | Choose one extension and test its failure modes |
| 29–32 | Deployment and capstone review | Demonstrate release, health checks, backup restore, and rollback |

Start small tests with JavaScript; week 23 deepens the practice. Start accessibility with HTML and security with your first API. Use in-memory data only for initial API exercises; integrate persistent authentication after database study. Do not expose the practice API publicly before completing its access controls.

## Weekly study loop

Spend about a quarter of your time reading, half building, and the rest testing and reviewing. At the end of each session record one concept, one failure, its cause, and your next action. At the end of the week explain the feature without referring to the lesson.

## Checkpoint rubric

Score each dimension 0 (missing), 1 (works with help or only on the happy path), or 2 (works independently with failure evidence): correctness, explanation, accessibility/API usability, failure handling, and reproducibility. Aim for 8/10 before proceeding; fix any zero in correctness or failure handling first. This is a learning rubric, not a professional certification.

## When you get stuck

Reproduce the smallest failing case. Read the actual error and inspect input/output. Check installed versions against official documentation. Change one thing, rerun, and record the result. When asking for help, share expected behavior, actual behavior, minimal code, and redacted logs.

Use AI to explain errors or review an attempt, then reproduce and explain the solution yourself. Never paste credentials or private data into prompts. A generated solution is not proof that you understand or have tested it.
