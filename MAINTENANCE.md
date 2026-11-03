# Curriculum maintenance

## Revision: 3 November 2026

Filled seven empty lessons and created seven missing practical/advanced lessons. Added a complete lesson index, setup guide, evidence-based learning schedule, progress tracker, and capstone rubric. Replaced the React fundamentals Create React App setup with a Vite learning path. Retained the existing long-form reference lessons.

## Scope and limitations

This revision repairs curriculum structure and known content gaps. It is not a line-by-line technical certification of the existing 58,000-plus lines of material. Existing examples may use different library versions or require surrounding application code. New lab instructions describe checks for learners; they are not claims that every lab or deployment was executed during editing.

The revised course guide owns scheduling. Older module overview week estimates remain for context. No completion of this curriculum guarantees employment, a senior engineering level, or production readiness.

## Primary references checked for this revision

- [React: building from scratch](https://react.dev/learn/build-a-react-app-from-scratch)
- [Vite: getting started](https://vite.dev/guide/)
- [TypeScript: narrowing](https://www.typescriptlang.org/docs/handbook/2/narrowing.html)
- [MDN: using service workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)

## Future edits

For a new lesson, include prerequisites, an explanation, a concrete exercise, expected results, failure cases, and evidence of completion. Link it from its module overview and the lesson index. Record the versions used when executing examples. Keep secrets, real personal data, and production database operations out of exercise fixtures.

## Reverification before publication

Verified on 3 November 2026 with Node.js v24.14.0 and temporary dependencies: typescript 7.0.2, react 19.3.1, vite 8.3.5.

- All 23 modules contain nonempty overview, fundamentals, practical, and advanced files.
- Markdown local file links outside code blocks resolve; fenced code blocks are balanced. Anchor targets and external URLs were not exhaustively checked.
- The new testing lesson passes both Node unit tests.
- The new TypeScript guard rejects four invalid fixtures and accepts a valid task.
- New TypeScript and React lesson code passes strict TypeScript checking.
- The React example builds with Vite in an isolated verification project; browser interaction was not tested.
- `git diff --check` passes.

These checks validate the documented revision, not every pre-existing snippet or a deployed application. Temporary dependencies and build output are not included in the course repository.
