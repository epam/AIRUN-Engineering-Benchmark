# Cursor Agent Tests — September 2026

## Summary

This is a next round of agentic testing of Cursor, agentic IDE built as a fork of Visual Studio Code. The agent has been tested with newest Claude Opus 5.5 with high effort. It shows significant improvement comparing with results obtained in February 2026 with Opus 4.6.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

## Testing

### Environment

| | Version |
|---|---|
| Cursor | 3.21.16 |
| Payment Plan | Enterprise |
| Default Model | Claude Opus 5.5 High |
| Run Mode | Agent |

## Code Generation Findings

- Mostly miss to provide the necessary instructions for running developed feature.
- May generate unnecessary custom code replacing the library/framework capabilities.
- May suggest a simplified straightforward solution.
- Performs gap analysis after finishing the task where reveals shortcomings and identifies areas that need attention.
- Creates tests to validate the generated solution. But often follows the Mirror Testing anti-pattern and creates tests reflecting exactly what the code currently does rather than validating the expected behavior.
- Suggest a quick review of committed changes: Run a local Bugbot review of your latest changes to catch issues before they ship.

## Testing Customization

General golf-application rules for agents are added as file `AGENTS.md`.

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0001/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md) | N/A | 34%<br><br>- DB migration has not been applied successfully.<br>- A schema-validation error (missing table 'competition') indicating that schema validation failed.<br>- The Flyway migration failed due to inability to load the JDBC driver.<br>- The application fails to launch due to a schema validation error.<br>- Tests could not be performed due to the failed application launch. | 86%<br><br>- The intended functionality is not accomplished.<br>- Exposes sensitive data in sources. | 1) docker compose run --rm flyway migrate<br><br>ERROR: Unable to instantiate JDBC driver: com.mysql.cj.jdbc.Driver => Check whether the jar file is presentFailure probably due to inability to load dependencies. Please ensure you have downloaded 'https://dev.mysql.com/downloads/connector/j/' and extracted to 'flyway/drivers' folder Caused by: Unable to instantiate class com.mysql.cj.jdbc.Driver : com.mysql.cj.jdbc.Driver Caused by: java.lang.ClassNotFoundException: com.mysql.cj.jdbc.Driver<br><br>2) Prevent user credentials expose in `docker-compose.yml`, `flyway.conf`.<br><br>3) Database name is specified by `MYSQL_DATABASE: ${GOLF_APP_DB_NAME:-golf04}` for mysql container, but it hardcoded as `golf04` in flyway.conf for flyway container.<br><br>4) Keep FLYWAY_URL, GOLF_APP_DB_JDBC_URL as before. | 100% | 100% | Files:<br>2 modified(M)<br>5 added(A)<br>0 deleted(D)<br><br>Lines:<br>531 insertions(+)<br>4 deletions(-) | Claude Opus 5 High |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See [agentic-workflow-tests/0003/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md) | N/A | 100% | 100% | | | | Files:<br>5 modified(M)<br>1 added(A)<br>3 deleted(D)<br><br>Lines:<br>210 insertions(+)<br>118 deletions(-) | |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0004/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md) | N/A | 59%<br><br>- Spring HTTP Message Conversion is not utilized.<br>- The implementation manually builds CSV with raw `StringBuilder` concatenation instead of a proven CSV processing library. | 92%<br><br>- Custom CSV generation code does not handle edge cases, exceptions. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) As a rule, it is better to return `@ResponseBody` than to manually construct a `ResponseEntity`.<br><br>3) Using StringBuilder is a poor and error-prone choice for CVS generation. | 100% | 100% | Files:<br>3 modified(M)<br>6 added(A)<br>0 deleted(D)<br><br>Lines:<br>538 insertions(+)<br>1 deletions(-) | |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0008/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md) | N/A | 100% | 100% | | | | Files:<br>10 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>144 insertions(+)<br>86 deletions(-) | |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See [agentic-workflow-tests/0011/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md) | N/A | 100% | 86%<br><br>- Unrequested Flyway integration into the application runtime.<br>- Exposes sensitive data in sources. | 1) Remove unrequested Flyway integration into the application runtime.<br><br>2) Remove the application users plaintext credentials from the codebase. | 100% | 100% | Files:<br>3 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>110 insertions(+)<br>24 deletions(-) | |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0014/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md) | N/A | 94%<br><br>- Bootstrap bundle is not utilized to create the account menu. | 97%<br><br>- Custom CSS is generated instead of using Bootstrap adopted in the project. | 1) Rework the implementation using Bootstrap adopted in the project instead of custom CSS. | 100% | 100% | Files:<br>2 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>94 insertions(+)<br>2 deletions(-) | |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0016/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md) | N/A | 83%<br><br>- Using POST instead of DELETE HTTP method violates RESTful principles. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method. | 100% | 100% | Files:<br>3 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>107 insertions(+)<br>1 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **87%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 4 | 0.55 | 0.86 | 0.34 | 1.00 | 1.00 | 0.57 |
| 0003 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0004 | Local | 3 | 0.67 | 0.92 | 0.59 | 1.00 | 1.00 | 0.71 |
| 0008 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0011 | Local | 2 | 0.82 | 0.86 | 1.00 | 1.00 | 1.00 | 0.87 |
| 0014 | Local | 1 | 1.00 | 0.97 | 0.94 | 1.00 | 1.00 | 0.98 |
| 0016 | Local | 1 | 1.00 | 1.00 | 0.83 | 1.00 | 1.00 | 0.96 |

## Links

- [Cursor home](https://cursor.com)

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
