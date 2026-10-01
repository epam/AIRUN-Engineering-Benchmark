# Codex Agent Tests — September 2026

## Summary

This is a next round of agentic testing of Codex, coding agent embedded into ChatGPT desktop application. The agent has been tested with newest GPT-6 Astra with medium effort. It shows significant improvement comparing with results obtained in November 2025 with GPT-5-Codex.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

## Testing

### Environment

| | Version |
|---|---|
| ChatGPT desktop app | 26.917.71314 |
| Payment Plan | Plus |
| Default Model | GPT-6 Astra (medium) |
| Run Mode | Agent |

## Code Generation Findings

- Creates tests to validate the generated solution. But often follows the Mirror Testing anti-pattern and creates tests reflecting exactly what the code currently does rather than validating the expected behavior.
- May generate unnecessary custom code replacing the library/framework capabilities.
- May suggest a simplified straightforward solution. It is laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions how to improve and/or fix the solution code.

## Testing Customization

General golf-application rules for agents are added as file `AGENTS.md`.

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0001/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md) | N/A | 50%<br><br>- The database schema validation could be performed due to the failed application launch.<br>- The application failed to launch.<br>- Tests could not be performed due to the failed application launch. | 92%<br><br>- The intended functionality is not accomplished. | 1) Mysql container port is narrowed to "127.0.0.1:${MYSQL_PORT:-3306}:3306". Make a correction to allow connections from other machines.<br><br>2) The database name is hardcoded in compose.yaml, thus it doesn't seem flexible enough to suit all users and applicable in various environments. | 100% | 100% | Files:<br>2 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>546 insertions(+)<br>7 deletions(-) | |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See [agentic-workflow-tests/0003/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md) | N/A | 100% | 100% | | | | Files:<br>4 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>152 insertions(+)<br>43 deletions(-) | |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0004/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md) | N/A | 52%<br><br>- The default RoundScoreController GET endpoint was not preserved.<br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 72%<br><br>- Custom CSV generation code does not handle edge cases, exceptions.<br>- CSV generation is embedded in the controller.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using StringBuilder is a poor and error-prone choice for CVS generation. | 100% | 83%<br><br>- The CSV generation logic lacks necessary documentation. | Files:<br>2 modified(M)<br>4 added(A)<br>0 deleted(D)<br><br>Lines:<br>233 insertions(+)<br>1 deletions(-) | |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0008/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md) | N/A | 90%<br><br>- Missed "com.golf.app" logger in Log4j2 configuration.<br>- Missed "org.springframework.web" logger in Log4j2 configuration.<br>- The file appender is set up as a RandomAccessFileAppender rather than a RollingRandomAccessFileAppender. | 97%<br><br>- The intended functionality is not fully accomplished. Migration is done somehow, but the optimization is not.<br>- Logging within loop degrades performance. | 1) Missed "org.springframework.web" logger in Log4j2 configuration.<br><br>2) Missed "com.golf.app" logger in Log4j2 configuration.<br><br>3) Logging within loop degrades performance.<br><br>4) Explicit loggers are synchronous by default.<br><br>5) Would RollingRandomAccessFile be better for performance?<br><br>6) Use RollingRandomAccessFile as file appender. | 100% | 100% | Files:<br>9 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>188 insertions(+)<br>86 deletions(-) | |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See [agentic-workflow-tests/0011/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md) | N/A | 100% | 94%<br><br>- Exposes sensitive data in sources. | 1) Remove the application users plaintext credentials from the codebase. | 100% | 100% | Files:<br>2 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>23 insertions(+)<br>16 deletions(-) | |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0014/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md) | N/A | 49%<br><br>- The dependency org.thymeleaf.extras:thymeleaf-extras-springsecurity6 is not added.<br>- Thymeleaf security is not utilized.<br>- Bootstrap bundle is not properly utilized to create the account menu.<br>- The account menu is conditionally rendered via th:if, but it does not use the sec:authorize attribute with isAuthenticated().<br>- The username is published with a custom attribute injected by custom advice. | 96%<br><br>- Custom CSS is generated instead of using Bootstrap adopted in the project. | 1) Utilize Thymeleaf security in the implementation instead of custom code.<br><br>2) Rework the implementation using Bootstrap adopted in the project instead of custom CSS. | 100% | 100% | Files:<br>8 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>109 insertions(+)<br>10 deletions(-) | |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0016/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md) | N/A | 83%<br><br>- Using POST instead of DELETE HTTP method violates RESTful principles. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method.<br><br>2) Please rewrite deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")`. | 100% | 100% | Files:<br>3 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>73 insertions(+)<br>2 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **82%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 2 | 0.82 | 0.92 | 0.50 | 1.00 | 1.00 | 0.76 |
| 0003 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0004 | Local | 2 | 0.82 | 0.72 | 0.52 | 0.83 | 1.00 | 0.68 |
| 0008 | Local | 6 | 0.37 | 0.97 | 0.90 | 1.00 | 1.00 | 0.65 |
| 0011 | Local | 1 | 1.00 | 0.94 | 1.00 | 1.00 | 1.00 | 0.99 |
| 0014 | Local | 2 | 0.82 | 0.97 | 0.49 | 1.00 | 1.00 | 0.77 |
| 0016 | Local | 2 | 0.82 | 1.00 | 0.83 | 1.00 | 1.00 | 0.87 |

## Links

- [ChatGPT Codex home](https://chatgpt.com/codex/)

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
