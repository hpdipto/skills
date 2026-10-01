---
name: understand-pr
description: Understand a pull request locally before reviewing it.
---

# Understand PR

Understand the PR. Do not review it.

## Dependency

Before starting, load and follow `caveman`.

If unavailable, stop and tell the user.

## PR Source

1. Check the current branch.
2. If the current branch is associated with a pull request, use it.
3. Otherwise, ask the user for a PR number, URL, or other identifier.
4. Never guess the PR.

## Workflow

Inspect:

- PR description
- PR URL
- Related ticket/issue URL
- Title and author
- Full diff
- Changed files
- Relevant surrounding code
- Callers and consumers
- Tests
- Configuration and dependencies
- History when useful

Understand:

- Why the PR exists
- What it changes
- How it works
- How it fits the architecture
- What behavior changes
- Important data/control flows
- Important API/type/data-model changes
- Responsibilities of important changed components

Use concise structural representations when useful:

- File/component trees
- Call-flow diagrams
- Data-flow diagrams
- Control-flow diagrams
- API/data-model summaries
- Small pseudocode snippets

Do not:

- Review
- Find bugs
- Suggest fixes
- Modify source files
- Modify the PR

## Output

Save to:

`.tmp/understand-pr-<PR_NUMBER>.md`

Create `.tmp/` if necessary.

Overwrite if it already exists.

Use exactly this structure:

# PR #<PR_NUMBER>

PR Link: <PR_URL>

Ticket Link: <TICKET_URL>

Title: <PR_TITLE>

Author: <PR_AUTHOR>

## Intent

## Changes

## Flow

## Architecture

## Behavior

## Tests

## Unknown

Always include the PR Link, Ticket Link, Title, and Author.

If a value cannot be determined, use `N/A`. Never guess.

Use diagrams or small code snippets only when they improve understanding.

Keep everything minimal and factual.

After saving, return only a one-line confirmation.

## Style

Follow `caveman` ultra.

Be extremely concise.
Short bullets.
No filler.
No repetition.
No unnecessary explanation.
