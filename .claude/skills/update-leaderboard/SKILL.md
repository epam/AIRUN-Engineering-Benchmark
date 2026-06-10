---
name: update-leaderboard
description: Add a new row to the AI code assistants agents leaderboard at pages/sandbox-test/code-assistants-agents-leaderboard.md. USE WHEN the user asks to update the leaderboard, add a result to the leaderboard, or register a new agent report in the leaderboard. Triggers on phrases like "update the leaderboard", "add to the leaderboard", "add this result to the leaderboard".
---

# Update AI Code Assistants Agents Leaderboard

Insert a new row into the leaderboard table in `pages/sandbox-test/code-assistants-agents-leaderboard.md` based on a completed agent test report.

## Workflow

1. **Gather inputs** — collect the following from the user or from the report file:
   - Agent name and homepage URL
   - Model name and URL (if available)
   - Link(s) to the report file(s)
   - Agentic Tests grade (%) — from `## Agent's Final Grade` in the report
   - Chat Based Tests grade (%) — if the report or a linked sandbox-test report contains chat results
   - Code Completion Tests grade (%) — if the report or a linked sandbox-test report contains code completion results
2. **Format the row** following the Row Format rules below.
3. **Insert the row** into the leaderboard table at the correct position, following the Placement rules below.

## Row Format

```
| {Category} | {Test Details} | {Agentic Tests} | {Chat Based Tests} | {Code Completion Tests} |
```

| Column | Rule |
|---|---|
| `Category` | Agent display name with homepage link, followed by the model name in parentheses with a link if available. Example: `[Pi.Dev](https://pi.dev/) ([GLM-5.1](https://example.com/glm))` |
| `Test Details` | One or more markdown links to the relevant report files, separated by ` <br> `. Use paths relative to the leaderboard file location. Example: `[Pi.Dev Tests on GLM-5.1 - April 2026](../agentic-tests/reports/pi-dev/2026/pi-dev-glm-5-1-tests-april-2026.md)` |
| `Agentic Tests` | The agent's final grade percentage (e.g. `68%`). Bold (`**68%**`) if it is the highest value in the column. Leave `-` if not available. |
| `Chat Based Tests` | Chat-based test percentage (e.g. `92%`). Bold if highest. Leave `-` if not available. |
| `Code Completion Tests` | Code completion test percentage (e.g. `54%`). Bold if highest. Leave `-` if not available. |

## Placement

- The table is sorted by the **Agentic Tests** column in descending order.
- Rows with no agentic result (`-`) go at the bottom of the table, above the `<div>` footer.
- If multiple rows share the same percentage, insert the new row after the last existing row with the same value.
- If the new row has no agentic result, sort it among the bottom rows by the Chat Based Tests value (descending).
