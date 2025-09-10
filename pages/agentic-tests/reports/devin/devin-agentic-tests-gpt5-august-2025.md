# Devin AI Agent GPT-5 Preview Tests - August 2025

## Table of Contents
- [Summary](#summary)
- [Distinctive Features](#distinctive-features)
- [Testing](#testing)
    - [Environment](#environment)
    - [Code Generation Findings](#code-generation-findings)
    - [Testing Approach](#testing-approach)
        - [Repository Initialization](#repository-initialization)
        - [Repository Setup in Devin](#repository-setup-in-devin)
    - [Test Report](#test-report)

## Summary
This round of Devin agent tests is targeted to evaluate Agent Preview with GPT-5.
The agent preview shows about the same performance as the standard agent.

### Distinctive Features
- Devin is provided as Software as a Service. It works in cloud and generates solutions as pull requests to a client project GitHub repository.
- Devin integrates into the repository as a GitHub App and can respond to pull request comments.

## Testing

### Environment
| Item              | Version                 |
|-------------------|-------------------------|
| Devin AI          | N/A                     |
| Payment Plan      | Core (pay as you go)    |
| Default Model     | Undisclosed             |

### Code Generation Findings
- node.js/npm and python/pip centricity has been gone way and replaced with universal setup.
- May introduce unrequested changes.
- May leave legacy artifacts like comments for removed code generated within earlier iterations.
- May generate unnecessary code just following learned patterns not suitable in the current context.
- May generate a simplified solution following to learned wide-spread low-quality samples.
- May generated custom code instead of using the library/framework capabilities.
- It may be a laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions how to improve and/or fix the solution code.
- Can ask clarifying questions.

### Testing Approach
Due to SaaS nature of Devin we have to develop a specific setup for the testing.

Devin works with GitHub repository as a GitHub App, so a new repository is created to perform set of test on Golf application codebase.

#### Repository Initialization
- Create github repo in github
- Download zip from https://github.com/PolinaTolkachova/golf-application/
- Clone the repo:
  ```
  git clone git@github.com:user/golfapp-playground.git
  cd golfapp-playground
  ```
- Unpack sources:
  ```bash
  ln -s . golf-application-main
  unzip golf-application-main.zip
  rm golf-application-main
  ```
- Initial commit:
  ```bash
  git status
  git add src pom.xml README.md LICENSE .gitignore
  git commit -m "initial commit"
  git push origin main
  ```
#
### Repository Setup in Devin
Custom configurations:
- Install Dependencies
  ```bash
  sudo apt install maven -y
  ```
- Maintain Dependencies
  ```bash
  cd ~/repos/golfapp-playground && mvn clean install
  ```
- Setup Lint
  ```bash
  mvn compile
  ```
- Setup Tests
  ```bash
  mvn test
  ```
- Setup Local App
  ```bash
  mvn spring-boot:run
  ```

### Test Report
| No | Sourcecode Repository | Task Summary (Name/Category/Complexity) | Task Description (Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts (Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|----|------------------------|-----------------------------------------|-----------------------------------|-------------------|-------------------------|---------------------|------------------------------------------|--------------------|----------------|-----------|----------|
| 1 | https://github.com/PolinaTolkachova/golf-application | Id: 0001<br>Name: Make reverse engineering of DB schema and make it manageable with Flyway<br>Category: code-refactoring<br>Complexity: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md | N/A | 19%<br>- DB migration failed due to DATABASE SCHEMA errors<br>- Database schema validation failed during the application launch<br>- Hibernate configuration is not changed to validating database schema<br>- Testing could not be performed due to the application launch errors | 76%<br>- The intended functionality is not accomplished<br>- MySQL syntax errors<br>- Table and column naming conventions are inconsistent (mixed camelCase vs snake_case, uppercase table names).<br>- The SQL script contains inconsistent formatting and naming across statements | 1)<br>Flyway migrations failed with the following error:<br>Message: (conn=241) You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'IF NOT EXISTS `round_id` BIGINT NULL,<br>Location: src/main/resources/db/migration/V1__init_schema.sql<br>Line: 107<br>Caused by: java.sql.SQLSyntaxErrorException: ... near 'IF NOT EXISTS `round_id` BIGINT NULL,<br>Caused by: org.mariadb.jdbc.internal.util.exceptions.MariaDbSqlException: ... near 'IF NOT EXISTS `round_id` BIGINT NULL,<br>Caused by: java.sql.SQLException: ... near 'IF NOT EXISTS `round_id` BIGINT NULL,<br>  ADD KEY `idx_player_round_id_m` (`round_' at line 2<br><br>2)<br>The application failed to launch:<br>SchemaManagementException: Schema-validation: missing table [competition]<br><br>3)<br>Change spring.jpa.hibernate.ddl-auto to validate to allow Flyway to manage the schema. Do not alter Hibernate naming strategy, use the one existing before submitting the task. | 100% | 94%<br>- Expose database credentials in version-controlled configuration files | Files:<br>1 modified (M)<br>3 added (A)<br>0 deleted (D)<br><br>Lines:<br>359 insertions (+)<br>1 deletions (-) |  |
| 2 | https://github.com/PolinaTolkachova/golf-application | Id: 0003<br>Name: Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br>Category: code-refactoring<br>Complexity: High | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md | N/A | 75%<br>- The external authorization server is not configured, but added hardcoded JWT decoder instead | 83%<br>- The code lacks necessary documentation | 1)<br>The hardcoded JWT decoder is good at the beginning of development, but it does not suit for production or integration testing.<br><br>2)<br>The resource server is not configured in application.properties, but security.jwt.secret is | 100% | 83%<br>- The code lacks necessary documentation | Files:<br>4 modified (M)<br>2 added (A)<br>0 deleted (D)<br><br>Lines:<br>78 insertions (+)<br>56 deletions (-) |  |
| 3 | https://github.com/PolinaTolkachova/golf-application | Id: 0004<br>Name: Return round scores in CSV format in Golf application<br>Category: solution-or-component-generation<br>Complexity: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md | N/A | 59%<br>- Spring HTTP Message Conversion is not utilized<br>- A proven CSV processing library is not used to write CSV | 72%<br>- The implementation mixes presentation concerns with business logic, the CSV is built with controller<br>- The code lacks necessary documentation | 1)<br>Spring's message conversion mechanism is not utilized<br><br>2)<br>I do not like the idea to convert RoundScore to intermediate type RoundScoreCsvRow in controller and to use the type in HttpMessageConverter. Please use the original type in HttpMessageConverter.<br><br>3)<br>The CSV generation is handled manually using OutputStreamWriter and StringBuilder, which is error-prone. | 100% | 83%<br>- The code lacks necessary documentation | Files:<br>3 modified (M)<br>1 added (A)<br>0 deleted (D)<br><br>Lines:<br>107 insertions (+)<br>2 deletions (-) |  |
| 4 | https://github.com/PolinaTolkachova/golf-application | Id: 0008<br>Name: Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br>Category: solution-migration<br>Complexity: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md | N/A | 95%<br>- logging.level.* properties are not removed from application.properties<br>- The configuration uses RollingFile rather than RollingRandomAccessFile | 100% | 1)<br>Would RollingRandomAccessFile be better for performance?<br><br>2)<br>logging.level.* properties are not removed from application.properties | 100% | 100% | Files:<br>7 modified (M)<br>2 added (A)<br>2 deleted (D)<br><br>Lines:<br>112 insertions (+)<br>80 deletions (-) |  |
| 5 | https://github.com/PolinaTolkachova/golf-application | Id: 0011<br>Name: Migrate in-memory user and role definitions to database in Golf application<br>Category: code-refactoring<br>Complexity: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md | N/A | 100% | 86%<br>- Added unrequested Flyway dependency to runtime<br>- The migration script inserts passwords using `{noop}` (plaintext) which exposes credentials | 1) The migration script inserts passwords using `{noop}` (plaintext) which exposes credentials | 100% | 92%<br>- Added unrequested Flyway dependency to runtime | Files:<br>3 modified (M)<br>2 added (A)<br>0 deleted (D)<br><br>Lines:<br>48 insertions (+)<br>25 deletions (-) |  |
| 6 | https://github.com/PolinaTolkachova/golf-application | Id: 0014<br>Name: User Account Menu in Golf application<br>Category: solution-or-component-generation<br>Complexity: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md | N/A | 7%<br>- The dependency org.thymeleaf.extras:thymeleaf-extras-springsecurity6 is not added to pom.xml<br>- Multiple issues with adding the account menu to the templates<br>- Template parsing errors<br>- Tests could not be performed | 69%<br>- The intended functionality is not accomplished<br>- The Thymeleaf template crashes at runtime<br>- The use of inline style="..." attributes conflicts with the existing CSS organization<br>- Inline CSS and cramped markup reduce readability and violate separation of concerns<br>- The standard Thymeleaf/Spring Security approaches is not used. | 1)<br>ERROR org.thymeleaf.TemplateEngine - [THYMELEAF][http-nio-8082-exec-2] Exception processing template "home": An error happened during template parsing (template: "class path resource [templates/home.html]")<br>org.thymeleaf.exceptions.TemplateInputException: An error happened during template parsing (template: "class path resource [templates/home.html]")<br>Caused by: org.attoparser.ParseException: Exception evaluating SpringEL expression: "#httpServletRequest.remoteUser" (template: "blocks/header" - line 17, col 27)<br>Caused by: org.springframework.expression.spel.SpelEvaluationException: EL1007E: Property or field 'remoteUser' cannot be found on null<br><br>2)<br>Accessing the username via `#httpServletRequest.remoteUser` is not a standard or supported Thymeleaf/Spring Security approach. | 19%<br>- The dependency org.thymeleaf.extras:thymeleaf-extras-springsecurity6 is not added to pom.xml<br>- Multiple issues with adding the account menu to the templates<br>- Template parsing errors<br>- Tests could not be performed | 69%<br>- The intended functionality is not accomplished<br>- The Thymeleaf template crashes at runtime<br>- The use of inline style="..." attributes conflicts with the existing CSS organization<br>- Inline CSS and cramped markup reduce readability and violate separation of concerns<br>- The standard Thymeleaf/Spring Security approaches is not used. | Files:<br>1 modified (M)<br>0 added (A)<br>0 deleted (D)<br><br>Lines:<br>16 insertions (+)<br>8 deletions (-) |  |
| 7 | https://github.com/PolinaTolkachova/golf-application | Id: 0016<br>Name: Fix an issue with competition removing in Golf application<br>Category: code-bugfixing<br>Complexity: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md | N/A |  |  |  |  |  |  |  |

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
