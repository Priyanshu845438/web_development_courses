# Testing practical: observable behavior

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

JavaScript functions and an API with isolated test data.

## Lesson and lab

Start with a dependency-free unit test. Save the function as `task.mjs`:

```js
export function normalizeTitle(value) {
  if (typeof value !== 'string' || !value.trim()) {
    throw new TypeError('Title is required');
  }
  return value.trim();
}
```

Save `task.test.mjs` beside it:

```js
import test from 'node:test';
import assert from 'node:assert/strict';
import { normalizeTitle } from './task.mjs';
test('trims surrounding whitespace', () => {
  assert.equal(normalizeTitle('  Study  '), 'Study');
});
test('rejects invalid titles', () => {
  for (const value of ['', '   ', null, 42]) {
    assert.throws(() => normalizeTitle(value), TypeError);
  }
});
```

Run `node --test task.test.mjs`. Temporarily remove trimming and observe a failure, then restore it. A passing test is more convincing when you know the regression it detects.

Next, test the API against a disposable database: create a task, read it, reject an invalid body, and deny another user's update. Reset fixtures between cases. Add a browser test that creates a task through labeled controls and checks persistence after refresh.

Deliver unit, API, and browser test commands with results. Prefer accessible labels and user-visible outcomes over internal component state. Do not mock your database in the integration test meant to verify persistence.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
