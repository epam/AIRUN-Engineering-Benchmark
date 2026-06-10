---
name: report-from-pdf
description: Generate a standardized markdown coding-agent test report from an attached PDF. USE WHEN the user attaches a PDF of an agent test report and asks to convert it, create a markdown report, or generate an .md file from it. Output matches the AIRUN-Engineering-Benchmark format used in pages/agentic-tests/reports/{agent}/{year}/. Triggers on phrases like "create a report", "convert this PDF", "generate md from this PDF", "make a report from the attached doc".
---

# PDF → Markdown Agent Test Report

Convert an attached PDF coding-agent test report into a standardized `.md` file matching the AIRUN-Engineering-Benchmark format.

## Workflow

1. **Extract** all data from the attached PDF: title, date, summary, details, environment table, code generation findings, testing customization note, every row of the test report table, agent's final grade text, and the grade summary table.
2. **Resolve the output path** using the naming convention below.
3. **Fill in** `references/report-template.md` with the extracted data to produce the final markdown.
4. **Save** the file to the resolved path, creating the directory if it does not exist.

## Output Path Convention

```
pages/agentic-tests/reports/{agent-slug}/{year}/{agent-slug}-{test-slug}-tests-{month}-{year}.md
```

| Token | Rule |
|---|---|
| `{agent-slug}` | kebab-case agent name from the report title (e.g. `pi-dev`, `cursor`, `jetbrains-ai-assistant`) |
| `{test-slug}` | model or variant slug if the title names one (e.g. `glm-5-1`, `claude-agent`, `junie`); omit entire token and its preceding `-` if not present |
| `{month}` | lowercase English month (e.g. `april`) |
| `{year}` | 4-digit year (e.g. `2026`) |

**Example**: `Pi.Dev Coding Agent Tests on GLM-5.1 - April 2026` → `pages/agentic-tests/reports/pi-dev/2026/pi-dev-glm-5-1-tests-april-2026.md`

## Section Mapping

| PDF Content | Markdown Section |
|---|---|
| Opening summary paragraphs | `## Summary` |
| Agent description and feature highlights | `## Details` |
| Environment table (version, model, etc.) | `## Testing` → `### Environment` |
| Code generation observations | `## Code Generation Findings` |
| Note about AGENTS.md / rules file | `## Testing Customization` |
| Full test case table | `## Test Report` |
| Final grade text + summary table | `## Agent's Final Grade` |

## Test Report Table

The table has **12 columns** — preserve all of them even when a row cell is empty:

`#` | `Run` | `Sourcecode Repository` | `Task Summary` | `Task Description (Initial Prompt)` | `First-Shot Effort` | `First-Shot Completeness` | `First-Shot Accuracy` | `Subsequent Prompts (Feedback, Comments)` | `Final Completeness` | `Final Accuracy` | `Statistics` | `Comments`

**Cell formatting rules:**

- Use `<br>` for line breaks within a cell; use `<br><br>` to separate bullet-like items.
- In the **Task Summary** column, bold field labels: `**Id:**`, `**Name:**`, `**Category:**`, `**Complexity:**`, each followed by `<br><br>` before the next field.
- In **First-Shot Completeness / Accuracy** and **Final** equivalents: start with the percentage, then `<br><br>`, then bullet items prefixed with `- `.
- In the **Subsequent Prompts** column: number each prompt `1)`, `2)`, etc., separated by `<br><br>`.
- In the **Statistics** column: `Files:<br>X modified(M)<br>Y added(A)<br>Z deleted(D)<br><br>Lines:<br>N insertions(+)<br>M deletions(-)`.
- Leave a cell blank (just empty) when there is no content.

## Agent's Final Grade Section

Start with a sentence: `The agent's final grade is **{X}%**.`

Then include the summary table with columns:

`Number` | `Tag` | `Subsequent Prompts Count` | `Performance` | `accuracy.first` | `completeness.first` | `accuracy.final` | `completeness.final` | `Grade`

All numeric values as decimals (e.g. `0.67`), right-aligned with `---:` except `Number` and `Tag`.

## Copyright Footer

Always end the report with this exact HTML paragraph, replacing the year with the report year:

```html
<p style="text-align: center;">    © {YEAR} EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
```

## Template

See `references/report-template.md` for the complete report skeleton with `{PLACEHOLDER}` tokens to fill in.
