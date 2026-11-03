# React practical: task board

[Module overview](README.md) · [Course guide](../../COURSE-GUIDE.md)

## Before you begin

JavaScript arrays, events, and TypeScript task types.

## Lesson and lab

Create the React/TypeScript project from the setup guide. Replace `src/App.tsx` with:

```tsx
import { useState, type FormEvent } from 'react';
type Task = { id: string; title: string; done: boolean };
export default function App() {
  const [tasks, setTasks] = useState<Task[]>([]);
  const [title, setTitle] = useState('');
  function add(event: FormEvent<HTMLFormElement>) {
    event.preventDefault();
    if (!title.trim()) return;
    setTasks(current => [...current, {
      id: crypto.randomUUID(), title: title.trim(), done: false
    }]);
    setTitle('');
  }
  return <main>
    <h1>Task board</h1>
    <form onSubmit={add}>
      <label htmlFor="title">Task title</label>
      <input id="title" value={title} required
        onChange={event => setTitle(event.target.value)} />
      <button>Add task</button>
    </form>
    {tasks.length === 0 && <p>No tasks yet.</p>}
    <ul>{tasks.map(task => <li key={task.id}>
      <label><input type="checkbox" checked={task.done}
        onChange={() => setTasks(current => current.map(item =>
          item.id === task.id ? { ...item, done: !item.done } : item))} />
        {task.title}</label>
    </li>)}</ul>
  </main>;
}
```

Run the dev server and add two tasks with identical titles. Toggle one: only that task should change. Stable IDs distinguish records; titles and array positions do not.

Add a completed-task filter using a derived array, not a second copy of task state. Add deletion and an announced validation message for whitespace input. Extract a TaskItem component with typed props.

Check keyboard submission, empty state, independent toggles, and production build. Refresh currently clears tasks: document this limitation. Add persistence only after validating stored data; store no credentials. Later replace persistence with the course API and cover loading, error, and retry states.

## Completion evidence

Save your implementation or design, the commands or steps used to verify it, observed results, and one remaining limitation. Explain the main tradeoff without reading the lesson.
