---
name: report-from-pdf
description: Generate a standardized markdown coding-agent test report from an attached PDF. USE WHEN the user attaches a PDF of an agent test report and asks to convert it, create a markdown report, or generate an .md file from it. Output matches the AIRUN-Engineering-Benchmark format used in pages/agentic-tests/reports/{agent}/{year}/. Triggers on phrases like "create a report", "convert this PDF", "generate md from this PDF", "make a report from the attached doc".
---

# PDF → Markdown Agent Test Report

Convert an attached PDF coding-agent test report into a standardized `.md` file matching the AIRUN-Engineering-Benchmark format.

## Workflow

1. **Read the PDF in full** — see [Reading the PDF](#reading-the-pdf). Never work from a partial read; the test report table is the bulk of the document and is easy to truncate silently.
2. **Open one existing report as a reference** — pick the most recent file under `pages/agentic-tests/reports/` (e.g. `devin/2026/devin-agentic-tests-may-2026.md`). The repository format drifts slightly over time; the newest report is the source of truth, this skill is the summary of it.
3. **Resolve the output path** using the naming convention below.
4. **Fill in** `references/report-template.md` with the extracted data to produce the final markdown.
5. **Save** the file to the resolved path, creating the `{agent-slug}/{year}/` directories if they do not exist.
6. **Verify** the result against the [checklist](#verification-checklist) before reporting completion.
7. **Offer the follow-up**: the report is not visible on the site until the leaderboard is updated — offer to run the `update-leaderboard` skill next.

## Reading the PDF

These reports run to dozens of pages and the `Read` tool accepts at most 20 PDF pages per call.

- Read the PDF in successive page ranges (`pages: "1-20"`, `"21-40"`, …) until you reach the end. A range that returns nothing means you have passed the last page.
- Extract the test report table **one task row at a time** into a scratch file as you go, rather than holding the whole table in your head — wide tables are where data gets dropped.
- If the PDF is scanned (page reads return no text), stop and tell the user; do not guess at the content.

## Data Fidelity

- **Transcribe, never infer.** Percentages, file/line statistics, task ids, prompt texts and grades are copied verbatim from the PDF. If a value is absent, leave the cell empty — do not compute, round or reconstruct it.
- Escape any literal `|` inside a table cell as `\|`, otherwise it breaks the row.
- Keep the PDF's own wording for prose sections; do not rewrite or summarize it.

## Output Path Convention

```
pages/agentic-tests/reports/{agent-slug}/{year}/{agent-slug}-{test-slug}-tests-{month}-{year}.md
```

| Token | Rule |
|---|---|
| `{agent-slug}` | kebab-case agent name from the report title (e.g. `pi-dev`, `cursor`, `jetbrains-ai-assistant`). Reuse the existing directory name if the agent already has one. |
| `{test-slug}` | **Defaults to `agentic`** — that is the form used by most reports in the repository (`claude-code-agentic-tests-may-2026.md`). Replace it with a model or variant slug **only when the report title names one** (e.g. `glm-5-1`, `claude-agent`, `junie`, `spec-mode`), giving `pi-dev-glm-5-1-tests-april-2026.md`. |
| `{month}` | lowercase English month (e.g. `april`) |
| `{year}` | 4-digit year (e.g. `2026`) |

**Examples**

- `Claude Code Agent Tests - May 2026` → `pages/agentic-tests/reports/claude-code/2026/claude-code-agentic-tests-may-2026.md`
- `Pi.Dev Coding Agent Tests on GLM-5.1 - April 2026` → `pages/agentic-tests/reports/pi-dev/2026/pi-dev-glm-5-1-tests-april-2026.md`

Some older reports sit directly in `{agent-slug}/` without a year directory, or omit the year from the filename. That is legacy — new reports always use `{agent-slug}/{year}/` and always carry the year in the filename. Do not rename existing files.

## Section Mapping

`## Summary`, `## Testing` → `### Environment`, `## Code Generation Findings`, `## Testing Customization`, `## Test Report` and `## Agent's Final Grade` appear in every report, in that order.

| PDF Content | Markdown Section | |
|---|---|---|
| Opening summary paragraphs | `## Summary` | required |
| Environment table (version, model, etc.) | `## Testing` → `### Environment` | required |
| Code generation observations | `## Code Generation Findings` | required |
| Note about AGENTS.md / rules file | `## Testing Customization` | required |
| Full test case table | `## Test Report` | required |
| Final grade text + summary table | `## Agent's Final Grade` | required |
| Agent description / feature highlights | `## Details` or `## Distinctive Features` — use the heading the PDF itself uses | optional, after `## Summary` |
| Setup, indexing or repository-preparation notes | `## Testing Approach` (with `###` subsections) | optional, after `## Testing Customization` |
| Reference links collected at the end | `## Links` | optional, last section before the footer |

Include every optional section the PDF contains, and omit the ones it does not. Do not invent a section to fill the template.

## Test Report Table

The table has **13 columns** — emit all of them in every row, leaving a cell empty rather than dropping it:

`#` | `Run` | `Sourcecode Repository` | `Task Summary` | `Task Description (Initial Prompt)` | `First-Shot Effort` | `First-Shot Completeness` | `First-Shot Accuracy` | `Subsequent Prompts (Feedback, Comments)` | `Final Completeness` | `Final Accuracy` | `Statistics` | `Comments`

**Cell formatting rules:**

- Use `<br>` for line breaks within a cell; use `<br><br>` to separate bullet-like items.
- In the **Task Summary** column, bold field labels: `**Id:**`, `**Name:**`, `**Category:**`, `**Complexity:**`, each followed by `<br><br>` before the next field.
- In **First-Shot Completeness / Accuracy** and their **Final** equivalents: start with the percentage (with the `%` sign), then `<br><br>`, then bullet items prefixed with `- `. When there are no bullets, the cell is just the percentage.
- In the **Subsequent Prompts** column: number each prompt `1)`, `2)`, etc., separated by `<br><br>`. When the PDF says the agent needed none, write `Not required`.
- In the **Statistics** column: `Files:<br>X modified(M)<br>Y added(A)<br>Z deleted(D)<br><br>Lines:<br>N insertions(+)<br>M deletions(-)`.
- Leave a cell blank (just empty) when there is no content.

## Agent's Final Grade Section

Start with a sentence: `The agent's final grade is **{X}%**.`

Then include the summary table with columns:

`Number` | `Tag` | `Subsequent Prompts Count` | `Performance` | `accuracy.first` | `completeness.first` | `accuracy.final` | `completeness.final` | `Grade`

Unlike the test report table, the values here are **decimals, not percentages** (e.g. `0.67`). Right-align every column with `---:` except `Number` and `Tag`. One row per test case, in the same order as the test report table.

## Copyright Footer

Always end the report with this exact HTML paragraph, replacing the year with the report year:

```html
<p style="text-align: center;">    © {YEAR} EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
```

## Verification Checklist

Run these checks against the saved file and report the results; fix anything that fails before finishing.

- [ ] The number of rows in `## Test Report` equals the number of task rows in the PDF, and the `#` column runs 1..N with no gaps.
- [ ] Every row has exactly 13 cells (14 `|` characters, counting the leading and trailing ones).
- [ ] `## Agent's Final Grade` has one summary row per test report row, with matching task ids.
- [ ] The final grade percentage in the sentence matches the grade stated in the PDF.
- [ ] Every required section from the mapping is present, in order, and every optional section the PDF has is included.
- [ ] The copyright footer is present with the report's year.
- [ ] No `{PLACEHOLDER}` tokens and no template `<!-- ... -->` comments remain in the output.

## Template

See `references/report-template.md` for the complete report skeleton with `{PLACEHOLDER}` tokens to fill in.
