# JetBrains IDEA Claude Agent Tests — April 2026

## Summary

The new version of Claude Agent has become integrated in JetBrains IDEs AI Assistant via Agent Client Protocol (ACP). The new agent is powered by Anthropic models, including the Claude 4.6 Opus. The agent has become more flexible, allowing users to select one from multiple execution modes, including plan mode, and to choose a suitable LLM model for the task.

The agent has been tested with the Claude Opus 4.6 model and has shown first-rate performance, although not as outstanding as in the previous run. The agent still has the ability to complete the tasks assigned to it. The agent responds reasonably to feedback, which allowed the goal to be successfully achieved in a minimum number of steps. However, the agent may suggest plain, straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

The agent's user interface is well designed and polished, and will be convenient for users who have experience with JetBrains IDEs.

## Details

Claude Agent is a coding agent by Anthropic bundled with AI Assistant. Starting from IDE versions 2025.3.4, Claude Agent is available in AI Assistant through the Agent Client Protocol (ACP) instead of a custom integration via Claude Agent SDK.

Claude Agent is provided with AI Assistant and runs over the dedicated Node.js runtime installed on the local workstation. By default, the runtime is not accessible outside of the IDE.

Claude Agent can be used either with a JetBrains AI subscription or with an Anthropic API token.

The agent allows selecting one of the Anthropic models to perform a task. Currently, the following options are available:

- **Default** — the agent chooses the model best suited for the task by itself.
- **Sonnet 4.6** — 1M context.
- **Opus 4.6** — 1M context.
- **Haiku**

The agent can operate in one of the following modes, providing a distinct level of autonomy and interaction:

- **Default** — standard behavior; prompts for potentially dangerous operations.
- **Accept Edits** — automatically applies file edits.
- **Plan Mode** — enables planning without executing actions.
- **Don't Ask** — does not prompt for permissions and denies actions that are not pre-approved.
- **Bypass Permissions** — bypasses all permission checks.

## Testing

### Environment

| Component | Version |
|---|---|
| IDE | JetBrains IntelliJ IDEA 2026.1 |
| JetBrains AI Assistant | 261.22158.366 |
| Claude Agent | 0.25.3 |
| Model | Claude Opus 4.6 |

## Code Generation Findings

- Recommends follow-up steps after solution generation, allowing a developer to drive the development.
- Enters plan mode by itself for complex tasks.
- Claude Agent hangs in interim and explicit plan mode if the developer has chosen a concrete model. Workaround: restart IDE.
- Can suggest simplified, straightforward solutions and prefers to make rash decisions rather than probe deeply into the problem.
- It may be laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions on how to improve and/or fix the solution code.
- May miss some project setup details and generate a non-optimal solution for the project, ignoring the project tech stack.

## Testing Customization

General golf-application rules for agents are added as file:

```text
.aiassistant/rules/AGENTS.md
```

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See agentic-workflow-tests/0001/README.md | N/A | 50%<br><br>- Database schema validation error: wrong column type.<br>- The application run failed due to schema-validation error.<br>- Tests could not be performed due to the failed app launch. | 86%<br><br>- The intended functionality is not accomplished.<br>- Exposes sensitive data in sources. | Follow the recommendation:<br><br>0) Change `spring.jpa.hibernate.ddl-auto` in `application.properties` from `update` to `validate`.<br><br>Review:<br><br>1) `SchemaManagementException`: Schema-validation: wrong column type encountered in column `[gender]` in table `[player]`; found `[varchar (Types#VARCHAR)]`, but expecting `[tinyint (Types#TINYINT)]`<br><br>2) Prevent user credentials expose in `docker-compose.yml`, `flyway.conf`.<br><br>3) Using the root user as the application database user leads to security risks. | 100% | 100% | Files:<br>2 modified(M)<br>4 added(A)<br>0 deleted(D)<br><br>Lines:<br>441 insertions(+)<br>4 deletions(-) | Started with default auto-selected model, switched to Opus in review stage. |
| 2 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See agentic-workflow-tests/0003/README.md | N/A | 100% | 100% | Not required |  |  | Files:<br>3 modified(M)<br>0 added(A)<br>3 deleted(D)<br><br>Lines:<br>18 insertions(+)<br>116 deletions(-) |  |
| 3 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See agentic-workflow-tests/0004/README.md | N/A | 56%<br><br>- `null` values are represented as `null` rather than empty strings.<br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 63%<br><br>- The intended functionality is not fully accomplished.<br>- Custom CSV generation code does not handle edge cases, exceptions.<br>- CSV generation is embedded in the controller.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using `StringBuilder` is a poor and error-prone choice for CVS generation. | 100% | 83%<br><br>- The CSV generation logic lacks necessary documentation. | Files:<br>3 modified(M)<br>1 added(A)<br>0 deleted(D)<br><br>Lines:<br>99 insertions(+)<br>1 deletions(-) |  |
| 4 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See agentic-workflow-tests/0008/README.md | N/A | 65%<br><br>- `spring-boot-starter-logging` is not fully excluded from Spring Boot starter dependencies.<br>- `spring-boot-starter-logging` and hence Logback is still present.<br>- LMAX Disruptor is not added as dependency and it is not utilized.<br>- `application.properties` still contains logging level configurations.<br>- Logging is not asynchronous in Log4j2 configuration.<br>- The configuration uses a `<RollingFile>` appender rather than a `<RollingRandomAccessFile>` appender.<br>- The application log file is not created. | 92%<br><br>- The intended functionality is not accomplished.<br>- Logging within loop degrades performance. | 1) SLF4J: Class path contains multiple SLF4J providers.<br>SLF4J: Found provider `[ch.qos.logback.classic.spi.LogbackServiceProvider@6bc168e5]`<br>SLF4J: Found provider `[org.apache.logging.slf4j.SLF4JServiceProvider@7b3300e5]`<br>SLF4J: Actual provider is of type `[ch.qos.logback.classic.spi.LogbackServiceProvider@6bc168e5]`<br><br>2) Configure Log4j2 for maximum performance as it has been requested.<br><br>3) Would `RollingRandomAccessFile` be better for performance?<br><br>4) Fix the issue, but keep ability to configure log dir externally:<br>`WARN StatusConsoleListener Infinite loop in property interpolation of LOG_DIR->sys:LOG_DIR`<br><br>5) `logging.level.*` properties are not removed from `application.properties`. The created loggers are synchronous by default. It affects the logging performance.<br><br>6) Logging within loop degrades performance.<br><br>7) Mapping within stream as logging statement argument affects performance too. | 100% | 100% | Files:<br>7 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>84 insertions(+)<br>85 deletions(-) |  |
| 5 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See agentic-workflow-tests/0011/README.md | N/A | 77%<br><br>- The application launch fails due to a SQL syntax error.<br>- Tests could not be performed due to the failed app launch. | 88%<br><br>- The intended functionality is not accomplished.<br>- SQL syntax error. | 1) Failed to execute SQL script statement #3 of file `[golfapp-idea-claude-20260407-00\target\classes\schema.sql]`: `CREATE UNIQUE INDEX IF NOT EXISTS ix_auth_username ON authorities (username, authority)` | 100% | 100% | Files:<br>2 modified(M)<br>2 added(A)<br>0 deleted(D)<br><br>Lines:<br>31 insertions(+)<br>23 deletions(-) | Minor: the solution relies on `spring.sql.init.mode`, it is not directly requested. |
| 6 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See agentic-workflow-tests/0014/README.md | N/A | 85%<br><br>- Bootstrap bundle is not utilized to create the account menu.<br>- The account menu is not expandable sub-menu but just raw main menu elements.<br>- An user is not redirected to proper login page after logout. | 92%<br><br>- The intended functionality is not fully accomplished. | 1) Make the account menu an expandable sub-menu, rather than just a few main menu items.<br><br>2) Try to rework the account menu using Bootstrap adopted in the project instead of custom JavaScript and CSS.<br><br>3) The account menu does not expand downwards on the application pages.<br><br>4) The account menu does not expand downwards on the following pages:<br>- Enter Your Round score<br>- Your Round Score Page<br>- ADD COMPETITION<br>- EDIT COMPETITION<br>- ADD COMPETITION ROUND<br>- ADD COURSE<br><br>5) An user is redirected to unused sign in page instead of actual login page after logout where he can not login again: `http://localhost:8082/login?logout` | 100% | 100% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>22 insertions(+)<br>1 deletions(-) |  |
| 7 | Local | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See agentic-workflow-tests/0016/README.md | N/A | 83%<br><br>- The solution uses POST HTTP method for competition deletion instead of DELETE | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method.<br><br>2) Please rewrite competition deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")`. | 100% | 100% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>11 insertions(+)<br>1 deletions(-) |  |

## Agent's Final Grade

The agent's final grade is **76%**.

| Number | Tag | Subsequent Prompts Count | Performance | Accuracy First | Completeness First | Accuracy Final | Completeness Final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | Local | 3 | 0.67 | 0.86 | 0.50 | 1.00 | 1.00 | 0.68 |
| 0003 | Local | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0004 | Local | 2 | 0.82 | 0.63 | 0.56 | 0.83 | 1.00 | 0.67 |
| 0008 | Local | 7 | 0.30 | 0.92 | 0.65 | 1.00 | 1.00 | 0.54 |
| 0011 | Local | 1 | 1.00 | 0.88 | 0.77 | 1.00 | 1.00 | 0.91 |
| 0014 | Local | 5 | 0.45 | 0.92 | 0.85 | 1.00 | 1.00 | 0.67 |
| 0016 | Local | 2 | 0.82 | 1.00 | 0.83 | 1.00 | 1.00 | 0.87 |

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
