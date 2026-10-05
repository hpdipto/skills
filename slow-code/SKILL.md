---
name: slow-code
description: Implement code incrementally with explicit user approval before every file change.
---

# Slow Code

Implement the requested change one small step at a time.

## Dependencies

Before starting:

1. If the `asd-ste100` skill is available, load and follow it.
2. If the `asd-ste100` skill is not available, follow the ASD-STE100 writing conventions directly.
3. If `ponytail` is available, load and follow it as well.

## Context

A coding context is required.

If no clear context is available, ask the user what they want to build or change.

Do not start implementation without context.

## Workflow

1. Understand the requested change.
2. Show a top-level task breakdown.
3. Ask the user for permission to start.
4. For each step:

    - Identify exactly one file to modify or create.
    - Explain what will change and why.
    - If the change is more than 50 lines, break it into smaller chunks of at most 50 lines.
    - Ask the user for permission to edit.
    - If the user wants to make the change themselves, stop and wait.
    - Otherwise, edit the target file directly.
    - Show a concise summary of the change.
    - Present the change using the harness's native diff/change viewer when available.
    - If the harness has no diff viewer, use `git diff` to show the change.
    - If `delta` is installed, pipe the diff through `delta` for improved readability.
    - Ask the user to review and understand the change.

5. Continue to the next step only after the user explicitly allows it.

## Rules

- One file at a time.
- One logical change at a time.
- Maximum 50 lines changed per chunk.
- Edit target files directly.
- Never create temporary or duplicate files just to generate or display a diff.
- Never edit multiple files in one step.
- Never continue automatically after an edit.
- Always present the change after a completed chunk.
- Use clear, simple, and unambiguous language following ASD-STE100.
- Preserve all previous instructions and decisions throughout the session.
- Do not make unrelated changes.
- Do not batch edits for convenience.
- Do not overthink or over-engineer the solution.
- Prefer the simplest reasonable implementation.
- If a later step requires changing a previously modified file, explain why and ask permission again.
- If requirements become unclear, stop and ask.
