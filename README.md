# es0 — General AI Agent Workspace

This directory is a personal workspace for working with AI agents on my laptop.
It is **not a codebase**: no project, no builds, no linting, no CI. It exists so
that technical questions, research, notes, and todo lists get a persistent home
instead of dying with the chat session that produced them.

> **If you are an AI agent:** the authoritative instructions for working in this
> directory are in [`AGENTS.md`](AGENTS.md). Read it before doing anything here —
> even if you were pointed at this README instead. The rules below describe the
> same system.

## How it works — threads

Every conversation or task gets its own **thread** — a folder under `threads/`,
numbered in creation order:

```
threads/id-1/   ← first conversation
threads/id-2/   ← second conversation
...
```

Everything a conversation produces or consumes — notes, docs, todo lists,
scratch files, files I drag in — lives inside that thread's folder. Nothing
ever sits loose in the root of `es0`.

Each thread starts as a `README.md` with the thread ID and the date it was
opened. The agent updates that README as the conversation goes: topic, a short
log of what happened, what files exist, and a status (`active` → `done`).
Threads are never renumbered and IDs are never reused. Finished threads are
archived history — readable for context, but not to be modified.

## Thread index

One row per thread, appended when a thread starts.

| ID | Date opened | Topic           | Status |
| -- | ----------- | --------------- | ------ |
| 1  | 2026-10-12  | Workspace setup | done   |

## The system — agent rules

1. **New conversation → new thread.** Find the highest `threads/id-N` and
   create `threads/id-(N+1)/` with its `README.md` (thread ID + today's date,
   ISO format). Append a row to the thread index above.
2. **Everything lives in the thread.** Every file you create, and every file
   the user drops in, goes inside the current thread's folder.
3. **Keep the thread README updated.** Fill in the topic, log what you did,
   list the files, keep the status current. Mark it `done` when the
   conversation wraps up, and update its index row.
4. **Don't touch other threads.** They're archived history.
5. **Nothing in the root.** The root of `es0` holds only `README.md`,
   `AGENTS.md`, and `threads/`.
6. **Sensible filenames.** Lowercase, hyphenated, descriptive:
   `todo.md`, `postgres-notes.md`, `winget-commands.md`.
