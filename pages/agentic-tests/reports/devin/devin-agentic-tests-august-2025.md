# Devin AI Agent Tests - August 2025

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
This is a next round of Devin agent tests. The new version has obtained universal setup, node.js/npm and python/pip centricity has been gone away.

It is revealed that the agent becomes more expensive. Worth mentioning that the payment policy is not transparent and too arbitrary. Session fees are not linked to successful completion of tasks, the user is also forced to pay for unsuccessful attempts at solving.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing.

It turned out that the new version of the agent shows worse performance than before.

### Distinctive Features
- Devin is provided as Software as a Service. It works in cloud and generates solutions as pull requests to a client project GitHub repository.
- Devin integrates into the repository as a GitHub App and can respond to pull request comments.

## Testing

### Environment
| Item | Version |
|---|---|
| Devin AI | N/A |
| Payment Plan | Core (pay as you go) |
| Default Model | Undisclosed |

### Code Generation Findings
- node.js/npm and python/pip centricity has been gone away and replaced with universal setup.
- May introduce unrequested changes.
- May generate a simplified solution following to learned wide-spread low-quality samples.
- May generated custom code instead of using the library/framework capabilities.
- It may be a laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions how to improve and/or fix the solution code.

### Testing Approach
Due to SaaS nature of Devin we have to develop a specific setup for the testing.

Devin works with GitHub repository as a GitHub App, so a new repository is created to perform set of test on Golf application codebase.

#### Repository Initialization
- Create github repo in github
- Download zip from https://github.com/PolinaTolkachova/golf-application/
- `git clone git@github.com:user/golfapp-playground.git`
- `cd golfapp-playground`
-
```
ln -s . golf-application-main
unzip golf-application-main.zip
rm golf-application-main
```
-
```
git status
git add src pom.xml README.md LICENSE .gitignore
git commit -m "initial commit"
git push origin main
```

#### Repository Setup in Devin
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
| No | Sourcecode Repository | Task Summary<br>Name/Category/Complexity | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---:|---|---|---|---|---|---|---|---|---|---|---|
| 1 | https://github.com/PolinaTolkachova/golf-application | Id: 0001<br><strong>Name</strong>: Make reverse engineering of DB schema and make it manageable with Flyway<br><strong>Category</strong>: code-refactoring<br><strong>Complexity</strong>: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md | N/A | 35%<br>- The database schema validation failed<br>- Hibernate configuration is not changed to validating database schema<br>- The application failed to launch due to invalid column type<br>- Manual test couldn't be performed due to application start issues | 92%<br>- The intended functionality is not accomplished | 1)<br>Schema-validation: wrong column type encountered in column [gender] in table [player]; found [varchar (Types#VARCHAR)], but expecting [tinyint (Types#TINYINT)]<br><br>2)<br>Schema-validation: missing table [round_roundscores] | 85%<br>- Hibernate configuration has not been changed from updating database schema to validating database schema | 100% | Files:<br>1 modified (M)<br>5 added (A)<br>0 deleted (D)<br><br>Lines:<br>669 insertions (+)<br>0 deletions (-) |  |
| 2 | https://github.com/PolinaTolkachova/golf-application | Id: 0003<br><strong>Name</strong>: Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><strong>Category</strong>: code-refactoring<br><strong>Complexity</strong>: High | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md | N/A | 86%<br>- The authorization server is not configured<br>- The application failed to launch | 66%<br>- The intended functionality is not accomplished<br>- Authentication and authorization are configured improperly | 1)<br>Error starting ApplicationContext:<br>Parameter 0 of method setFilterChains in org.springframework.security.config.annotation.web.configuration.WebSecurityConfiguration required a bean of type 'org.springframework.security.oauth2.jwt.JwtDecoder' that could not be found.<br><br>2)<br>Error while attempting to get http://localhost:8082/admin with scope GOLF:ADMIN:<br>HTTP/1.1 401<br>WWW-Authenticate: Bearer error="invalid_token", error_description="An error occurred while attempting to decode the Jwt: Signed JWT rejected: Another algorithm expected, or no matching key(s) found", error_uri="https://tools.ietf.org/html/rfc6750#section-3.1"<br><br>Answers:<br>- Use recommended option: add a sample issuer URI to application.properties<br><br>3)<br>Error while attempting to get http://localhost:8082/admin with scope GOLF:ADMIN:<br>HTTP/1.1 403<br>WWW-Authenticate: Bearer error="insufficient_scope", error_description="The request requires higher privileges than provided by the access token.", error_uri="https://tools.ietf.org/html/rfc6750#section-3.1"<br><br>4)<br>By the way, it seems defining JwtDecoder bean is redundant. Spring Boot auto-configures the bean. | 100% | 100% | Files:<br>13 modified (M)<br>2 added (A)<br>0 deleted (D)<br><br>Lines:<br>134 insertions (+)<br>38 deletions (-) |  |
| 3 | https://github.com/PolinaTolkachova/golf-application | Id: 0004<br><strong>Name</strong>: Return round scores in CSV format in Golf application<br><strong>Category</strong>: solution-or-component-generation<br><strong>Complexity</strong>: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md | N/A | 52%<br>- The default RoundScoreController GET endpoint is not preserved<br>- Spring HTTP Message Conversion is not utilized<br>- The code does not utilize a proven CSV processing library to write CSV | 72%<br>- The code does not handle edge cases, for instance null values<br>- CSV-generation logic is embedded in the controller instead of being delegated to a service or utility layer<br>- The CSV generation logic lacks necessary documentation | 1)<br>Spring's message conversion mechanism is not utilized<br><br>2)<br>Error while getting round scores as CSV:<br>ERROR org.thymeleaf.TemplateEngine - [THYMELEAF][http-nio-8082-exec-2] Exception processing template "round-score": Error resolving template [round-score], template might not exist or might not be accessible by any of the configured Template Resolvers<br>org.thymeleaf.exceptions.TemplateInputException: Error resolving template [round-score], template might not exist or might not be accessible by any of the configured Template Resolvers<br><br>3)<br>Writing CSV manually with OutputStreamWriter is error-prone. The code does not handle edge cases.<br>For instance, the error is logged:<br>ERROR o.a.c.c.C.[.[.[.[dispatcherServlet] - Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed: java.lang.NullPointerException: Cannot invoke "java.lang.Integer.toString()" because the return value of "com.golf.app.model.Score.getStroke()" is null] with root cause<br>java.lang.NullPointerException: Cannot invoke "java.lang.Integer.toString()" because the return value of "com.golf.app.model.Score.getStroke()" is null<br><br>3)<br>The issue has been fixed. But the implementation still builds a CSV text manually, this leads to errors and maintainance issues.<br><br>4)<br>Use a proven CVS processing library to write CSV<br><br>5)<br>Keep RoundScoreController displayScoreCardMainPage() method returning response by default, not only for "text/html". | 100% | 75%<br>- Unused imports<br>- The CSV generation logic lacks necessary documentation | Files:<br>3 modified (M)<br>3 added (A)<br>0 deleted (D)<br><br>Lines:<br>225 insertions (+)<br>1 deletions (-) |  |
| 4 | https://github.com/PolinaTolkachova/golf-application | Id: 0008<br><strong>Name</strong>: Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><strong>Category</strong>: solution-migration<br><strong>Complexity</strong>: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md | N/A | 74%<br>- LMAX Disruptor dependency is not added<br>- RollingRandomAccessFile appender is not used in log4j2.xml<br>- logs/golf-app.log file is created but empty<br>- The application failed to start due to class-loading errors | 92%<br>- The intended functionality is not accomplished | 1)<br>ERROR StatusConsoleListener Could not create plugin of type class org.apache.logging.log4j.core.async.AsyncLoggerConfig for element AsyncLogger: java.lang.NoClassDefFoundError: com/lmax/disruptor/EventHandler<br>java.lang.NoClassDefFoundError: com/lmax/disruptor/EventHandler<br><br>2)<br>`log.debug("Round players: {}", round.getRoundplayers().stream().map(Player::getName).toList());` affects app performance.<br><br>3)<br>Would RollingRandomAccessFile be better for performance? | 100% | 100% | Files:<br>7 modified (M)<br>1 added (A)<br>2 deleted (D)<br><br>Lines:<br>109 insertions (+)<br>75 deletions (-) |  |
| 5 | https://github.com/PolinaTolkachova/golf-application | Id: 0011<br><strong>Name</strong>: Migrate in-memory user and role definitions to database in Golf application<br><strong>Category</strong>: code-refactoring<br><strong>Complexity</strong>: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md | N/A | 100% | 100% | Not required |  | Files:<br>2 modified (M)<br>2 added (A)<br>0 deleted (D)<br><br>Lines:<br>33 insertions (+)<br>22 deletions (-) |  |
| 6 | https://github.com/PolinaTolkachova/golf-application | Id: 0014<br><strong>Name</strong>: User Account Menu in Golf application<br><strong>Category</strong>: solution-or-component-generation<br><strong>Complexity</strong>: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md | N/A | 64%<br>- Bootstrap bundle is not utilized on pages with account menu<br>- The account menu is not functional<br>- The application failed to launch | 83%<br>- The intended functionality is not accomplished<br>- Introducing H2 database is far beyond adding the account menu | 1)<br>Replacing of MySql database with H2 database is far beyond adding the account menu. The changes were not requested.<br><br>2)<br>The account menu does not expand downwards on the app pages.<br><br>3)<br>The account menu does not expand downwards anyway.<br><br>4)<br>jQuery should not be mixed with Bootstrap.<br><br>5)<br>The account menu still does not expand downwards on<br>"ADD PLAYER" page, "PLAYER DETAILS" page, "EDIT PLAYER" page,<br>"COMPETITION DETAILS" page, "COMPETITION ROUND DETAILS" pages,<br>"ADD COURSE" page. | 100% | 100% | Files:<br>23 modified (M)<br>0 added (A)<br>0 deleted (D)<br><br>Lines:<br>62 insertions (+)<br>39 deletions (-) |  |
| 7 | https://github.com/PolinaTolkachova/golf-application | Id: 0016<br><strong>Name</strong>: Fix an issue with competition removing in Golf application<br><strong>Category</strong>: code-bugfixing<br><strong>Complexity</strong>: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md | N/A | 83%<br>- The solution uses POST HTTP method for competition deletion instead of DELETE | 97%<br>- The new code uses `java.util.logging.Logger` instead of SLF4J logger | 1)<br>Using POST instead of DELETE HTTP method violates RESTful principles.<br><br>2)<br>Use @DeleteMapping("/{id}") instead of @DeleteMapping("/{id}/remove")<br><br>3)<br>The new code uses `java.util.logging.Logger` instead of SLF4J logger<br><br>4)<br>The new code uses `java.util.logging.Logger` instead of SLF4J logger | 100% | 100% | Files:<br>4 modified (M)<br>0 added (A)<br>0 deleted (D)<br><br>Lines:<br>27 insertions (+)<br>2 deletions (-) |  |

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
