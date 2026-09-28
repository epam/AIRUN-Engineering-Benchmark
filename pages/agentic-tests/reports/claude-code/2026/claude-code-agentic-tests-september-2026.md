# Claude Code Agent Tests — September 2026

## Summary

This is a next round of agentic testing of Claude Code, a terminal-based coding agent from Anthropic. The agent has been tested with newest Claude Opus 5 model (1M context) with medium effort. It shows significant improvement comparing with results obtained in May 2026 with Opus 4.7.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction. Also it has been observed that the agent deeply falls in Exception-Driven Development or Trial-and-Error Coding anti-patterns usage in attempts to get the working solution, causing the time and cost increasing.

## Testing

### Environment

| | Version |
|---|---|
| Claude Code | 2.1.268 |
| Payment Plan | Enterprise |
| Default Model | Opus 5 (1M context) with Medium effort |
| Run Mode | Manual Mode (Default) |

## Code Generation Findings

- Deeply falls in Exception-Driven Development or Trial-and-Error Coding anti-patterns usage in attempts to get the working solution, causing the time and cost increasing.
- Able to set up the test environment, for instance, launching Docker container for MySql.
- May create tests to validate the generated solution.
- May generate unnecessary custom code replacing the library/framework capabilities.
- May suggest a simplified straightforward solution.

## Testing Customization

General golf-application rules for agents are added as file `.claude/CLAUDE.md`.

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0001/README.md` | N/A | 85%<br><br>- Hibernate configuration is not changed from updating database schema to validating database schema. | 94%<br><br>- Exposes sensitive data in sources. | 1) Hibernate configuration is not changed from updating database schema to validating database schema.<br><br>2) Prevent user credentials expose in `flyway.conf`. | 100% | 100% | Files:<br>2 modified(M)<br>5 added(A)<br>0 deleted(D)<br><br>Lines:<br>550 insertions(+)<br>2 deletions(-) | |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See `agentic-workflow-tests/0003/README.md` | N/A | 75%<br><br>- The application.properties file uses the property 'golf.oauth2.issuer' instead of 'spring.security.oauth2.resourceserver.jwt.issuer-uri'.<br>- The configuration provided sets up an embedded authorization server via AuthorizationServerConfig rather than configuring an external authorization server. | 83%<br><br>- The intended functionality is not fully accomplished.<br>- Unrequested authorization server is embedded into application. | 1) Configure an external authorization server instead of the embedded authorization server. | 100% | 100% | Files:<br>4 modified(M)<br>3 added(A)<br>4 deleted(D)<br><br>Lines:<br>284 insertions(+)<br>135 deletions(-) | |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See `agentic-workflow-tests/0004/README.md` | N/A | 59%<br><br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 88%<br><br>- Custom CSV generation code does not handle edge cases, exceptions.<br>- CSV generation is embedded in the controller. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using OutputStreamWriter is a poor and error-prone choice for CVS generation. | 100% | 100% | Files:<br>2 modified(M)<br>4 added(A)<br>0 deleted(D)<br><br>Lines:<br>584 insertions(+)<br>1 deletions(-) | |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0008/README.md` | N/A | 95%<br><br>- The application.properties still contains logger configuration.<br>- The configuration uses a RollingFile appender instead of a RollingRandomAccessFile appender. | 100% | 1) `logging.level.*` properties are not removed from application.properties, but reconfigured for another loggers.<br><br>2) Would RollingRandomAccessFile be better for performance? | 100% | 100% | Files:<br>8 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>159 insertions(+)<br>83 deletions(-) | |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See `agentic-workflow-tests/0011/README.md` | N/A | 100% | 94%<br><br>- Exposes sensitive data in sources. | 1) Remove plaintext credentials from source code.<br><br>2) Remove the application users plaintext credentials. | 100% | 100% | Files:<br>3 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>196 insertions(+)<br>26 deletions(-) | Minor: the solution relies on spring.sql.init.mode, it is not directly requested. |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See `agentic-workflow-tests/0014/README.md` | N/A | 90%<br><br>- Bootstrap bundle is not utilized to create the account menu.<br>- An user is not redirected to proper login page after logout. | 88%<br><br>- The intended functionality is not fully accomplished.<br>- Custom CSS is generated instead of using Bootstrap adopted in the project. | 1) Try to rework the account menu using Bootstrap adopted in the project instead of custom JavaScript and CSS.<br><br>2) An user is redirected to unused sign in page instead of actual login page after logout where he can not login again: http://localhost:8082/login?logout | 100% | 100% | Files:<br>17 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>110 insertions(+)<br>15 deletions(-) | |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0016/README.md` | N/A | 83%<br><br>- Using POST instead of DELETE HTTP method violates RESTful principles. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method. | 100% | 100% | Files:<br>3 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>111 insertions(+)<br>1 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **88%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 2 | 0.82 | 0.94 | 0.85 | 1.00 | 1.00 | 0.86 |
| 0003 | Local | 1 | 1.00 | 0.83 | 0.75 | 1.00 | 1.00 | 0.90 |
| 0004 | Local | 2 | 0.82 | 0.88 | 0.59 | 1.00 | 1.00 | 0.78 |
| 0008 | Local | 2 | 0.82 | 1.00 | 0.95 | 1.00 | 1.00 | 0.90 |
| 0011 | Local | 2 | 0.82 | 0.94 | 1.00 | 1.00 | 1.00 | 0.90 |
| 0014 | Local | 2 | 0.82 | 0.88 | 0.90 | 1.00 | 1.00 | 0.85 |
| 0016 | Local | 1 | 1.00 | 1.00 | 0.83 | 1.00 | 1.00 | 0.96 |

## Links

- [Claude Code Agent home](https://claude.ai)

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
