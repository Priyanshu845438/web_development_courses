# Development setup

[Home](README.md) · [Guide](COURSE-GUIDE.md)

Install a code editor, Git, a modern browser with developer tools, and a supported Node.js LTS release compatible with your build tool. Check [Node.js downloads](https://nodejs.org/en/download) and [Vite requirements](https://vite.dev/guide/) before installation; requirements change.

```sh
git --version
node --version
npm --version
```

Record these versions in your project README. Keep exercises in a separate `practice/` directory; do not run every command block from the reference lessons in the course repository.

## First browser exercise

Create `practice/hello/index.html` with a heading and a labeled input. Open it in your browser. Inspect the DOM, use the keyboard to focus the input, and change one style in developer tools. Later use a local development server for modules and network requests.

## React practice project

From your practice directory:

```sh
npm create vite@latest task-board -- --template react-ts
cd task-board
npm install
npm run dev
```

Open the URL printed by the development server. Stop it with Ctrl+C. Run `npm run build` to check the production build, then `npm run preview` for a local preview. Preview is not a production hosting service. Commit the lockfile; use `npm ci` for reproducible installs after a lockfile exists.

This course uses Vite for learning client-side React. For applications needing integrated routing, server rendering, or server components, evaluate the framework options described in the [React documentation](https://react.dev/learn/build-a-react-app-from-scratch).

## Working safely and reproducibly

Use `.env.example` with placeholder names, exclude `.env` and dependencies from Git, and keep secrets on the server. Frontend environment values included in a bundle are public. Use a disposable database for exercises and tests. Record database setup, migration, and reset steps before storing important work.

## Troubleshooting

| Symptom | First check |
| --- | --- |
| Command not found | Reopen the terminal and verify installation/PATH |
| Unsupported runtime | Compare `node --version` with the tool requirements |
| Port occupied | Stop your previous server or choose another port |
| Request fails | Inspect URL, status, response body, server logs, and CORS configuration |
| Page works only in dev | Build and preview; inspect asset paths and environment configuration |
| Dependency mismatch | Use the project's lockfile and documented runtime; avoid arbitrary upgrades |
