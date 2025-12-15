# Copilot (Claude Opus 4.5) Agent Tests - December 2025

# Table of Contents

- [Summary](#summary)
- [Testing](#testing)
    - [Environment](#environment)
    - [Code Generation Findings](#code-generation-findings)
    - [Test Report](#test-report)
    - [Agent's Final Grade](#agents-final-grade)

## Summary

GitHub Copilot Agent is an integral part of GitHub Copilot Visual Studio Code extension.

The new agent version provides the newest Anthropic LLMs including Claude Opus 4.5, Claude Sonnet 4.5, Claude Haiku 4.5. The testing is performed with Claude Opus 4.5.

GitHub Copilot has shown excellent results and will be among the top three based on testing results. However, the developer must carefully review the proposed solutions to identify shortcomings and address them, or, in case of simplified straightforward solution, drive the development in right technical direction.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing.

## Testing

### Environment

|                      | Version                                  |
|----------------------|------------------------------------------|
| GitHub Copilot Extension | 0.33.4                              |
| VS Code              | Version: 1.106.3 (system setup)         |
| Default Model        | Claude Opus 4.5 (Preview)               |
| Run Mode             | Agent                                   |

### Code Generation Findings

- Able to suggest reasonable advice to apply database schema scripts (instead of run the script itself through trial and error).
- Can suggest simplified straightforward solutions.
- May generate custom code instead of using the library/framework capabilities.

### Test Report

| # | Sourcecode Repository | Task Summary (Name/Category/Complexity) | Task Description (Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts (Feedback, Comments) | Final Completeness | Final Accuracy | Final Test Grade | Statistics | Comments |
|---|------------------------|------------------------------------------|-----------------------------------|--------------------|-------------------------|---------------------|------------------------------------------|--------------------|---------------|------------------|-----------|----------|
| 1 | <https://github.com/PolinaTolkachova/golf-application> | **Id:** 0001<br>**Name**: Make reverse engineering of DB schema and make it manageable with Flyway<br>**Category**: code-refactoring<br>**Complexity**: Medium | See <https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md> | N/A | 35%<br>- Application startup failed with Schema-validation error.<br>- Hibernate configuration is not changed from updating database schema to validating database schema.<br>- The application failed to launch.<br>- Tests could not be performed due to the failed app launch. | 92%<br>- The intended functionality is not accomplished. | 1) Container logs show an initialization error during `/docker-entrypoint-initdb.d/01-init.sql`: “ERROR 1410 (42000): You are not allowed to create a user with GRANT.”<br>2) `01-init.sql` is useless.<br>3) `SchemaManagementException: Schema-validation: wrong column type encountered in column [gender] in table [player]; found [varchar (Types#VARCHAR)], but expecting [tinyint (Types#TINYINT)]`<br>4) Configure Hibernate to validate database schema. | 100% | 100% | 59% | Files:<br>1 modified(M)<br>5 added(A)<br>0 deleted(D)<br><br>Lines:<br>587 insertions(+)<br>1 deletions(-) |  |
| 2 | <https://github.com/PolinaTolkachova/golf-application> | **Id:** 0003<br>**Name**: Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br>**Category**: code-refactoring<br>**Complexity**: High | See <https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md> | N/A | 100% | 100% | Not required |  |  | 100% | Files:<br>3 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>114 insertions(+)<br>42 deletions(-) |  |
| 3 | <https://github.com/PolinaTolkachova/golf-application> | **Id:** 0004<br>**Name**: Return round scores in CSV format in Golf application<br>**Category**: solution-or-component-generation<br>**Complexity**: Low | See <https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md> | N/A | 59%<br>- Spring HTTP Message Conversion is not utilized.<br>- No CSV library used. | 72%<br>- CSV is built manually with StringBuilder.<br>- The code does not address CSV generation edge properly.<br>- CSV generation is embedded in the controller.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized.<br>2) Using PrintWriter is a poor and error-prone choice for CSV generation. | 100% | 83%<br>- The CSV generation logic lacks necessary documentation. | 70% | Files:<br>3 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>131 insertions(+)<br>1 deletions(-) |  |
| 4 | <https://github.com/PolinaTolkachova/golf-application> | **Id:** 0008<br>**Name**: Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br>**Category**: solution-migration<br>**Complexity**: Medium | See <https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md> | N/A | 79%<br>- `logging.level.*` properties are not removed from application.properties.<br>- Log4j2 logging is not fully asynchronous, only async appenders are used.<br>- LMAX Disruptor is not utilized.<br>- RollingFile is configured instead of RollingRandomAccessFile.<br>- Log4j2 loggers are not asynchronous.<br>- Incorrect Log4j2 configuration: Infinite loop in property interpolation of `LOG_DIR->sys:LOG_DIR`. | 83%<br>- The intended functionality is not fully accomplished: migration to Log4j2 has been completed, but performance optimization is not finished.<br>- Unrequested `org.hibernate.SQL` logger is configured. | 1) `logging.level.*` properties are not removed from application.properties. The created loggers are synchronous by default. It affects the logging performance.<br>2) Ensure logging is fully asynchronous in Log4j2 configuration.<br>3) Enable fully async logging using LMAX Disruptor with properties, not by hardcoding system property in `GolfWebApplication.java`.<br>4) Would `RollingRandomAccessFile` be better for performance?<br>5) WARN StatusConsoleListener Infinite loop in property interpolation of `LOG_DIR->sys:LOG_DIR`. | 100% | 92%<br>- Unrequested `org.hibernate.SQL` logger is configured. | 62% | Files:<br>7 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>121 insertions(+)<br>81 deletions(-) |  |
| 5 | <https://github.com/PolinaTolkachova/golf-application> | **Id:** 0011<br>**Name**: Migrate in-memory user and role definitions to database in Golf application<br>**Category**: code-refactoring<br>**Complexity**: Low | See <https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md> | N/A | 94%<br>- The unique index for AUTHORITIES table for username, authority is not created. | 91%<br>- The SQL migration script contains a MySQL syntax error.<br>- Exposes plaintext credentials in source code. | 1) Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near `IF NOT EXISTS ix_auth_username ON authorities (username, authority)`.<br>2) Remove plaintext credentials from comments in `V1__spring_security_schema_and_users.sql`. | 100% | 100% | 87% | Files:<br>1 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>42 insertions(+)<br>23 deletions(-) |  |
| 6 | <https://github.com/PolinaTolkachova/golf-application> | **Id:** 0014<br>**Name**: User Account Menu in Golf application<br>**Category**: solution-or-component-generation<br>**Complexity**: Low | See <https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md> | N/A | 94%<br>- Bootstrap bundle is missed on some pages with account menu. | 92%<br>- The intended functionality is not fully accomplished. | 1) The account menu does not expand down on "Your Round Score Page", "EDIT COMPETITION" page, "ADD COMPETITION ROUND" page, "ADD COMPETITION" page, "ADD COURSE" page.<br>2) The account menu still does not expand down on "Your Round Score Page".<br>3) It has not helped. The account menu still does not expand down on "Your Round Score Page".<br>4) It has not helped. The account menu still does not expand down on "Your Round Score Page".<br>5) The account menu does not expand down on "Enter Your Round score" page. | 100% | 100% | 69% | Files:<br>10 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>210 insertions(+)<br>107 deletions(-) |  |
| 7 | <https://github.com/PolinaTolkachova/golf-application> | **Id:** 0016<br>**Name**: Fix an issue with competition removing in Golf application<br>**Category**: code-bugfixing<br>**Complexity**: Medium | See <https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md> | N/A | 83%<br>- The implementation uses POST method instead of DELETE HTTP method for competition deletion. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method.<br>2) Please rewrite competition deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")`. | 100% | 100% | 87% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>11 insertions(+)<br>1 deletions(-) |  |

### Agent's Final Grade

The agent's final grade is **76%**.

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
