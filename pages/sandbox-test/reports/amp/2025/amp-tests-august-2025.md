# Amp (Sourcegraph) Code Assistant Test Execution Results - August 2025

## Table of Contents

- [Final Score - Chat-Based Tests (Golf App + Sandbox Tests)](#final-score---chat-based-tests-golf-app--sandbox-tests)
- [Sandbox Test Execution Results](#sandbox-test-execution-results)
    - [Summary Scores](#summary-scores)
    - [Chat-Based Tests Results](#chat-based-tests-results)
    - [Code Completion Tests Results](#code-completion-tests-results)
    - [Configuration](#configuration)
    - [User Experience Summary](#user-experience-summary)
- [Golf App Test Execution Results](#golf-app-test-execution-results)
    - [Chat-Based Tests Results](#chat-based-tests-results-1)
    - [Configuration](#configuration-1)

## Final Score - Chat-Based Tests (Golf App + Sandbox Tests)

- **Overall Pass Rate:** 94.50% (6 failed out of 109 tests)

## Sandbox Test Execution Results

**Report file:**  
[SandboxTestsAmazonQApril2025.xlsx](../../../../../reports/2025/SandboxTestsAmpAugust2025.xlsx)

### Summary Scores

- **Overall Pass Rate:** 76.77% (36 failed out of 155 tests)
- **Chat-Based Tests Pass Rate:** 95.40% (4 failed out of 87 tests)
- **Code Completion Tests Pass Rate:** 52.94% (32 failed out of 68 tests)

### Chat-Based Tests Results

| Language   | Pass Rate (%) | Total Tests | Failed Tests |
|------------|---------------|-------------|--------------|
| Java       | 95.45         | 44          | 2            |
| C#         | 94.29         | 35          | 2            |
| TypeScript | 100.00        | 8           | 0            |

*Note: Amp currently [uses Claude Sonnet 4](https://ampcode.com/manual#how-to-prompt) for most tasks.*

### Code Completion Tests Results

| Language   | Pass Rate (%) | Total Tests | Failed Tests |
|------------|---------------|-------------|--------------|
| Java       | 45.00         | 40          | 22           |
| C#         | 70.00         | 20          | 6            |
| TypeScript | 50.00         | 8           | 4            |

### Configuration

- **Amp version:** 0.0.1754022583 (Research preview)

### User Experience Summary

- Chat responses were generated at a moderate speed compared to other AI code assistants.
- Code completion worked quickly.
- No plugin errors were encountered during testing.
- The cost to run 155 tests was approximately $10.

## Golf App Test Execution Results

**Report file:**  
[SandboxTestsAmazonQApril2025.xlsx](../../../../../reports/2025/GolfAppTestsAmpJuly2025.xlsx)

### Chat-Based Tests Results

| Language | Pass Rate (%) | Total Tests | Failed Tests |
|----------|---------------|-------------|--------------|
| Java     | 90.91         | 22          | 2            |

*Note: Amp currently [uses Claude Sonnet 4](https://ampcode.com/manual#how-to-prompt) for most tasks.*

### Configuration

- **Amp version:** 0.0.1752221392 (Research preview)

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
