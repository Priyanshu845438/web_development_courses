# TypeScript practical: validate task input

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

JavaScript objects, functions, and TypeScript fundamentals.

## Lesson and lab

TypeScript checks code before execution; it does not validate a JSON response at runtime. Treat external data as unknown until checked.

```ts
type Task = { id: string; title: string; done: boolean };
function isTask(value: unknown): value is Task {
  if (typeof value !== 'object' || value === null) return false;
  return 'id' in value && typeof value.id === 'string'
    && 'title' in value && typeof value.title === 'string'
    && value.title.trim().length > 0
    && 'done' in value && typeof value.done === 'boolean';
}
const incoming: unknown = JSON.parse('{"id":"1","title":"Study","done":false}');
if (isTask(incoming)) console.log(incoming.title);
```

Create a `task-board` project using the setup guide. Put this example in `src/task.ts`, export the type and guard, and run `npx tsc --noEmit --strict --target ES2022 src/task.ts`. Then model loading/success/error as a discriminated union and render each state explicitly.

Exercise: write a pure `toggleTask(tasks, id)` function that returns a new array without mutating the input. Deliberately assign a string to `done` and confirm the compiler rejects it; remove that intentional error before committing.

Verify null, missing fields, blank titles, wrong field types, and a valid task. Explain why `as Task` would not protect a network boundary. Extension: return useful field-level validation errors instead of a boolean.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
