# OpenAI Codex Extension Tests - September 2025

## Table of Contents

- [Summary](#summary)
- [Testing](#testing)
    - [Environment](#environment)
    - [Code Generation Findings](#code-generation-findings)
    - [Test Report](#test-report)
- [Agent’s Final Grade](#agents-final-grade)

## Summary

Codex IDE extension is a coding agent provided as a VS Code extension.

The agent showed one of the best performances in solving tasks. There are some drawbacks, however. For instance, it tends to suggest simplified, straightforward solutions.

The implementation plan is not shown; the agent starts to generate a solution immediately.

The context and history are not kept; they disappear after IDE restart or project close.

The agent UI is far from perfect.

The agent has been examined with tasks belonging to various categories such as solution-or-component generation, solution migration, code refactoring, and code bugfixing.

## Testing

### Environment

|                        | Version    |
|------------------------|------------|
| OpenAI Codex Extension  | 0.4.0      |
| Payment Plan           | Team       |
| Default Model          | GPT-5      |
| Agent Mode             | Full access|
| Reasoning Effort       | Medium     |

### Code Generation Findings

- The default agent mode is too intrusive, asking for every single action and not allowing general approval. Conversely, full access mode seems insecure. The extension pushes for full access.
- May show changes for one file and ask approval for another.
- Requests file edit approvals one by one, keeping users tied to the IDE.
- May keep unused code leftover from previous iterations.
- Formulates open questions to refine the solution.

### Test Report

| # | Source Code Repository | Task Summary (Name/Category/Complexity) | Task Description (Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts (Feedback, Comments) | Final Completeness | Final Accuracy | Final Test Grade | Statistics | Comments |
|---|-----------------------|------------------------------------------|-----------------------------------|-------------------|------------------------|---------------------|-----------------------------------------|--------------------|----------------|------------------|------------|----------|
| 1 | [github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | Id: 0001<br>Name: Make reverse engineering of DB schema and make it manageable with Flyway<br>Category: code-refactoring<br>Complexity: Medium | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md) | N/A | 32%<br>- Mysql container start failed due to invalid configuration<br>- DB migration could not be performed<br>- The application launch could not be performed<br>- The application testing could not be performed | 86%<br>- The code does not accomplish the intended functionality<br>- Default credentials are hardcoded in the Docker Compose and documented in the README. | 0) answer to the agent question: Switch Hibernate DDL to validate and add a Flyway run section to the README<br>1) Mysql container failed to start: unknown variable 'default-authentication-plugin=caching_sha2_password'.<br>2) Schema-validation: wrong column type encountered in column [gender] in table [player]; found [smallint (Types#SMALLINT)], but expecting [tinyint (Types#TINYINT)]<br>3) Do not apply database schema fixes as new version. Just update V1__init_schema.sql.<br>4) Schema-validation: missing table [round_score_scores]<br>5) Schema-validation: missing column [round_score_id] in table [round_score_scores] | 100% | 94%<br>- Default credentials are hardcoded in the Docker Compose and documented in the README. | 51% | Files:<br>2 modified(M)<br>3 added(A)<br>0 deleted(D)<br>Lines:<br>418 insertions(+)<br>2 deletions(-) | |
| 2 | [github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | Id: 0003<br>Name: Refactor Golf application access-control layer, replace Basic Authentication with OAuth2 Authorization<br>Category: code-refactoring<br>Complexity: High | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md) | N/A | 75%<br>- External authorization server is not configured. Instead, a local HS256 secret is specified | 100% | 1) Configure external authorization server URI instead of local HS256 secret | 100% | 100% | 94% | Files:<br>4 modified(M)<br>0 added(A)<br>0 deleted(D)<br>Lines:<br>66 insertions(+)<br>45 deletions(-) | |
| 3 | [github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | Id: 0004<br>Name: Return round scores in CSV format in Golf application<br>Category: solution-or-component-generation<br>Complexity: Low | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md) | N/A | 59%<br>- Spring HTTP Message Conversion is not utilized<br>- A proven CSV processing library is not used to write CSV | 72%<br>- The implementation mixes presentation concerns with business logic, the CSV is built with controller<br>- The code lacks necessary documentation | 1) Spring's message conversion mechanism is not utilized<br>2) Converting RoundScore to intermediate type RoundScoreCsvRow in controller and using the type in HttpMessageConverter. Please use the original type in HttpMessageConverter.<br>3) HttpMessageConverter is defined as anonymous inner class (not readable/maintainable, complicates testing)<br>4) CSV generation is handled manually using OutputStreamWriter and StringBuilder, which is error-prone.<br>5) GET /round-score with Accept: text/csv returns all fields empty except Id. Error is logged: Java 8 date/time type `java.time.LocalDate` not supported by default: add Module "com.fasterxml.jackson.datatype:jackson-datatype-jsr310" to enable handling | 100% | 83%<br>- The code lacks necessary documentation | 53% | Files:<br>2 modified(M)<br>2 added(A)<br>0 deleted(D)<br>Lines:<br>141 insertions(+)<br>0 deletions(-) | |
| 4 | [github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | Id: 0008<br>Name: Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br>Category: solution-migration<br>Complexity: Medium | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md) | N/A | 90%<br>- `logging.level.*` properties are not removed from application.properties<br>- Log4j2 loggers are not effectively configured as asynchronous | 100% | 0) Document described performance optimization options in README<br>1) Permanently enable full Async Loggers<br>2) `logging.level.*` properties are not removed from application.properties | 100% | 100% | 89% | Files:<br>8 modified(M)<br>2 added(A)<br>2 deleted(D)<br>Lines:<br>129 insertions(+)<br>90 deletions(-) | |
| 5 | [github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | Id: 0011<br>Name: Migrate in-memory user and role definitions to database in Golf application<br>Category: code-refactoring<br>Complexity: Low | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md) | N/A | 73%<br>- The application failed to launch<br>- Test couldn't be performed due to application launch failure | 92%<br>- The code does not accomplish the intended functionality | 1) Got the error: `ERROR o.s.boot.SpringApplication -  Application run failed ... Error creating bean with name 'flyway' ... Unsupported Database: MySQL 8.0`<br>Consider that database is managed externally. Keep the scripts, but remove Flyway from runtime. | 100% | 100% | 92% | Files:<br>2 modified(M)<br>2 added(A)<br>0 deleted(D)<br>Lines:<br>34 insertions(+)<br>25 deletions(-) | |
| 6 | [github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | Id: 0014<br>Name: User Account Menu in Golf application<br>Category: solution-or-component-generation<br>Complexity: Low | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md) | N/A | 31%<br>- The dependency `org.thymeleaf.extras:thymeleaf-extras-springsecurity6` is not added to pom.xml<br>- Multiple issues with adding the account menu to the templates<br>- Template parsing errors<br>- Tests could not be performed | 73%<br>- The intended functionality is not accomplished<br>- The Thymeleaf template crashes at runtime<br>- The standard Thymeleaf/Spring Security approaches is not used. | 1) ERROR org.thymeleaf.TemplateEngine - Exception processing template "<i>home</i>": SpringEL expression `#httpServletRequest.userPrincipal != null` property missing<br>2) The account menu does not expand downwards on the app pages.<br>3) The account menu does not expand downwards anyway. | 100% | 100% | 60% | Files:<br>16 modified(M)<br>0 added(A)<br>0 deleted(D)<br>Lines:<br>49 insertions(+)<br>48 deletions(-) | |
| 7 | [github.com/PolinaTolkachova/golf-application](https://github.com/PolinaTolkachova/golf-application) | Id: 0016<br>Name: Fix an issue with competition removing in Golf application<br>Category: code-bugfixing<br>Complexity: Medium | See [README.md](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md) | N/A | 83%<br>- The solution uses POST HTTP method for competition deletion instead of DELETE | 100% | 1) Using POST instead of DELETE HTTP method violates RESTful principles.<br>2) Support hidden HTTP method declaratively.<br>3) Clean up the unused code left over from previous iterations. | 100% | 100% | 79% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br>Lines:<br>14 insertions(+)<br>3 deletions(-) | |

## Agent's Final Grade

The agent's final rating is 74%.

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
