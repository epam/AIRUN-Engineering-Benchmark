# GitHub Copilot (Gemini 2.5 Pro Preview) Code Assistant Sandbox Tests - June 2025

## Table of Contents

- [Summary](#summary)
- [Test Execution Results](#test-execution-results)
- [Score](#score)
- [Chat-Based Tests (Gemini 2.5 Pro Preview)](#chat-based-tests-gemini-25-pro-preview)
- [Code Completion Tests](#code-completion-tests)
- [Configuration](#configuration)
- [UX Summary](#ux-summary)
- [Links](#links)

## Summary

Compared to the Copilot results from [March 2025](copilot-gpt4o-sandbox-tests-march-2025.md) with the GPT-4o model, the chat-based test pass rate decreased from **91.95%** to **86.21%** with Gemini 2.5 Pro (Preview) model. The code completion pass rate also dropped from **81.67%** to **73.53%**. This decrease can be attributed to the rise in the number of complex code completion tests, which increased from **60** to **68**.

Overall, the pass rate decreased from **87.76%** to **80.65%** compared to the results from March 2025.

## Test Execution Results

[SandboxTestsCopilotJune2025.xlsx](../../../../../reports/2025/SandboxTestsCopilotGemini2.5ProJune2025.xlsx)

## Score

- **Overall Score:** 80.65% (30/155)
- **Chat-based tests score:** 86.21% (12/87)
- **Code completion tests score:** 73.53% (18/68)

## Chat-Based Tests (Gemini 2.5 Pro Preview)

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 86.36         | 44            | 6            |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 85.71         | 35            | 5            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 87.50         | 8             | 1            |

*The tests for the chat window were conducted using the Gemini 2.5 Pro (Preview) model.*

## Code Completion Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 65.00         | 40            | 14           |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 85.00         | 20            | 3            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 87.50         | 8             | 1            |

## Configuration

- **Copilot version:** 1.336.0
- **IDE:** VS Code

## UX Summary

- Copilot shows a higher speed of code completion generation compared to Amazon Q, Gemini Code Assist, and Cursor.
- Chat with Gemini 2.5 Pro LLM generated answers more slowly compared to Amazon Q, Gemini Code Assist, and the chat with GPT-4o LLM.
- The Copilot copy button in the suggested code in the chat window often worked incorrectly and copied only part of the suggested code.

## Links

- [GitHub Copilot (GPT-4o) Code Assistant Sandbox Tests - March 2025](copilot-gpt4o-sandbox-tests-march-2025.md)
- [AI Code Assistants Leaderboard as of April 2025](../../../code-assistants-2025.md)

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
