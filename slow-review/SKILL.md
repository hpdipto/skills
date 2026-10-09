---
name: slow-review
description: Review pull requests incrementally, explain code changes against the PR description and ticket, identify testing gaps, and produce actionable review comments with a final verdict.
---

# Slow Review

Review the pull request one step at a time. Explain each code block and how it relates to the intended changes.

## Dependencies

Before starting:

1. If the `asd-ste100` skill is available, load and follow it.
2. If it is unavailable, follow ASD-STE100 writing conventions directly.
3. If `ponytail` is available, load and follow it as well.

## Context

A review context is required.

Use the PR description, linked ticket, and code changes as context.

If the PR or its context is missing, ask the user for the required information.

Do not start the review without sufficient context.

## Workflow

1. Read the PR description and linked ticket.
2. Inspect the complete diff.
3. Show a top-level review breakdown.
4. Ask the user for permission to start.
5. For each step:

    - Identify one file and one logical code block to review.
    - Explain what the code does.
    - Explain why the code changed.
    - Relate the change to the PR description or ticket.
    - Identify potential bugs, missing cases, or design concerns.
    - Explain each concern with clear reasoning.
    - Identify relevant tests for the code.
    - Check whether the PR includes tests for the intended behavior and important edge cases.
    - Report missing tests, regressions, and untested behavior in the review findings.
    - For each significant concern that warrants a PR comment:

        - Identify the exact file and line where the comment should appear.
        - Generate a concise, actionable Markdown comment.
        - Explain why the issue matters and what change is needed.
        - Include a code suggestion when a small, concrete fix is clear.

    - Ask the user to review and understand the explanation.
    - Continue only after the user explicitly allows it.

6. After all steps, summarize the findings and proposed inline comments.
7. Provide a final review comment and verdict: `APPROVE`, `REQUEST CHANGES`, or `COMMENT`.

## Inline Review Comments

Generate inline comments only for concerns important enough to warrant a PR comment.

For each inline comment, use this format:

- **File:** `path/to/file`
- **Line:** Exact line number or smallest relevant line range in the diff.
- **Comment:**

    ```markdown
    Explain the issue, its impact, and the expected change.
    ```

Rules for inline comments:

- Anchor each comment to the smallest relevant line range in the diff.
- Use a line changed by the PR whenever possible.
- Explain the problem and its practical impact.
- State the expected change clearly.
- Keep comments concise and actionable.
- Include a code suggestion only when the fix is clear and small.
- Do not generate inline comments for minor observations, subjective preferences, or unrelated style issues.
- If the exact line cannot be established from the diff, identify the relevant code block without inventing a line number.

## Final Review

After reviewing all files and code blocks:

1. Summarize the findings by severity.
2. List the missing tests and uncovered edge cases.
3. Present the proposed inline comments with their file paths and line numbers.
4. Write one concise, actionable final review comment in Markdown.
5. Choose one verdict:

    - `APPROVE`: No blocking issues found.
    - `REQUEST CHANGES`: At least one significant issue must be fixed.
    - `COMMENT`: Feedback is useful, but approval or requested changes are not warranted.

The final review comment must support the selected verdict. Do not request changes for minor or subjective concerns alone.

## Rules

- Review one file and one logical code block at a time.
- Explain the code before moving to the next block.
- Keep the PR description and ticket as the source of truth for intended behavior.
- Do not assume requirements that are not documented.
- Distinguish confirmed bugs from possible concerns.
- Do not report unrelated style preferences as defects.
- Do not modify code or tests during the review.
- Do not overthink or over-engineer the review.
- Use the harness's native diff viewer when available.
- If no diff viewer is available, use `git diff`; use `delta` if installed.
- Never continue automatically to the next step.
- Preserve the review context and previous findings throughout the session.
- If requirements or code behavior are unclear, stop and ask.
- Keep explanations and comments clear, simple, and unambiguous.
- Do not invent line numbers, requirements, test results, or code behavior.
