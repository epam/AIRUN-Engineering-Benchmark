## Table of Contents

- [Summary](#summary)
- [Test Execution Results](#test-execution-results)
- [Score](#score)
- [Chat-Based Tests (Gemini 2.5 Flash)](#chat-based-tests-gemini-25-flash)
- [Code Completion Tests](#code-completion-tests)
- [Configuration](#configuration)
- [Links](#links)

## Summary

Compared to the Cursor results from [March 2025](cursor-gpt4o-sandbox-tests-march-2025.md) the code completion pass rate decreased from **71.67%** to **55.88%**. This decrease can be attributed to the rise in the number of complex code completion tests, which increased from **60** to **68**.

The pass rate for chat-based tests with Gemini 2.5 Flash model remains the same as the [March 2025 results with the GPT-4o](cursor-gpt4o-sandbox-tests-march-2025.md) (**88.51%**).

## Test Execution Results

[SandboxTestsCursorJune2025.xlsx](../../../../../reports/2025/SandboxTestsCursorGemini2.5FlashJune2025.xlsx)

## Score

- **Overall Score:** 74.19% (40/155)
- **Chat-based tests score:** 88.51% (10/87)
- **Code completion tests score:** 55.88% (30/68)

## Chat-Based Tests (Gemini 2.5 Flash)

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 84.09         | 44            | 7            |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 91.43         | 35            | 3            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 100           | 8             | 0            |

*The tests for the chat window were conducted using the Gemini 2.5 Flash model.*

## Code Completion Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 50.00         | 40            | 20           |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 65.00         | 20            | 7            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|:-------------:|:-------------:|:------------:|
| 62.50         | 8             | 3            |

## Configuration

- **Cursor version:** 1.1.5

## Links

- [Cursor (Gemini 2.5-pro-exp-03-25) AI Code Assistant Sandbox Tests - March 2025](cursor-gemini2.5-sandbox-tests-march-2025.md)
- [Cursor (Claude 3.7 Sonnet) AI Code Assistant Sandbox Tests - March 2025](cursor-sonnet3.7-sandbox-tests-march-2025.md)
- [Cursor (GPT-4o) AI Code Assistant Sandbox Tests - March 2025](cursor-gpt4o-sandbox-tests-march-2025.md)
- [AI Code Assistants Leaderboard as of April 2025](../../../code-assistants-2025.md)

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
