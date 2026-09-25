---
name: update-leaderboard
description: Add or update a row in the AI code assistants agents leaderboard at pages/sandbox-test/code-assistants-agents-leaderboard.md. USE WHEN the user asks to update the leaderboard, add a result to the leaderboard, or register a new agent report in the leaderboard. Triggers on phrases like "update the leaderboard", "add to the leaderboard", "add this result to the leaderboard".
---

# Update AI Code Assistants Agents Leaderboard

Register a completed agent test report in the leaderboard table in `pages/sandbox-test/code-assistants-agents-leaderboard.md`.

## Workflow

1. **Read the whole leaderboard file first.** Its column widths are padded with spaces so the pipes line up; you need the existing rows to match that formatting, to find the current maxima, and to decide between adding and updating.
2. **Gather inputs** — from the report file or the user:
   - Agent name and homepage URL
   - Model name and URL (if available)
   - Link(s) to the report file(s)
   - Agentic Tests grade (%) — from `## Agent's Final Grade` in the report
   - Chat Based Tests grade (%) — if the report or a linked sandbox-test report contains chat results
   - Code Completion Tests grade (%) — if the report or a linked sandbox-test report contains code completion results
3. **Decide: new row or edit?** — see [Add or Update](#add-or-update).
4. **Format the row** following the Row Format rules below.
5. **Place the row** following the Placement rules below.
6. **Re-check the bold markers** across the whole column — see [Bold Rules](#bold-rules). This is the step most easily missed.
7. **Update the `as of` heading** — see [Heading](#heading).
8. **Validate** against the [checklist](#verification-checklist).
9. **Mention the site rebuild** — the published site under `docs/` is generated separately (see the `Update docs …` commits). Tell the user the leaderboard change is not live until `docs/` is regenerated; do not attempt to edit `docs/assets/*.js` by hand.

## Add or Update

- A row is keyed by **agent + model combination**, not by agent. `GitHub Copilot` has several rows, one per chat model, all pointing at the same agentic report.
- If a row for the same agent **and** the same model already exists, update that row in place: add the new report link to `Test Details` and replace the changed grade.
- If the model or agent variant is new, add a new row and leave the existing ones untouched — the leaderboard keeps historical results (e.g. Claude Code appears for Opus 4.7 and for Sonnet 4.5).

## Row Format

```
| {Category} | {Test Details} | {Agentic Tests} | {Chat Based Tests} | {Code Completion Tests} |
```

| Column | Rule |
|---|---|
| `Category` | Agent display name with homepage link, followed by the model name in parentheses with a link if available. Example: `[Pi.Dev](https://pi.dev/) ([GLM-5.1](https://ollama.com/library/glm-5.1))`. When agent and chat use different models, spell both out: `([Claude Opus 4.6](…) for Agent, [Claude 4.6 Sonnet](…) for Chat)`. When the vendor does not disclose it, write `(LLM is undisclosed)`. |
| `Test Details` | One or more markdown links to the relevant report files, separated by ` <br> `. Example: `[Pi.Dev Tests on GLM-5.1 - April 2026](../agentic-tests/reports/pi-dev/2026/pi-dev-glm-5-1-tests-april-2026.md)` |
| `Agentic Tests` | The agent's final grade percentage (e.g. `68%`). `-` if not available. |
| `Chat Based Tests` | Chat-based test percentage (e.g. `92%`). `-` if not available. |
| `Code Completion Tests` | Code completion test percentage (e.g. `54%`). `-` if not available. |

Pad each cell with trailing spaces so the closing pipes line up with the surrounding rows.

### Link Paths

Paths are relative to `pages/sandbox-test/`, where the leaderboard lives:

- agentic test reports → `../agentic-tests/reports/{agent}/{year}/{file}.md`
- sandbox (chat / code completion) reports → `reports/{agent}/{year}/{file}.md`

## Placement

- The table is sorted by the **Agentic Tests** column in descending order.
- When the new row ties with existing rows, put it **first** among the tied rows — the newest result leads (in the May 2026 update, Devin 83% was placed above the existing Amp 83%).
- Rows with no agentic result (`-`) go at the bottom of the table, above the `<div style='text-align: right;'>` footer, sorted among themselves by Chat Based Tests descending.

## Bold Rules

Bold marks the current best result in each of the three numeric columns, and it has to be maintained across the column, not just on the new row:

- Bold (`**83%**`) **every** row whose value equals the column maximum — ties are all bold.
- If the new row sets a new maximum, **remove** the bold from the rows that previously held it.
- If the new row ties the current maximum, bold it too and leave the existing bold rows alone.
- `-` is never bold.
- Do this independently for each of the three numeric columns.

## Heading

The first line is `# AI Code Assistants vs Agents Leaderboard as of {Month} {Year}`. If the report being added is newer than the month in that heading, update it to the report's month and year.

## Verification Checklist

- [ ] The Agentic Tests column still reads as a descending sequence top to bottom, with `-` rows only at the bottom.
- [ ] Each numeric column has bold on exactly the rows holding its maximum, and nowhere else.
- [ ] Every link in the new or edited row points at a file that exists on disk, at the correct relative depth.
- [ ] The new row has exactly 5 cells and its pipes align with the neighbouring rows.
- [ ] The `as of {Month} {Year}` heading reflects the newest report in the table.
