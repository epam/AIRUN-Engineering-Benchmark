# GitHub Copilot Agent Tests — September 2026

## Summary

This is a next round of agentic testing of GitHub Copilot agent embedded into VS Code as extension. The agent has been tested with newest GPT-6 Astra model. It shows improvement comparing with results obtained in May 2026 with Claude Opus 4.5, raising the passing tests from 76% to 84%.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction. Also it has been observed that the agent deeply falls in Exception-Driven Development or Trial-and-Error Coding anti-patterns usage in attempts to get the working solution, causing the time and cost increasing.

## Testing

### Environment

| | Version |
|---|---|
| GitHub Copilot | 0.66.0 (embedded into VS Code) |
| VS Code | 1.138.0 |
| Payment Plan | Enterprise |
| Default Model | GPT-6 Astra |
| Run Mode | Agent |

## Code Generation Findings

- Utilizes Exception-Driven Development or Trial-and-Error Coding anti-patterns usage in attempts to get the working solution, causing the time and cost increasing.
- Can ask clarifying questions to align on the direction and scope of development.
- May create tests to validate the generated solution. But often follows the Mirror Testing anti-pattern and creates tests reflecting exactly what the code currently does, without validating the expected behavior.
- May generate unnecessary custom code replacing the library/framework capabilities.
- May suggest a simplified straightforward solution. It is laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions how to improve and/or fix the solution code.
- Tends to write change log to the repository root README.md, including low level technical details.
- Can use browser to debug UI.

## Testing Customization

General golf-application rules for agents are added as file `AGENTS.md`.

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0001/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md) | N/A | 50%<br><br>- The database schema validation could be performed due to the failed application launch.<br>- The application failed to launch.<br>- Tests could not be performed due to the failed application launch. | 92%<br><br>- The intended functionality is not accomplished. | 1) Mysql container port is narrowed to "127.0.0.1:${MYSQL_PORT:-3306}:3306" | 100% | 100% | Files:<br>3 modified(M)<br>4 added(A)<br>0 deleted(D)<br><br>Lines:<br>494 insertions(+)<br>4 deletions(-) | |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See [agentic-workflow-tests/0003/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md) | N/A | 100% | 100% | | | | Files:<br>7 modified(M)<br>2 added(A)<br>0 deleted(D)<br><br>Lines:<br>431 insertions(+)<br>104 deletions(-) | |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0004/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md) | N/A | 59%<br><br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 83%<br><br>- CSV generation documentation is added, but put in README instead of code comments. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using StringBuilder is a poor and error-prone choice for CVS generation.<br><br>3) Not sure, String bashing is needed in RoundScoreCsvUtils.toCsv and here:<br>`String csv = RoundScoreCsvUtils.toCsv(roundScores.roundScores());`<br>`StreamUtils.copy(csv, StandardCharsets.UTF_8, outputMessage.getBody());`<br><br>4) Does it make sense to have RoundScoresCsv DTO and single-functioned RoundScoreCsvUtils? The code looks like spaghetti, it is rather untestable. | 100% | 83%<br><br>- CSV generation documentation is added, but put in README instead of code comments. | Files:<br>3 modified(M)<br>4 added(A)<br>0 deleted(D)<br><br>Lines:<br>436 insertions(+)<br>1 deletions(-) | |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0008/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md) | N/A | 90%<br><br>- `logging.level.*` properties are not completely removed from application.properties. The created loggers are synchronous by default. it can unintentionally affects the logging performance.<br>- The configuration uses a RandomAccessFile appender instead of a RollingRandomAccessFile appender.<br>- Not all Log4j2 loggers are asynchronous. | 100% | 1) `logging.level.*` properties are not completely removed from application.properties. The created loggers are synchronous by default. It affects the logging performance.<br><br>2) Would RollingRandomAccessFile be better for performance?<br><br>3) The original logger for "org.springframework.web" from Logback configuration is not kept, but replaced with a logger for "org.springframework" in Log4j2 configuration. | 100% | 100% | Files:<br>8 modified(M)<br>4 added(A)<br>2 deleted(D)<br><br>Lines:<br>339 insertions(+)<br>85 deletions(-) | |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See [agentic-workflow-tests/0011/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md) | N/A | 100% | 100% |  | | | Files:<br>3 modified(M)<br>2 added(A)<br>0 deleted(D)<br><br>Lines:<br>260 insertions(+)<br>27 deletions(-) | |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See [agentic-workflow-tests/0014/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md) | N/A | 49%<br><br>- thymeleaf-extras-springsecurity6 dependency is not added.<br>- Thymeleaf security namespace is not utilized.<br>- Bootstrap bundle is not utilized to create the account menu.<br>- The attribute sec:authorize="isAuthenticated()" is not user to show username.<br>- The account menu is not enclosed in authentication guarded element. | 93%<br><br>- Custom CSS is generated instead of using Bootstrap adopted in the project.<br>- Created custom ControllerAdvice to publish username as attribute instead of Thymeleaf sec:authentication="name". | 1) Try to rework the account menu using Bootstrap adopted in the project instead of custom JavaScript and CSS.<br><br>2) Use Thymeleaf-extras-springsecurity6 instead of custom ControllerAdvice to show username as attribute. | 100% | 100% | Files:<br>16 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>191 insertions(+)<br>19 deletions(-) | |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See [agentic-workflow-tests/0016/README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md) | N/A | 83%<br><br>- Using POST instead of DELETE HTTP method violates RESTful principles. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method.<br><br>2) Please rewrite deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")`. | 100% | 100% | Files:<br>5 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>184 insertions(+)<br>1 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **84%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 1 | 1.00 | 0.92 | 0.50 | 1.00 | 1.00 | 0.85 |
| 0003 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0004 | Local | 4 | 0.55 | 0.83 | 0.59 | 0.83 | 1.00 | 0.61 |
| 0008 | Local | 3 | 0.67 | 1.00 | 0.90 | 1.00 | 1.00 | 0.81 |
| 0011 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0014 | Local | 2 | 0.82 | 0.93 | 0.49 | 1.00 | 1.00 | 0.76 |
| 0016 | Local | 2 | 0.82 | 1.00 | 0.83 | 1.00 | 1.00 | 0.87 |

## Links

- [GitHub Copilot home](https://github.com/copilot)

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
