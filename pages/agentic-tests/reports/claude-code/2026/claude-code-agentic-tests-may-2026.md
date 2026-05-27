# Claude Code Agent Tests - May 2026

## Summary

This is a next round of agentic testing of Claude Code, a terminal-based coding agent from Anthropic. The agent has been tested with newest Claude Opus 4.7 model (1M context) with medium effort. It does not show significant improvement comparing with results obtained in November 2025 with Sonnet 4.5. Some tests have been passed better, but the overall result is about the same, slightly better than the six-month-old one.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

## Testing

### Environment

| | Version |
|---|---|
| Claude Code | 2.1.142 |
| Payment Plan | Enterprise |
| Default Model | Opus 4.7 (1M context) with medium effort |

## Code Generation Findings

- May generate unnecessary custom code replacing the library/framework capabilities.
- May suggest a simplified straightforward solution. It is laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions how to improve and/or fix the solution code.
- May try to read resources out of task scope. For instance: parent directory of project directory, user profile directory.
- Can get lost during work, in case of difficulties switching from the Bash tool set to the PowerShell tool set and vice versa.
- May mislead the developer by defending a previously made decision.

## Testing Customization

General golf-application rules for agents are added as file `.claude/CLAUDE.md`.

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0001/README.md` | N/A | 50%<br><br>- Schema validation failed: wrong column type.<br>- The application launch fails due to a database schema validation error.<br>- Testing could not be performed due to the failed application launch. | 83%<br><br>- The intended functionality is not accomplished.<br>- Exposes sensitive data in sources. | 1) Schema-validation: wrong column type encountered in column [gender] in table [player]; found [varchar (Types#VARCHAR)], but expecting [tinyint (Types#TINYINT)]<br><br>2) SchemaManagementException: Schema-validation: missing table [user]<br><br>3) Prevent user credentials expose in `docker-compose.yml`, `flyway.conf`. | 100% | 100% | Files:<br>2 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>405 insertions(+)<br>2 deletions(-) | |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See `agentic-workflow-tests/0003/README.md` | N/A | 100% | 100% | Not required | | | Files:<br>3 modified(M)<br>0 added(A)<br>1 deleted(D)<br><br>Lines:<br>28 insertions(+)<br>51 deletions(-) | |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See `agentic-workflow-tests/0004/README.md` | N/A | 52%<br><br>- The default RoundScoreController GET endpoint was not preserved, but restricted to "text/html".<br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 72%<br><br>- Custom CSV generation code does not handle edge cases, exceptions.<br>- CSV generation is embedded in the controller.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using StringBuilder is a poor and error-prone choice for CVS generation.<br><br>3) Regression: the default RoundScoreController GET endpoint is narrowed to "text/html" media type only. | 100% | 83%<br><br>- The CSV generation logic lacks necessary documentation. | Files:<br>2 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>128 insertions(+)<br>0 deletions(-) | |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0008/README.md` | N/A | 90%<br><br>- The application.properties still contains properties.<br>- The configuration uses a `<RandomAccessFile>` appender rather than a `<RollingRandomAccessFile>` appender.<br>- Log4j2 loggers are not configured as asynchronous. | 97%<br><br>- Logging within loop degrades performance. | 1) `logging.level.*` properties are not removed from application.properties. The created loggers are synchronous by default. It affects the logging performance.<br><br>2) Remove "org.springframework" logger.<br><br>3) Logging within loop degrades performance.<br><br>4) Would RollingRandomAccessFile be better for performance?<br><br>5) Replace RandomAccessFile with RollingRandomAccessFile.<br><br>6) Fix the issue, but keep the ability to configure log dir externally via LOG_DIR env var: WARN StatusConsoleListener Infinite loop in property interpolation of LOG_DIR->sys:LOG_DIR | 100% | 100% | Files:<br>7 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>112 insertions(+)<br>85 deletions(-) | |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See `agentic-workflow-tests/0011/README.md` | N/A | 100% | 94%<br><br>- Exposes sensitive data in sources. | 1) Remove plaintext credentials from comments in src/main/resources/data.sql. | 100% | 100% | Files:<br>2 modified(M)<br>2 added(A)<br>0 deleted(D)<br><br>Lines:<br>36 insertions(+)<br>24 deletions(-) | Minor: the solution relies on spring.sql.init.mode, it is not directly requested. |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See `agentic-workflow-tests/0014/README.md` | N/A | 75%<br><br>- The account menu does not expand downwards.<br>- Some tests could not be performed due to the menu expanding issue. | 86%<br><br>- The intended functionality is not accomplished. | 1) The account menu does not expand down on all pages. | 100% | 100% | Files:<br>2 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>31 insertions(+)<br>1 deletions(-) | |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0016/README.md` | N/A | 83%<br><br>- Using POST instead of DELETE HTTP method violates RESTful principles. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method.<br><br>2) Rewrite the competition deletion using HTTP `DELETE` method. | 100% | 100% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>13 insertions(+)<br>1 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **81%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 3 | 0.67 | 0.83 | 0.50 | 1.00 | 1.00 | 0.67 |
| 0003 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0004 | Local | 3 | 0.67 | 0.72 | 0.52 | 0.83 | 1.00 | 0.62 |
| 0008 | Local | 6 | 0.37 | 0.97 | 0.90 | 1.00 | 1.00 | 0.65 |
| 0011 | Local | 1 | 1.00 | 0.94 | 1.00 | 1.00 | 1.00 | 0.99 |
| 0014 | Local | 1 | 1.00 | 0.86 | 0.75 | 1.00 | 1.00 | 0.90 |
| 0016 | Local | 2 | 0.82 | 1.00 | 0.83 | 1.00 | 1.00 | 0.87 |

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
