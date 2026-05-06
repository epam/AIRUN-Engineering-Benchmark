# Pi.Dev Coding Agent Tests on GLM-5.1 — April 2026

## Summary

Pi.Dev Coding Agent is an open-source minimal terminal coding agent. The fundamental difference between Pi and other agents is the minimalistic setting of interaction with LLM and maximum reliance on LLM in solving all the tasks. Pi promises to provide stable and highly customizable coding harness allowing to manage the development environment by own and avoid of being trapped by vendor dictating the adaptation to the agent roadmap, updates, feature changes, pricing volatility, usage policy shifts, etc.

The agent has been tested with GLM-5.1 model. Although it successfully completed the tasks assigned to it, it has shown unremarkable performance. Evidently there are difficulties with discovering a big complex context and linking multiple instances in the model/agent setup. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. In response, the agent generated solutions affecting from 3 files and 12 code lines till 16 files and 670 code lines. It took from 1 to 9 iterations to complete the given development either successfully or to prove that further agent-assisted development was not reasonable.

## Details

Pi.Dev Coding Agent is positioned as a minimal terminal coding harness rather than as a coding agent.

The fundamental difference between Pi and other agents is the minimalistic setting of interaction with LLM and maximum reliance on LLM in solving all the tasks. Pi promises to provide stable and highly customizable coding harness allowing to manage the development environment by own and avoid of being trapped by vendor dictating the adaptation to the agent roadmap, updates, feature changes, pricing volatility, usage policy shifts, etc.

Here are some highlights:

- Pi provides minimal system prompt, minimal toolset, but skips features like sub-agents and plan mode.
- Pi runs in full YOLO mode and has unrestricted access to filesystem and can execute any command without permission checks or safety guards.
- Pi supports 15+ LLM providers, allows to add custom providers and models.
- Pi supports tree-structured, shareable history.
- Pi's minimal system prompt and extensibility allows to get the most from context engineering.
- Pi is extensible by design, it doesn't dictate the development workflow, but allows a developer to build the own workflow with extensions, skills, or installed from third-party packages.

## Testing

### Environment

| | Version |
|---|---|
| Pi.Dev Coding Agent | 0.70 |
| Default Model | GLM-5.1 |
| Thinking level | High |

## Features Feedback

| Category | Grade | Comments | Evaluation Criteria |
|---|---|---|---|
| Auto-discovery of task relevant source code | Excellent | | Agent must find all files related to task context. It is good when the agent can report on the exact context pieces that it used during task solving |
| Implementation plan support | Mediocre | Creates the plan on the fly. There is not a separate Plan Mode. | Agent must generate an implementation plan consisting of steps with a clear detailed description of what change, why and how is made in each step. It is good when the developer is able to comment on the generated implementation plan and re-generate it according to the comments |
| Apply generated changes to local files | Excellent | | Agent must apply generated changes to local files. The expectation is that changes can be made flexibly by a developer request: all files, files one by one, chosen code fragments. |
| Iterative work on solution | Excellent | | Agent must allow a developer leave a feedback to generated solution and improve the solution following the developer comments. |
| Feature usage instructions generation | Excellent | | Agent should generate a feature usage instructions describing how to use or test the feature. |
| External tools support | Excellent | | Agent must be able to call external tools after permission of the developer |
| Model Context Protocol (MCP) support | ? | MCP servers are considered as inefficient, users are advised to use CLI tools or extensions instead. | Agent should be able to use MCP to connect to external systems and data sources to get context from. |
| Context/History retention | Bad | The functionality was broken at the testing time. | Agent should keep task solving sessions to allow a developer to recall details of agent/developer interactions. Agent may allow to continue development within the session after a time. |
| UI usability | Excellent | | How easy agent user interfaces are to use. |
| Code Lintering | Excellent | | |

## Code Generation Findings

- Gives the most clean view and shows the most detailed log of interactions with the model between the evaluated coding agents.
- Can create tests to validate the generated solution.
- May go beyond the scope of the given task by generating code distantly related to the requested changes.
- May suggest a simplified straightforward solution. It is laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions how to improve and/or fix the solution code.

## Testing Customization

General golf-application rules for agents are added as file `AGENTS.md`.

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md | N/A | 32%<br><br>- The DB migration did not apply successfully.<br>- The docker-compose logs show errors related to the initialization of the MySQL container (error when running the migration script).<br>- Schema validation failed: missing table `competition_players`.<br>- The application launch fails due to a database schema validation error.<br>- Testing could not be performed due to the failed application launch. | 69%<br><br>- The intended functionality is not accomplished.<br>- The DB migration embedded into Docker setup, added as Spring Flyway external conf, and Flyway migration enabled at Spring app start.<br>- The SQL script fails during execution due to a foreign key reference error.<br>- Exposes sensitive data in sources. | 1) Take off DB migration from Docker setup, Spring app configuration.<br><br>2) Configure Hibernate to validate schema only, let Flyway manage schema.<br><br>3) Flyway reported: Schema history table `golf04`.`flyway_schema_history` does not exist yet. Successfully validated 0 migrations (execution time 00:00.023s). WARNING: No migrations found. Are your locations set up correctly?<br><br>4) ERROR: Failed to execute script V1__create_golf_schema.sql. Message: (conn=34) Failed to open the referenced table 'player'<br><br>5) Schema-validation: wrong column type encountered in column [gender] in table [player]; found [varchar (Types#VARCHAR)], but expecting [tinyint (Types#TINYINT)]<br><br>6) Using the root user as the application database user leads to security risks.<br><br>7) The database user credentials are hardcoded in docker/mysql-init/01_create_app_user.sql while they should be managed by container environment.<br><br>8) Prevent user credentials expose in `docker-compose.yml`, `flyway.conf`.<br><br>9) localhost/golf04: Access denied for user 'golf_app' | 100% | 100% | Files:<br>2 modified(M)<br>5 added(A)<br>0 deleted(D)<br><br>Lines:<br>440 insertions(+)<br>5 deletions(-) | |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md | N/A | 59%<br><br>- The external authorization server is not utilized.<br>- The access is enabled by default for endpoints being added.<br>- The application launch failed.<br>- Tests could not be performed due to the failed app launch. | 64%<br><br>- The intended functionality is not accomplished.<br>- The code is generated to work in dev/test environment rather in production one.<br>- Unrequested standalone custom JWT generation and utilization.<br>- Direct RSA key injection and unsecured JWT generation leads to security risks. | 1) Use the external authorization server instead of standalone custom JWT generation and utilization.<br><br>2) Prevent cases where newly added endpoints would be accessible to any authenticated user (the access is not denied by default).<br><br>3) Keep User entity table as is, but prevent H2 syntax error while creating `user` table.<br><br>4) Remove /register/me endpoint. | 100% | 100% | Files:<br>10 modified(M)<br>4 added(A)<br>2 deleted(D)<br><br>Lines:<br>545 insertions(+)<br>125 deletions(-) | |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md | N/A | 52%<br><br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 72%<br><br>- Custom CSV generation code does not handle edge cases, exceptions.<br>- CSV generation is embedded in the controller.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using StringBuilder is a poor and error-prone choice for CVS generation.<br><br>3) Regression: the default RoundScoreController GET endpoint is narrowed to "text/html" media type only.<br><br>4) RoundScoreController.toCsvDtoList(...) private method implements untestable conversion. | 100% | 83%<br><br>- The CSV generation logic lacks necessary documentation. | Files:<br>3 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>171 insertions(+)<br>2 deletions(-) | |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md | N/A | 60%<br><br>- `spring-boot-starter-logging` is not fully excluded from Spring Boot starter dependencies.<br>- `spring-boot-starter-logging` (and hence Logback) is still present.<br>- LMAX Disruptor is not added as dependency and it is not utilized.<br>- application.properties still contains logging level configurations.<br>- Logging is not asynchronous in Log4j2 configuration.<br>- The configuration uses a \<RollingFile\> appender rather than a \<RollingRandomAccessFile\> appender.<br>- The application log file is not created. | 88%<br><br>- The intended functionality is not accomplished.<br>- Logging within loop degrades performance. | 1) SLF4J: Class path contains multiple SLF4J providers. Found provider [ch.qos.logback.classic.spi.LogbackServiceProvider@6bc168e5] Found provider [org.apache.logging.slf4j.SLF4JServiceProvider@7b3300e5] Actual provider is of type [ch.qos.logback.classic.spi.LogbackServiceProvider@6bc168e5]<br><br>2) Configure Log4j2 for maximum performance as it has been requested.<br><br>3) `logging.level.*` properties are not removed from application.properties. The created loggers are synchronous by default. It affects the logging performance.<br><br>4) Fix the issue, but keep the ability to configure log dir externally: WARN StatusConsoleListener Infinite loop in property interpolation of LOG_DIR->env:LOG_DIR<br><br>5) env:LOG_DIR is referenced twice now, it may cause errors in future. Create a property LOG_PATH initialized with env:LOG_DIR, use the property in the appender config. | 100% | 100% | Files:<br>7 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>131 insertions(+)<br>89 deletions(-) | |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md | N/A | 100% | 100% | Not required | | | Files:<br>2 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>51 insertions(+)<br>23 deletions(-) | Minor: the solution relies on spring.sql.init.mode, it is not directly requested. |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md | N/A | 95%<br><br>- An user is not redirected to proper login page after logout. | 92%<br><br>- The intended functionality is not fully accomplished. | 1) An user is redirected to unused sign in page instead of actual login page after logout where he can not login again: http://localhost:8082/login?logout&continue<br><br>2) An user is redirected to CSS style after login: http://localhost:8082/styles/main.css?continue | 100% | 92%<br><br>- Unrequested login form change provided as fix to introduced during feature development bugs. | Files:<br>5 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>151 insertions(+)<br>32 deletions(-) | |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md | N/A | 83%<br><br>- The solution uses POST HTTP method for competition deletion instead of DELETE | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method.<br><br>2) Please rewrite competition deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")`.<br><br>3) The competition deletion error: There was an unexpected error (type=Method Not Allowed, status=405). Method 'POST' is not supported. org.springframework.web.HttpRequestMethodNotSupportedException: Request method 'POST' is not supported at org.springframework.web.servlet.mvc.method.RequestMappingInfoHandlerMapping.handleNoMatch(RequestMappingInfoHandlerMapping.java:265) | 100% | 100% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>11 insertions(+)<br>1 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **68%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 9 | 0.20 | 0.69 | 0.32 | 1.00 | 1.00 | 0.35 |
| 0003 | Local | 4 | 0.55 | 0.64 | 0.59 | 1.00 | 1.00 | 0.58 |
| 0004 | Local | 4 | 0.55 | 0.72 | 0.52 | 0.83 | 1.00 | 0.56 |
| 0008 | Local | 5 | 0.45 | 0.88 | 0.60 | 1.00 | 1.00 | 0.60 |
| 0011 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0014 | Local | 2 | 0.82 | 0.92 | 0.95 | 0.92 | 1.00 | 0.86 |
| 0016 | Local | 3 | 0.67 | 1.00 | 0.83 | 1.00 | 1.00 | 0.79 |

## Links

- [Pi.dev Home](https://pi.dev/)

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
