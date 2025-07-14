# Zencoder (Claude 3.7 Sonnet) AI Code Assistant Sandbox Tests - July 2025

## Table of Contents
- [Test execution results](#test-execution-results)
- [Summary](#summary)
   - [Chat based tests (Claude 3.7 Sonnet)](#chat-based-tests-claude-37-sonnet)
   - [Code completion tests](#code-completion-tests)
- [Configuration](#configuration)

## Summary

Zencoder showed low performance on the code completion test (**23.53%**). However, C# test performance (**45%**) was much better than that of the Java and TypeScript tests (**12.50%** and **15%**, respectively).

In contrast, Zencoder demonstrated high performance on the chat-based test (**90.80%**).

## Test Execution Results

[SandboxTestsZencoderSonnet3.7July2025.xlsx](../../../../../reports/2025/SandboxTestsZencoderSonnet3.7July2025.xlsx)

## Score

- **Overall Score:** 61.29% (60/155)
- **Chat-based tests score:** 90.80% (8/87)
- **Code completion tests score:** 23.53% (52/68)

## Chat-Based Tests (Claude 3.7 Sonnet)

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 88.64         | 44            | 5            |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 91.43         | 35            | 3            |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 100           | 8             | 0            |

*The tests for the chat window were conducted using the Claude 3.7 Sonnet model.*

## Code Completion Tests

**Java:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 15.00         | 40            | 34           |

**C#:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 45.00         | 20            | 11           |

**TypeScript:**

| Pass Rate (%) | Tests (Total) | Failed Tests |
|---------------|---------------|--------------|
| 12.50         | 8             | 7            |

## Configuration

- **Zencoder version:** 2.14.3
- **IDE:** VS Code

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
