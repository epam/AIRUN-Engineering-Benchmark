# Gemini AI Code Assistant Sandbox Tests - June 2025

## Table of Contents

- [Summary](#summary)
- [Test Execution Results](#test-execution-results)
- [Score](#score)
- [Chat-Based Tests](#chat-based-tests)
- [Code Completion Tests](#code-completion-tests)
- [Configuration](#configuration)
- [UX Summary](#ux-summary)
- [Links](#links)

## Summary

Compared to the Gemini Code Assist results from [April 2025](gemini-sandbox-tests-april-2025.md), the chat-based test pass rate decreased from **91.95%** to **85.05%**. The code completion pass rate also dropped from **70%** to **41.18%**. This decrease can be attributed to the rise in the number of complex code completion tests, which increased from **60** to **68**.

Overall, the pass rate decreased from **82.99%** to **65.81%** compared to the results from April 2025.

## Test Execution Results

[SandboxTestsGeminiJune2025.xlsx](../../../../../reports/2025/SandboxTestsGeminiJune2025.xlsx)

## Score

- **Overall Score:** 65.81% (53/155)
- **Chat-based tests score:** 85.05% (13/87)
- **Code completion tests score:** 41.18% (40/68)

## Chat-Based Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|:-------------:|-------------:|
| 84.09         | 44            | 7            |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|:-------------:|-------------:|
| 85.71         | 35            | 5            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|:-------------:|-------------:|
| 87.50         | 8             | 1            |

## Code Completion Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|:-------------:|-------------:|
| 37.50         | 40            | 25           |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|:-------------:|-------------:|
| 40.00         | 20            | 12           |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|:-------------:|-------------:|
| 62.50         | 8             | 3            |

## Configuration

- **Gemini Code Assist version:** 2.37.0
- **IDE:** VS Code

## UX Summary

- Gemini Code Assist code completion is noticeably slower than Copilot, Amazon Q, and Cursor.

## Links

- [Gemini AI Code Assistant Sandbox Tests - April 2025](gemini-sandbox-tests-april-2025.md)
- [AI Code Assistants Leaderboard as of April 2025](../../../code-assistants-2025.md)

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
