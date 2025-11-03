# JetBrains AI Assistant Claude Agent Agentic Tests - October 2025

## Table of Contents

- [Summary](#summary)
- [Testing](#testing)
    - [Environment](#environment)
    - [Code Generation Findings](#code-generation-findings)
    - [Test Report](#test-report)
- [Agent's Final Grade](#agents-final-grade)

## Summary

Claude Agent is natively integrated in JetBrains IDEs coding agent built on top of Claude Agent SDK, the same technology that used by Claude Code. The new agent is powered by Anthropic models, including the Claude 4.5 Sonnet.

The agent has taken a leading position among the tested coding agents. The advantages, which allowed it to achieve this position, include the high readiness of the initial solution and the ability to refine the solution to an acceptable level in a minimum number of iterations. However the agent may miss to address some requested changes or suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

The agent experiences issue while tracking progress of large and complex tasks. Users should consider to divide such tasks into smaller, more manageable steps to make it less frustrating and easier to accomplish.

The agent's user interface is well designed and polished, and will be convenient for users having experience with JetBrains IDEs.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. In response, the agent generated solutions affecting from 2 files and 13 code lines till 11 files and 409 code lines. It took from 1 to 3 iterations to complete the given development successfully.

## Testing

### Environment

| Item | Version / Value |
| --- | --- |
| Claude Agent | Beta |
| IDE | IntelliJ IDEA 2025.2.3 (Ultimate Edition) |
| Default Model | Multiple models including Claude 4.5 Sonnet. |
| License | JetBrains AI Pro |

### Code Generation Findings

- May generate custom code instead of using the library/framework capabilities.
- Can examine git history.
- Plan mode allows to review and adjust implementation plan before starting coding.
- Can create tests to verify the developed solution.
- In cases of complex and large tasks, the agent allows you to control the solution generation process, giving you the opportunity to review changes, comment on them, and express your wishes on which area to focus on and which subtasks to complete first.
- In cases of complex and large tasks, the agent has difficulties with tracking implementation plan TODO items. After some time, the agent begins to create multiple inconsistent files to track the progress of the task.
- The agent terminal is not exposed (showed). It makes troubleshooting of agent launched commands issues rather difficult.

### Test Report

| No | Sourcecode Repository | Task Summary (Name/Category/Complexity) | Task Description (Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts (Feedback, Comments) | Final Completeness | Final Accuracy | Final Test Grade | Statistics | Comments |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | https://github.com/PolinaTolkachova/golf-application | Id: 0001<br>Name: Make reverse engineering of DB schema and make it manageable with Flyway<br>Category: code-refactoring<br>Complexity: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md | N/A | 32%<br>- Database schema validation error.<br>- Flyway migration error: Found non-empty schema. The solution supposed the schema migration both with Flyway and within MySQL database initialization.<br>- Hibernate configuration is not changed to validate database schema.<br>- The application run failed due to schema-validation error.<br>- Tests could not be performed due to the failed app launch. | 86%<br>- The intended functionality is not accomplished.<br>- Passwords and secrets are shown in plaintext. | 1) The `docker-compose.yml` suppose the schema initialization from `/docker-entrypoint-initdb.d/V1__Initial_schema.sql`. Although it is requested to use Flyway to manage the database schema.<br>2) SchemaManagementException: Schema-validation: wrong column type encountered in column [gender] in table [player]; found [varchar (Types#VARCHAR)], but expecting [tinyint (Types#TINYINT)] | 85%<br>- Hibernate configuration is not changed to validate database schema. | 94%<br>- Passwords and secrets are shown in plaintext. | 66% | Files: 0 modified, 3 added, 0 deleted<br>Lines: 409 insertions, 0 deletions |  |
| 2 | https://github.com/PolinaTolkachova/golf-application | Id: 0003<br>Name: Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br>Category: code-refactoring<br>Complexity: High | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md | N/A | 93%<br>- The application code does deny access by default for newly added endpoints. | 100% | Not required |  |  | 96% | Files: 3 modified, 0 added, 0 deleted<br>Lines: 29 insertions, 44 deletions |  |
| 3 | https://github.com/PolinaTolkachova/golf-application | Id: 0004<br>Name: Return round scores in CSV format in Golf application<br>Category: solution-or-component-generation<br>Complexity: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md | N/A | 59%<br>- Spring HTTP Message Conversion is not utilized.<br>- The code does not utilize a proven CSV processing library to write CSV. | 68%<br>- The code does not handle edge cases for CSV generation.<br>- CSV generation is embedded in the controller.<br>- The code bypasses Spring’s content negotiation (e.g., `produces = "text/csv"`) and manually checks headers, rather than using `HttpMessageConverter` or annotation-driven media type handling.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized<br>2) The code changed to use Spring's content negotiation, but Spring's message conversion is not used, CVS is directly generated with StringBuilder.<br>3) Using OutputStreamWriter is a poor and error-prone choice for CVS generation. | 93%<br>- The default RoundScoreController GET endpoint was not preserved, changed to respond to "text/html" only. | 83%<br>- The CSV generation logic lacks necessary documentation | 61% | Files: 3 modified, 1 added, 0 deleted<br>Lines: 97 insertions, 2 deletions |  |
| 4 | https://github.com/PolinaTolkachova/golf-application | Id: 0008<br>Name: Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br>Category: solution-migration<br>Complexity: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md | N/A | 89%<br>- `logging.level.*` properties are not removed from application.properties.<br>- `logging.properties` is not deleted.<br>- RollingRandomAccessFile appender is not used in log4j2.xml.<br>- Log4j2 loggers are not effectively asynchronous. | 100% | 1) Legacy logging configurations are not cleaned up.<br>2) Log4j2 loggers are not effectively asynchronous.<br>3) Would RollingRandomAccessFile be better for performance? | 100% | 100% | 81% | Files: 7 modified, 2 added, 2 deleted<br>Lines: 125 insertions, 81 deletions |  |
| 5 | https://github.com/PolinaTolkachova/golf-application | Id: 0011<br>Name: Migrate in-memory user and role definitions to database in Golf application<br>Category: code-refactoring<br>Complexity: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md | N/A | 100% | 92%<br>- Unrequested code: DatabaseUserInitializer bean is added to update password at the app launch | Not required |  |  | 96% | Files: 1 modified, 2 added, 0 deleted<br>Lines: 102 insertions, 23 deletions |  |
| 6 | https://github.com/PolinaTolkachova/golf-application | Id: 0014<br>Name: User Account Menu in Golf application<br>Category: solution-or-component-generation<br>Complexity: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md | N/A | 83%<br>- Bootstrap JavaScript bundle required to make the dropdown expand is not added.<br>- The dropdown menu does not expand.<br>- The menu logout functionality could not be tested. | 92%<br>- The intended functionality is not accomplished. | 1) The account menu does not expand downwards on all pages | 100% | 100% | 94% | Files: 2 modified, 0 added, 0 deleted<br>Lines: 26 insertions, 1 deletion |  |
| 7 | https://github.com/PolinaTolkachova/golf-application | Id: 0016<br>Name: Fix an issue with competition removing in Golf application<br>Category: code-bugfixing<br>Complexity: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md | N/A | 83%<br>- The solution uses POST HTTP method for competition deletion instead of DELETE | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method<br>2) Please rewrite competition deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")`<br>3) There was an unexpected error (type=Method Not Allowed, status=405). Method 'POST' is not supported. org.springframework.web.HttpRequestMethodNotSupportedException: Request method 'POST' is not supported | 100% | 100% | 79% | Files: 3 modified, 0 added, 0 deleted<br>Lines: 12 insertions, 1 deletion |  |

### Agent's Final Grade

The agent's final grade is 82%.