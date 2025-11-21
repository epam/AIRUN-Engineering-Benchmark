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

| # | Sourcecode Repository | Task Summary<br/>Name/Category/Complexity | Task Description<br/>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br/>(Feedback, Comments) | Final Completeness | Final Accuracy | Final Test Grade | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | **Id:** 0001<br/>**Name**: Make reverse engineering of DB schema and make it manageable with Flyway<br/>**Category**: code-refactoring<br/>**Complexity**: Medium | See [agentic-workflow-tests/0001/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md) | N/A | 50%<br/>- The application failed schema validation: incorrect column type.<br/>- The application launch failed due to schema-validation error.<br/>- Tests could not be performed due to the failed app launch. | 92%<br/>- The intended functionality is not accomplished. | 0) answer to question:<br/>Do not add flyway dependency to pom.xml. Flyway migration should be called externally.<br/><br/>1)<br/>SchemaManagementException: Schema-validation: wrong column type encountered in column [gender] in table [player]; found [varchar (Types#VARCHAR)], but expecting [tinyint (Types#TINYINT)] | 100% | 100% | 85% | Files:<br/>1 modified(M)<br/>6 added(A)<br/>0 deleted(D)<br/><br/>Lines:<br/>732 insertions(+)<br/>1 deletions(-) | |
| 2 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | **Id:** 0003<br/>**Name**: Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br/>**Category**: code-refactoring<br/>**Complexity**: High | See [agentic-workflow-tests/0003/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md) | N/A | 100% | 100% | Not required | | | 100% | Files:<br/>3 modified(M)<br/>2 added(A)<br/>0 deleted(D)<br/><br/>Lines:<br/>284 insertions(+)<br/>44 deletions(-) | |
| 3 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | **Id:** 0004<br/>**Name**: Return round scores in CSV format in Golf application<br/>**Category**: solution-or-component-generation<br/>**Complexity**: Low | See [agentic-workflow-tests/0004/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md) | N/A | 52%<br/>- Minor: The default RoundScoreController GET endpoint modified to support HTML only.<br/>- Spring HTTP Message Conversion is not utilized.<br/>- The code does not utilize a proven CSV processing library to write CSV. | 72%<br/>- The code does not handle edge cases for CSV generation.<br/>- CSV generation is embedded in the controller.<br/>- The CSV generation logic lacks necessary documentation. | 1)<br/>Spring's message conversion mechanism is not utilized.<br/><br/>2)<br/>Using OutputStreamWriter is a poor and error-prone choice for CVS generation. | 93%<br/>- Minor: The default RoundScoreController GET endpoint modified to support HTML only. | 83%<br/>- The CSV generation logic lacks necessary documentation. | 67% | Files:<br/>3 modified(M)<br/>2 added(A)<br/>0 deleted(D)<br/><br/>Lines:<br/>245 insertions(+)<br/>2 deletions(-) | |
| 4 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | **Id:** 0008<br/>**Name**: Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br/>**Category**: solution-migration<br/>**Complexity**: Medium | See [agentic-workflow-tests/0008/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md) | N/A | 81%<br/>- LMAX Disruptor dependency is not added.<br/>- `logging.level.*` properties are not removed from application.properties.<br/>- `logging.properties` is not deleted.<br/>- Logging is not fully asynchronous in Log4j2 configuration.<br/>- RollingRandomAccessFile appender is not used in Log4j2 configuration. | 92%<br/>- The intended functionality is not fully accomplished. | 1)<br/>Log4j2 loggers are not asynchronous.<br/><br/>2)<br/>`logging.level.*` properties are not removed from application.properties.<br/><br/>3)<br/>Would RollingRandomAccessFile be better for performance?<br/><br/>4)<br/>WARN StatusConsoleListener Infinite loop in property interpolation of LOG_DIR->sys:LOG_DIR<br/><br/>5)<br/>`logging.properties` is not deleted | 100% | 100% | 66% | Files:<br/>7 modified(M)<br/>1 added(A)<br/>2 deleted(D)<br/><br/>Lines:<br/>124 insertions(+)<br/>83 deletions(-) | |
| 5 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | **Id:** 0011<br/>**Name**: Migrate in-memory user and role definitions to database in Golf application<br/>**Category**: code-refactoring<br/>**Complexity**: Low | See [agentic-workflow-tests/0011/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md) | N/A | 82%<br/>- Users can not login after migration. | 88%<br/>- The intended functionality is not accomplished.<br/>- SQL syntax error. | 1)<br/>Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'IF NOT EXISTS ix_auth_username ON authorities (username, authority)' at line 1<br/>SQLState: 42000<br/>ErrorCode: 1064<br/>Error occurred in:<br/>CREATE INDEX IF NOT EXISTS ix_auth_username ON authorities (username, authority) | 100% | 100% | 93% | Files:<br/>1 modified(M)<br/>8 added(A)<br/>0 deleted(D)<br/><br/>Lines:<br/>688 insertions(+)<br/>23 deletions(-) | |
| 6 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | **Id:** 0014<br/>**Name**: User Account Menu in Golf application<br/>**Category**: solution-or-component-generation<br/>**Complexity**: Low | See [agentic-workflow-tests/0014/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md) | N/A | 86%<br/>- The Bootstrap JavaScript bundle required for the dropdown to work is not added.<br/>- The account menu is not a dropdown menu, but separate main menu items.<br/>- An user is redirected to unused sign in page instead of actual login page after logout. | 92%<br/>- The intended functionality is not fully accomplished. | 1)<br/>The added account menu is not a dropdown menu, but separate main menu items.<br/><br/>2)<br/>The account menu does not expand down.<br/><br/>3)<br/>Bootstrap supports creation of dropdowns and does not need any extra custom scripts.<br/><br/>Answer to clarifying question:<br/>Update the other template pages to remove the Bootstrap 3 JS references.<br/><br/>4)<br/>The account menu does not expand down anyway.<br/><br/>5)<br/>The account menu still does not expand down on "Your Round Score Page", "EDIT COMPETITION" page, "ADD COMPETITION ROUND" page, "ADD COURSE" page.<br/><br/>6)<br/>An user is redirected to unused sign in page instead of actual login page after logout. | 100% | 100% | 63% | Files:<br/>23 modified(M)<br/>0 added(A)<br/>0 deleted(D)<br/><br/>Lines:<br/>88 insertions(+)<br/>33 deletions(-) | |
| 7 | [https://github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | **Id:** 0016<br/>**Name**: Fix an issue with competition removing in Golf application<br/>**Category**: code-bugfixing<br/>**Complexity**: Medium | See [agentic-workflow-tests/0016/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md) | N/A | 83%<br/>- The solution uses POST HTTP method for competition deletion instead of DELETE | 100% | 1)<br/>The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method<br/><br/>2)<br/>Please rewrite competition deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")` | 100% | 100% | 87% | Files:<br/>3 modified(M)<br/>0 added(A)<br/>0 deleted(D)<br/><br/>Lines:<br/>14 insertions(+)<br/>1 deletions(-) | |

## Agent's Final Grade
The agent's final grade is 80%.

## Plan Mode Examination
Claude Code agent recommends using Plan Mode to prepare for a complex request before making changes.

The task-solving with the Plan mode has been examined on [agentic test 0007. Migrate Golf application to reactive stack](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/tree/main/agentic-workflow-tests/0007).

The agent planning mode is powerful and flexible. A separate subagent is launched to create an implementation plan for the given task. The task is being broken down into manageable phases. The generated plan is suggested to the developer for review. The developer can ask to adjust the plan and pass it to the implementation.

The implementation is performed stage by stage. Each stage can be completed by launching a separate subagent allowing more efficient sub-task-solving within its context. The phase solution is accompanied by a comprehensive summary. After the stage is completed, the agent pauses, asks whether the implementation meets expectations, whether any adjustments should be made, or whether the next phase should be started. The developer is able to review the changes, provide feedback, and request further changes, and/or order the next phase solving.

The main agent successfully monitors the plan's implementation. At the same time, it allows the developer to control the solution generation process and intervene to make changes to the problem-solving process.

The generated solution is quite mature and subjectively better than competitors' solutions. However, it is not without its flaws and represents more of a solid draft, providing a firm foundation for further development.

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
