# CSS architecture fundamentals

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

Selectors, cascade, box model, Flexbox, and Grid.

## Lesson and lab

CSS architecture makes changes predictable. Start with shared tokens, small component boundaries, and explicit state styles before adding a library.

```css
:root {
  --space-2: 0.5rem;
  --space-4: 1rem;
  --color-text: #172033;
  --color-surface: #fff;
}
.task-card {
  padding: var(--space-4);
  color: var(--color-text);
  background: var(--color-surface);
  border: 1px solid #667085;
}
.task-card__title { margin-block: 0 var(--space-2); }
.task-card[data-complete="true"] { border-style: dashed; }
.task-card button:focus-visible { outline: 3px solid #174ea6; outline-offset: 3px; }
```

Tokens express shared decisions. Component classes limit accidental coupling. State attributes communicate variation without increasing selector specificity excessively. Do not convey completion by color alone; include visible text or a checked control.

Choose one primary approach: named component classes, CSS Modules, or an established utility system. Document why it fits the project. Avoid global element rules that silently alter unrelated components. Use semantic HTML before adding ARIA.

Exercise: identify repeated spacing/color values in your task board and replace them with tokens. Verify form controls, focus visibility, narrow layouts, and text zoom. Explain cascade order and specificity when two declarations conflict.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
