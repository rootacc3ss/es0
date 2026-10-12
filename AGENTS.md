# AGENTS.md — instructions for AI agents in es0

`es0` is a personal AI-agent workspace. It is not a codebase: no builds, no
tests, no linting, no dependency management, and it is not a git repo — don't
turn it into one. The work here is mostly prose (notes, docs, todo lists) and
scratch answers to technical questions.

The human-facing explanation of this system is the root `README.md`. This
file is the authoritative version of the rules.

## Thread protocol

Each conversation or task with the human is a **thread**. All work happens
inside thread folders under `threads/`.

**Starting a conversation:**

1. List `threads/` and find the highest existing `id-N`.
2. Create `threads/id-(N+1)/` with a `README.md`:

   ```
   # Thread <N>
   Date opened: <YYYY-MM-DD>
   Topic: <one line>
   Status: active
   ```

3. Append a row to the thread index table in the root `README.md`
   (ID, date, topic, status).

**During a conversation:**

- Every file you create — notes, docs, todo lists, scripts, scratch output —
  goes inside the current thread's folder. Same for any file the human drags
  in or points you at.
- Keep the thread's `README.md` current as you go: fill in the topic, add a
  short log of what was done, list the files that exist, keep the status
  accurate.

**Ending a conversation:**

- Set the thread's status to `done` and update its row in the index.

## Rules

- Nothing is ever created in the root of `es0`. The root holds only
  `README.md`, `AGENTS.md`, and `threads/`.
- Existing threads are archived history: read them for context, never modify,
  delete, or renumber them. Thread IDs are never reused.
- Filenames are lowercase, hyphenated, and descriptive
  (`aws-s3-notes.md`, `todo.md`, `winget-commands.md`).
- If a question doesn't obviously need a file, just answer it — but anything
  worth keeping across sessions gets written into the thread.
