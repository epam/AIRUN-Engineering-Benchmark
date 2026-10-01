# Google Antigravity Agent Tests — September 2026

## Summary

This is a next round of agentic testing of Antigravity, LLM-backed IDE from Google. It has been tested with Gemini 3.1 Pro with high effort. It shows the same results to results obtained in March 2026 with the same model.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

## Testing

### Environment

| | Version |
|---|---|
| Google Antigravity | 2.17.0 |
| Default Model | Gemini 3.1 Pro (high) |
| Run Mode | Agent |

## Code Generation Findings

- The permission request system is unintuitive and fiddly, requires too many approves without clear options to make approves of generic actions.
- Can suggest a simplified straightforward solutions, prefers to make rash decisions rather than probe deeply into the problem.
- May forget to clean up the code from utility tools used for auxiliary purposes.
- Can switch to non-existent tool and try to use it instead of proper one. For instance, switch to non-existent Maven wrapper instead of globally available Maven CLI.

## Testing Customization

General golf-application rules for agents are added as file `AGENTS.md`.

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0001/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md) | N/A | 85%<br><br>- Hibernate configuration is not changed from updating database schema to validating database schema. | 94%<br><br>- Exposes sensitive data in sources. | 1) Hibernate configuration is not changed from updating database schema to validating database schema.<br><br>2) Prevent user credentials expose in docker-compose.yml, flyway.conf.<br><br>3) Flyway's native configuration files do not support Bash-style default value fallbacks like ${VAR_NAME:-default}.<br><br>4) Using the root user as the application database user leads to security risks. | 100% | 100% | Files:<br>1 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>341 insertions(+)<br>2 deletions(-) | |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See [agentic-workflow-tests/0003/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md) | N/A | 66%<br><br>- The authorization server URI is not configured.<br>- The application launch fails due to missing authorization server configuration.<br>- Testing could not be performed due to the failed application launch. | 88%<br><br>- The intended functionality is not accomplished.<br>- Auth configuration is not finished. | 1) Add the external authorization server configuration. | 100% | 100% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>12 insertions(+)<br>41 deletions(-) | |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0004/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md) | N/A | 48%<br><br>- Null values are not correctly represented as empty strings.<br>- The data field containing the comma is enclosed in double quotes.<br>- The double quote contained in the data field is escaped by doubling it.<br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 63%<br><br>- The intended functionality is not fully accomplished.<br>- Custom CSV generation code does not handle edge cases, exceptions.<br>- CSV generation is embedded in the controller.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using OutputStreamWriter is a poor and error-prone choice for CVS generation. | 100% | 83%<br><br>- The CSV generation logic lacks necessary documentation. | Files:<br>2 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>92 insertions(+)<br>0 deletions(-) | |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0008/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md) | N/A | 90%<br><br>- application.properties still contains logging level configurations.<br>- The logging is not fully asynchronous in Log4j2 configuration.<br>- The file appender in the configuration is defined as a File appender rather than as a RollingRandomAccessFile appender.<br>- There are synchronous Log4j2 loggers.<br>- The logging calls use string concatenation instead of parameterized messages. | 88%<br><br>- The intended functionality is not accomplished.<br>- Logging within loop degrades performance. | 1) `logging.level.*` properties are not removed from application.properties. The created loggers are synchronous by default. It affects the logging performance.<br><br>2) Would RollingRandomAccessFile be better for performance?<br><br>3) Logging within loop degrades performance.<br><br>4) Restore the player name logging, but check is logging level enabled.<br><br>5) Fix, but keep using env var LOG_DIR: WARN StatusConsoleListener Infinite loop in property interpolation of LOG_DIR->sys:LOG_DIR<br><br>6) The logging calls in the controllers use string concatenation rather than parameterized messages. | 100% | 100% | Files:<br>7 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>96 insertions(+)<br>81 deletions(-) | |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See [agentic-workflow-tests/0011/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md) | N/A | 76%<br><br>- There is a syntax error in MySQL script creating the unique index for AUTHORITIES table for username, authority.<br>- Users could not login with their credentials. | 61%<br><br>- The intended functionality is not accomplished.<br>- The generated SQL code contains the syntax error.<br>- Exposes sensitive data in sources. | 1) Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'IF NOT EXISTS ix_auth_username ON authorities (username, authority)'.<br><br>2) Remove the application users plaintext credentials. | 100% | 100% | Files:<br>1 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>39 insertions(+)<br>24 deletions(-) | |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0014/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md) | N/A | 90%<br><br>- Bootstrap bundle is not utilized to create the account menu.<br>- The account menu is not expandable sub-menu but just raw main menu elements. | 92%<br><br>- The intended functionality is not fully accomplished. | 1) The account menu is not expandable sub-menu but just a few main menu elements.<br><br>2) The account menu does not expand downwards on all pages. | 100% | 100% | Files:<br>2 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>35 insertions(+)<br>9 deletions(-) | |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0016/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md) | N/A | 83%<br><br>- Using POST instead of DELETE HTTP method violates RESTful principles. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method. | 100% | 100% | Files:<br>4 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>10 insertions(+)<br>1 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **77%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 4 | 0.55 | 0.94 | 0.85 | 1.00 | 1.00 | 0.72 |
| 0003 | Local | 1 | 1.00 | 0.88 | 0.66 | 1.00 | 1.00 | 0.89 |
| 0004 | Local | 2 | 0.82 | 0.63 | 0.48 | 0.83 | 1.00 | 0.65 |
| 0008 | Local | 6 | 0.37 | 0.88 | 0.90 | 1.00 | 1.00 | 0.63 |
| 0011 | Local | 2 | 0.82 | 0.61 | 0.76 | 1.00 | 1.00 | 0.75 |
| 0014 | Local | 2 | 0.82 | 0.92 | 0.90 | 1.00 | 1.00 | 0.86 |
| 0016 | Local | 2 | 0.82 | 1.00 | 0.83 | 1.00 | 1.00 | 0.87 |

## Links

- [Google Antigravity home](https://antigravity.google)

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
