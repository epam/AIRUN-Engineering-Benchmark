# Claude Code Agent Tests - November 2025

## Table of Contents

- [Summary](#summary)
- [Testing](#testing)
    - [Environment](#environment)
    - [Code Generation Findings](#code-generation-findings)
    - [Test Report](#test-report)
- [Agent’s Final Grade](#agents-final-grade)
- [Plan Mode Examination](#plan-mode-examination)

# Summary
Anthropic Claude Code is a command line coding agent working in a terminal.

The new version of the agent showed better results than the May version and took a position among the leaders in agentic tests. The agent is now supported on Windows systems. Work with external tools has been improved. The user interface has also become more user-friendly. The interactive developer-manageable powerful and flexible plan mode allows to cope with large and complex tasks.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, and code-bugfixing.

# Testing

## Environment
|                   | Version                                  |
|-------------------|------------------------------------------|
| Claude Code       | 2.0.37                                   |
| Default Model     | claude-sonnet-4-5@20250929 (Thinking on) |
| Model Provider    | Google Vertex AI                         |

## Code Generation Findings
- May generate custom code instead of using the library/framework capabilities.
- Can create tests to verify the generated solution.
- Can ask clarifying questions.
- The agent allows a developer to control the solution generation process, giving the opportunity to confirm the suggested actions or ask to do them another way.
- In cases of complex and large tasks, the agent allows generating an implementation plan in plan mode first, reviewing it, and starting the solution generation thereafter. The agent tracks and processes the implementation plan phases reasonably.
- The agent partially fails to generate the necessary changes when working on complex and large tasks.

## Test Report

|   | Sourcecode Repository                                               | Task Summary                                                                                              | Task Description                                                                                                                                    | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy                      | Subsequent Prompts (Feedback, Comments)                                                                                     | Final Completeness | Final Accuracy       | Final Test Grade | Statistics                                                                                         | Comments |
|---|---------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|-------------------------|-------------------------------------|-----------------------------------------------------------------------------------------------------|-------------------|---------------------|-----------------|-----------------------------------------------------------------------------------------------------|----------|
| 1 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application)      | **Id:** 0001<br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br>**Category:** code-refactoring<br>**Complexity:** Medium | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md)                    | `N/A`              | 50%                     | 92% | 0) answer to question: Do not add Flyway dependency to pom.xml. Flyway migration should be called externally.<br>1) SchemaManagementException: Schema-validation... | 100%               | 100%                 | 85%             | Files: 1 modified(M), 6 added(A), 0 deleted(D) <br> Lines: 732 insertions(+), 1 deletion(-)                                               |          |
| 2 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application)      | **Id:** 0003<br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with OAuth2 Authorization<br>**Category:** code-refactoring<br>**Complexity:** High | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md)                    | `N/A`               | 100%                    | 100% | Not required                                                                                                    | —                 | —                   | 100%            | Files: 3 modified(M), 2 added(A), 0 deleted(D) <br> Lines: 284 insertions(+), 44 deletions(-)                                               |          |
| 3 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application)      | **Id:** 0004<br>**Name:** Return round scores in CSV format in Golf application<br>**Category:** solution-or-component-generation<br>**Complexity:** Low | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md)                    | `N/A`               | 52%                     | 72% | 1) Spring's message conversion mechanism is not utilized.<br>2) Using OutputStreamWriter is a poor and error-prone choice for CVS generation.<br> | 93%                | 83%                  | 67%             | Files: 3 modified(M), 2 added(A), 0 deleted(D) <br> Lines: 245 insertions(+), 2 deletions(-)                                                |          |
| 4 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application)      | **Id:** 0008<br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br>**Category:** solution-migration<br>**Complexity:** Medium | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md)                    | `N/A`               | 81%                     | 92% | 1) Log4j2 loggers are not asynchronous.<br>2) `logging.level.*` properties are not removed from application.properties.<br>3) RollingRandomAccessFile... | 100%               | 100%                 | 66%             | Files: 7 modified(M), 1 added(A), 2 deleted(D) <br>Lines: 124 insertions(+), 83 deletions(-)                                              |          |
| 5 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application)      | **Id:** 0011<br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br>**Category:** code-refactoring<br>**Complexity:** Low | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md)                    | `N/A`               | 82%                     | 88% | 1) Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version... | 100%               | 100%                 | 93%             | Files: 1 modified(M), 8 added(A), 0 deleted(D) <br>Lines: 688 insertions(+), 23 deletions(-)                                               |          |
| 6 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application)      | **Id:** 0014<br>**Name:** User Account Menu in Golf application<br>**Category:** solution-or-component-generation<br>**Complexity:** Low | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md)                    | `N/A`               | 86%                     | 92% | 1) The added account menu is not a dropdown menu, but separate main menu items.<br>2) The account menu does not expand down.<br>3) Bootstrap... | 100%               | 100%                 | 63%             | Files: 23 modified(M), 0 added(A), 0 deleted(D) <br> Lines: 88 insertions(+), 33 deletions(-)                                                |          |
| 7 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application)      | **Id:** 0016<br>**Name:** Fix an issue with competition removing in Golf application<br>**Category:** code-bugfixing<br>**Complexity:** Medium | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md)                    | `N/A`               | 83%                     | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method... | 100%               | 100%                 | 87%             | Files: 3 modified(M), 0 added(A), 0 deleted(D) <br> Lines: 14 insertions(+), 1 deletion(-)                                                  |          |

## Agent's Final Grade
The agent's final grade is 80%.

## Plan Mode Examination
Claude Code agent recommends using Plan Mode to prepare for a complex request before making changes.

The task-solving with the Plan mode has been examined on [agentic test 0007. Migrate Golf application to reactive stack](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0007/README.md).

The agent planning mode is powerful and flexible. A separate subagent is launched to create an implementation plan for the given task. The task is being broken down into manageable phases. The generated plan is suggested to the developer for review. The developer can ask to adjust the plan and pass it to the implementation.

The implementation is performed stage by stage. Each stage can be completed by launching a separate subagent allowing more efficient sub-task-solving within its context. The phase solution is accompanied by a comprehensive summary. After the stage is completed, the agent pauses, asks whether the implementation meets expectations, whether any adjustments should be made, or whether the next phase should be started. The developer is able to review the changes, provide feedback, and request further changes, and/or order the next phase solving.

The main agent successfully monitors the plan's implementation. At the same time, it allows the developer to control the solution generation process and intervene to make changes to the problem-solving process.

The generated solution is quite mature and subjectively better than competitors' solutions. However, it is not without its flaws and represents more of a solid draft, providing a firm foundation for further development.

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
