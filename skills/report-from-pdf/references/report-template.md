# {AGENT_FULL_NAME} Tests{SEPARATOR}{MODEL_OR_VARIANT} — {MONTH} {YEAR}

<!-- TITLE RULES:
  - SEPARATOR is " — " (em-dash with spaces) if MODEL_OR_VARIANT is present, else just a space before the em-dash.
  - MODEL_OR_VARIANT: model or agent variant name if named in the report (e.g. "on GLM-5.1", "Claude Agent", "Junie"). Omit if not applicable.
  - Example with model:    "Pi.Dev Coding Agent Tests on GLM-5.1 — April 2026"
  - Example without model: "Cursor AI Agent Tests — February 2026"
  - Example with variant:  "JetBrains IDEA Junie Agent Tests - April 2026"
-->

## Summary

{SUMMARY_PARAGRAPHS}

## Details

{DETAILS_PARAGRAPHS}

{DETAILS_HIGHLIGHTS_INTRO}

{DETAILS_BULLET_LIST}
<!-- If the source has a bullet-list of highlights under Details, include them here as a standard markdown list.
     If there are no bullets, remove the two lines above. -->

## Testing

### Environment

| Component | Version |
|---|---|
| {COMPONENT_1} | {VERSION_1} |
| {COMPONENT_2} | {VERSION_2} |
<!-- Add or remove rows to match the source PDF. Common rows: IDE, JetBrains AI Assistant, Agent, Default Model, LLM mode, Thinking level, Version, Payment Plan, Run Mode -->

## Code Generation Findings

- {FINDING_1}
- {FINDING_2}
<!-- Add or remove bullet points to match all findings in the source PDF. -->

## Testing Customization

{TESTING_CUSTOMIZATION_TEXT}

<!-- Example:
General golf-application rules for agents are added as file `AGENTS.md`.

OR (when a specific path is given):
General golf-application rules for agents are added as file:

```text
.aiassistant/rules/AGENTS.md
```
-->

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | {RUN} | {REPO_URL} | **Id:** {TASK_ID}<br><br>**Name:** {TASK_NAME}<br><br>**Category:** {CATEGORY}<br><br>**Complexity:** {COMPLEXITY} | See {TASK_README_URL} | {FIRST_SHOT_EFFORT} | {FIRST_SHOT_COMPLETENESS_PCT}<br><br>- {COMPLETENESS_ITEM_1}<br>- {COMPLETENESS_ITEM_2} | {FIRST_SHOT_ACCURACY_PCT}<br><br>- {ACCURACY_ITEM_1}<br>- {ACCURACY_ITEM_2} | 1) {PROMPT_1}<br><br>2) {PROMPT_2} | {FINAL_COMPLETENESS} | {FINAL_ACCURACY} | Files:<br>{M} modified(M)<br>{A} added(A)<br>{D} deleted(D)<br><br>Lines:<br>{INS} insertions(+)<br>{DEL} deletions(-) | {COMMENTS} |
<!-- Replicate the row pattern above for each test case. 
     - When First-Shot Completeness / Accuracy / Final values have no sub-bullets, just put the percentage.
     - When Subsequent Prompts is "Not required", put that text; no numbered items needed.
     - When Final Accuracy has sub-bullets (e.g. a residual issue), include them after the percentage.
     - When Statistics or Comments are empty, leave the cell blank. -->

## Agent's Final Grade

The agent's final grade is **{FINAL_GRADE_PCT}%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| {TASK_ID} | {TAG} | {SUBSEQUENT_COUNT} | {PERFORMANCE} | {ACC_FIRST} | {COMP_FIRST} | {ACC_FINAL} | {COMP_FINAL} | {GRADE} |
<!-- Add a row per test case. All numeric columns right-aligned (---:). -->

<p style="text-align: center;">    © {YEAR} EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
