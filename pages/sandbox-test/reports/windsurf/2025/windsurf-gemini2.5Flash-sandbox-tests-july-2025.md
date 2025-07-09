# Windsurf (Gemini 2.5 Flash) AI Code Assistant Sandbox Tests - July 2025

## Table of Contents
- [Test execution results](#test-execution-results)
- [Summary](#summary)
    - [Chat based tests (Gemini 2.5 Flash)](#chat-based-tests-gemini-25-flash)
    - [Code completion tests](#code-completion-tests)
- [Configuration](#configuration)

## Summary

Compared to the Windsurf results from [April 2025](windsurf-sonnet3.7-sandbox-tests-april-2025.md) with the Claude 3.7 Sonnet model, the chat-based test pass rate decreased from **90.80%** to **80.46%** with Gemini 2.5 Flash model. The code completion pass rate also dropped from **50.00%** to **48.53%**. This decrease can be attributed to the rise in the number of complex code completion tests, which increased from **60** to **68**.

Overall, the pass rate decreased from **74.15%** to **66.45%** _compared to the results from March 2025._

## Test Execution Results

[SandboxTestsWindsurfGemini2.5FlashJuly2025.xlsx](../../../../../reports/2025/SandboxTestsWindsurfGemini2.5FlashJuly2025.xlsx)

## Score

- **Overall Score:** 66.45% (52/155)
- **Chat-based tests score:** 80.46% (17/87)
- **Code completion tests score:** 48.53% (35/68)

## Chat-Based Tests (Gemini 2.5 Flash)

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 77.27         | 44            | 10           |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 82.86         | 35            | 6            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 87.50         | 8             | 1            |

*The tests for the chat window were conducted using the Gemini 2.5 Flash model.*

## Code Completion Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 37.50         | 40            | 25           |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 70.00         | 20            | 6            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 50.00         | 8             | 4            |

## Configuration

- **Windsurf version:** 1.10.7

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
