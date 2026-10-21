---
name: slow-code
description: Implement code in small, user-approved steps. Use minimal explanations, report every change, and suggest Conventional Commit messages and files to stage.
---

# Slow Code

Implement one small step at a time. Use the fewest words possible without losing clarity.

## Dependencies

Before starting:

1. If `caveman ultra` is available, load and follow it strictly. Do not compromise its instructions.
2. Otherwise, if `asd-ste100` is available, load and follow it.
3. If neither is available, use short, simple, direct language.
4. If `ponytail` is available, load and follow it too.

## Context

A clear coding task is required.

If the goal or requirements are unclear, ask the user.

Do not start without sufficient context.

## Workflow

### 1. Plan

1. Understand the requested change.
2. Identify relevant files and constraints.
3. Show a short, ordered task breakdown.
4. Explain the purpose of each step in one sentence.
5. Ask permission to start.

Do not edit before approval.

### 2. Execute One Step at a Time

For each step:

1. **Explain:** State the goal, target file, planned change, and reason. Use minimal words.
2. **Ask:** Get explicit permission before editing.
3. **Edit:** Modify only the approved file.
4. **Limit:** Change at most 50 lines per chunk. Ask permission before each chunk.
5. **Show:** Present the diff using the harness's native viewer. Otherwise, use `git diff`, or `delta` if installed.
6. **Report:** Explain the result using the format below.
7. **Wait:** Ask the user to review the change. Do not continue without explicit approval.

Never create temporary or duplicate files to display diffs.

### 3. Required Update After Every Operation

Use this format. Keep each item brief.

**Changed:** What changed.

**Why:** Why it changed.

**Verified:** What was checked and the actual result.

**Next:** The next step and its purpose.

If verification was not performed, say so. Do not invent results.

### 4. Revisit a File

If a later step requires another edit to an existing file:

1. Explain why.
2. State the exact planned change.
3. Ask permission again.
4. Edit only after approval.
5. Show the diff and report the result.

Earlier approval does not authorize later edits.

### 5. Prepare a Commit

When a logical change is complete:

1. Review the relevant diff.
2. Confirm the intended behavior.
3. Report verification results.
4. Suggest a Conventional Commit message.
5. List the exact files to stage and why.
6. Exclude unrelated or pre-existing changes.

Use this format:

**Commit message**
`type(scope): describe the change`

**Stage**

- `path/to/file` — brief reason.

**Why**
One short sentence describing the commit.

Use an appropriate type: `feat`, `fix`, `refactor`, `test`, `docs`, `build`, or `chore`.

Do not stage, commit, or push unless explicitly asked.

If the work is not ready, state what remains.

## Rules

- One file at a time.
- One logical change at a time.
- Maximum 50 changed lines per chunk.
- Ask permission before every file change and chunk.
- Edit target files directly.
- Never modify multiple files in one step.
- Always show the diff after an edit.
- Always explain what changed, why, and what comes next.
- Keep explanations minimal. Remove repetition and unnecessary detail.
- Prefer short sentences and simple words.
- Preserve prior decisions and instructions.
- Do not make unrelated changes.
- Do not over-engineer. Choose the simplest reasonable solution.
- Report only checks that were actually performed.
- Suggest Conventional Commit messages and exact staging files when ready.
- Never stage, commit, or push without permission.
- If requirements are unclear, stop and ask.
- Never continue automatically after an operation.
