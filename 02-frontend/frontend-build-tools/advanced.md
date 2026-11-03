# Build tools: reproducible delivery

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

A working frontend project and a successful production build.

## Lesson and lab

A development server and a production build have different responsibilities. Inspect the generated output rather than assuming development behavior matches deployment.

1. Commit a lockfile and record the supported Node runtime. Install with `npm ci` in a clean checkout.
2. Run type checking separately when your bundler only transforms TypeScript, then run the production build.
3. Inspect generated asset sizes and identify a large dependency. Lazy-load an infrequently used feature and compare the resulting requests.
4. Preview the build under the intended base path. Refresh a nested route and document the host fallback requirement.
5. Inspect the bundle for an intentionally harmless environment marker. Explain why frontend configuration cannot hold secrets.

Deliver a build report with commands, runtime, bundle sizes before/after, and observed tradeoffs. Test a missing environment value and a failed asset request. Source maps aid debugging but may reveal source; decide how they are uploaded and served. Avoid performance claims based on bundle size alone: measure loading and interaction on the same device and network conditions.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
