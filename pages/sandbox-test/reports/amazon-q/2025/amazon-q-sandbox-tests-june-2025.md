# Amazon Q AI Code Assistant Sandbox Tests - June 2025

## Table of Contents
- [Summary](#summary)
- [Test Execution Results](#test-execution-results)
- [Score](#score)
- [Chat-Based Tests](#chat-based-tests)
- [Code Completion Tests](#code-completion-tests)
- [Configuration](#configuration)
- [UX Summary](#ux-summary)

## Summary

Compared to the Amazon Q results from [April 2025](amazon-q-sandbox-tests-april-2025.md), the chat-based test pass rate increased from **91.95%** to **94.25%**. However, the code completion pass rate decreased from **65%** to **54.41%**. This decrease can be attributed to the rise in the number of complex code completion tests, which increased from **60** to **68**.

As a result of the higher percentage of failed code completion tests, the overall pass rate decreased from **80.95%** to **76.77%** compared to the results from April 2025.

## Test Execution Results

[SandboxTestsAmazonQJune2025.xlsx](../../../../../reports/2025/SandboxTestsAmazonQJune2025.xlsx)

## Score

- **Overall Score:** 76.77% (36/155)
- **Chat-based tests score:** 94.25% (5/87)
- **Code completion tests score:** 54.41% (31/68)

## Chat-Based Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
| ------------- | ------------- | ------------ |
| 93.18         | 44            | 3            |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
| ------------- | ------------- | ------------ |
| 94.29         | 35            | 2            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
| ------------- | ------------- | ------------ |
| 100           | 8             | 0            |

*For about 30% of the chat-based tests, the default Amazon Q model was used. For the remaining tests, the Claude Sonnet 4 model was used after Amazon Q added the option to select a chat model (Claude 3.7 or Claude 4).*

## Code Completion Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
| ------------- | ------------- | ------------ |
| 42.50         | 40            | 23           |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
| ------------- | ------------- | ------------ |
| 75.00         | 20            | 5            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
| ------------- | ------------- | ------------ |
| 62.50         | 8             | 3            |

## Configuration

- **Amazon Q version:** 1.77.0
- **IDE:** VS Code

## UX Summary

Code completion is slower compared to Copilot—at least twice as slow. In some tests, no suggestions were generated at all.

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
