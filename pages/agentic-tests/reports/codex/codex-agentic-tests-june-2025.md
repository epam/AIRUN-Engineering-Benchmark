# OpenAI Codex Tests - June 2025

## Table of Contents
- [Summary](#summary)
- [Testing](#testing)
    - [Environment](#environment)
    - [Code Generation Findings](#code-generation-findings)
    - [Testing Approach](#testing-approach)
        - [Repository Initialization](#repository-initialization)
        - [Codex Environment Customization](#codex-environment-customization)
    - [Test Report](#test-report)

## Summary
OpenAI Codex is a cloud-based software engineering agent powered by a version of OpenAI o3 that's fine-tuned for real-world software development. The agent integrates directly with GitHub repositories. When given a task, Coded launches a container in a cloud, warm up a preconfigured environment, clones the codebase, and performs the task, having access to most of development tools.

The agent showed one of the best performance among the examined agents. It mostly successfully completed the assigned tasks with minor issues.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. In response, the agent generated solutions affecting from 2 files and 20 code lines till 10 files and 310 code lines. It took from 1 to 7 iterations to complete the given development either successfully or to prove that further agent-assisted development was not reasonable.

## Testing

### Environment
|                | Version |
|----------------|---------|
| OpenAI Codex   | N/A     |
| Payment Plan   | Team    |
| Default Model  | OpenAI o3 |

### Code Generation Findings
- Commit messages are poorly written, they don't convey what specific changes were made or why. On contrary, pull request summaries are generally good.
- Relatively long solution generation time.
- Each request processing is prepended with a new container start accompanied by environment setup. It takes time.
- Extra time can be spent to finish suggested secondary functionality. For instance, the agent suggested dev setup for issuing access tokens and omitted prod setup with external auth server.
- Supports generation solution in multiple versions, up to 4. However, the profit is debatable. One case is tested, but the versions didn't differ noticeably, the agent suggested just three variations of one solution, although there could be at least two diverse variants.

### Testing Approach
Due to SaaS nature of Codex we have to develop a specific setup for the testing.

Codex works with GitHub repository, so a new repository is created to perform set of test on Golf application codebase.

#### Repository Initialization
- Create github repo in github
- Download zip from https://github.com/PolinaTolkachova/golf-application/
- git clone git@github.com:user/golfapp-playground.git
- cd golfapp-playground
- ln -s . golf-application-main  
  unzip golf-application-main.zip  
  rm golf-application-main
- git status  
  git add src pom.xml README.md LICENSE .gitignore  
  git commit -m "initial commit"  
  git push origin main

#### Codex Environment Customization
- Repository: the created repository
- Sharing: Only you
- Container image: Universal
- Agent internet access: Common dependencies
- Additional allowed domains: cdn.jsdelivr.net, ajax.googleapis.com, maxcdn.bootstrapcdn.com, getbootstrap.com
- Setup script:
```bash
sudo apt update
sudo apt install maven -y

mkdir -p ~/.m2
cat > ~/.m2/settings.xml <<EOF
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.2.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.2.0 https://maven.apache.org/xsd/settings-1.2.0.xsd">
  <proxies>
    <proxy>
      <id>codexProxy</id>
      <active>true</active>
      <protocol>http</protocol>
      <host>proxy</host>
      <port>8080</port>
    </proxy>
  </proxies>
</settings>

EOF

mvn -v
```

### Test Report
| # | Sourcecode Repository | Task Summary (Name/Category/Complexity) | Task Description (Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts (Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | https://github.com/PolinaTolkachova/golf-application | Id: 0001<br><b>Name</b>: Make reverse engineering of DB schema and make it manageable with Flyway<br><b>Category</b>: code-refactoring<br><b>Complexity</b>: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0001/README.md | N/A | 46%<br>- The Flyway migration resulted in an error: Failed to open the referenced table 'player'<br>- Hibernate configuration is not changed from updating database schema to validating database schema<br>- The application failed to start due to a database schema validation error<br>- Testing was not performed due to the application failing to launch correctly | 66%<br>- The created DML script does not fully cover all necessary tables or relationships defined in the Java entities.<br>- The code does not accomplish the intended functionality due to incomplete database migrations: missing tables/columns | 1)<br>ERROR: Migration of schema `golf04` to version "1 - init" failed!<br>Message    : (conn=9) Failed to open the referenced table 'player'<br>Location   : src\main\resources\db\migration\V1__init.sql<br>Line       : 93<br><br>2)<br>org.hibernate.tool.schema.spi.SchemaManagementException: Schema-validation: missing table [competition_judges]<br><br>3)<br>org.hibernate.tool.schema.spi.SchemaManagementException: Schema-validation: missing column [players_id] in table [competition_players]<br><br>4)<br>org.hibernate.tool.schema.spi.SchemaManagementException: Schema-validation: wrong column type encountered in column [gender] in table [player]; found [varchar (Types#VARCHAR)], but expecting [tinyint (Types#TINYINT)]<br><br>5)<br>org.hibernate.tool.schema.spi.SchemaManagementException: Schema-validation: missing table [round_roundscores]<br><br>6)<br>org.hibernate.tool.schema.spi.SchemaManagementException: Schema-validation: missing table [round_score_scores] | 92%<br>- Hibernate configuration is not changed from updating database schema to validating database schema | 100% | Files:<br>0 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>310 insertions(+)<br>0 deletions(-) |  |
| 2 | https://github.com/PolinaTolkachova/golf-application | Id: 0003<br><b>Name</b>: Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><b>Category</b>: code-refactoring<br><b>Complexity</b>: High | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0003/README.md | N/A | 60%<br>- External authorization server is not configured<br>- Access restriction configuration has not been fully completed | 70%<br>- The application authorization functionality is not accomplished | 1)<br>I try to get token with the request below and get HTTP/1.1 401:<br>curl -v -X POST http://localhost:8082/token -H "Content-Type: application/json" -d '{"subject":"user","scope":"GOLF:ADMIN"}'<br><br>2)<br>Requesting token still fails:<br>curl -v -X POST http://localhost:8082/token -H "Content-Type: application/json" -d '{"subject":"a","scope":"GOLF:ADMIN"}'<br>&lt; HTTP/1.1 401<br>&lt; Vary: Origin<br>&lt; Vary: Access-Control-Request-Method<br>&lt; Vary: Access-Control-Request-Headers<br>&lt; WWW-Authenticate: Bearer<br><br>3)<br>Requesting token still fails. The error is logged:<br>2025-06-12T14:39:20.422 [http-nio-8082-exec-2] ERROR o.a.c.c.C.[.[.[.[dispatcherServlet] -  Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed: org.springframework.security.oauth2.jwt.JwtEncodingException: An error occurred while attempting to encode the Jwt: Failed to select a JWK signing key] with root cause<br>org.springframework.security.oauth2.jwt.JwtEncodingException: An error occurred while attempting to encode the Jwt: Failed to select a JWK signing key<br><br>4)<br>Issuing of tokens within the application is good for dev environment. Keep the functionality if dev profile is activated. Configure external authorization server to be used by the application by default. | 100% | 90%<br>- The `TokenController` class lacks comprehensive exception handling. While it handles basic token generation, it does not account for potential issues such as invalid input data or failures during token encoding. | Files:<br>4 modified(M)<br>3 added(A)<br>0 deleted(D)<br><br>Lines:<br>123 insertions(+)<br>41 deletions(-) | The initial solution supposes configuration of embedded authorization server and token issuig, that is not applicable for production. |
| 3 | https://github.com/PolinaTolkachova/golf-application | Id: 0004<br><b>Name</b>: Return round scores in CSV format in Golf application<br><b>Category</b>: solution-or-component-generation<br><b>Complexity</b>: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0004/README.md | N/A | 100% | 66%<br>- The new CSV generation method does not include exception handling<br>- The CSV response is constructed manually using `StringBuilder` instead of leveraging Spring's HTTP message converters<br>- The CSV is built manually without using a proven library<br>- The default RoundScoreController GET endpoint has suddenly changed to produce "text/html" solely | 1)<br>The CSV response is constructed manually using `StringBuilder` instead of leveraging Spring's HTTP message converters<br><br>2)<br>Preserve the default RoundScoreController GET endpoint producing all media types other than "text/csv"<br><br>3)<br>The CSV headers defined in `RoundScoreCsvDto` do not precisely match the headers expected by the `scorecardsTable` in `round-score-main.html`<br><br>4)<br>The controller method `displayScoreCardMainPageCsv` does not include exception handling mechanisms. If unexpected errors occur during CSV generation or data retrieval, it may lead to unhandled exceptions, potentially causing the application to crash or behave unpredictably.<br><br>5)<br>I am not sure that converting RoundScore to RoundScoreCsvDto directly in the controller is a good practice | 100% | 100% | Files:<br>2 modified(M)<br>4 added(A)<br>0 deleted(D)<br><br>Lines:<br>235 insertions(+)<br>1 deletions(-) |  |
| 4 | https://github.com/PolinaTolkachova/golf-application | Id: 0008<br><b>Name</b>: Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><b>Category</b>: solution-migration<br><b>Complexity</b>: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0008/README.md | N/A | 86%<br>- LMAX Disruptor is not used<br>- Not all Log4j2 loggers are effectively configured as asynchronous<br>- `RollingRandomAccessFile` appender is not added to log4j2 config, `File` appender is used instead<br>- logs/golf-app.log file is empty<br>- logging properties are not removed from application.properties | 81%<br>- The changes introduced runtime issue: java.lang.NoClassDefFoundError: com/lmax/disruptor/EventHandler<br>- The performance optimizations intended through Log4j2’s asynchronous capabilities are not fully realized due to incomplete configuration | 1)<br>ERROR StatusConsoleListener Could not create plugin of type class<br>org.apache.logging.log4j.core.async.AsyncLoggerConfig$RootLogger for element AsyncRoot: java.lang.NoClassDefFoundError: com/lmax/disruptor/EventHandler<br> java.lang.NoClassDefFoundError: com/lmax/disruptor/EventHandler<br><br>2)<br>Would RollingRandomAccessFile be better for performance?<br><br>3)<br>It seems, synchronous loggers are used. Could you review Log4j2 configuration if it fully optimized for performance? | 96%<br>- logging properties are not removed from application.properties | 100% | Files:<br>6 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>96 insertions(+)<br>77 deletions(-) |  |
| 5 | https://github.com/PolinaTolkachova/golf-application | Id: 0011<br><b>Name</b>: Migrate in-memory user and role definitions to database in Golf application<br><b>Category</b>: code-refactoring<br><b>Complexity</b>: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0011/README.md | N/A | 100% | 100% |  |  | Files:<br>1 modified(M)<br>2 added(A)<br>0 deleted(D)<br><br>Lines:<br>28 insertions(+)<br>23 deletions(-) |  |
| 6 | https://github.com/PolinaTolkachova/golf-application | Id: 0014<br><b>Name</b>: User Account Menu in Golf application<br><b>Category</b>: solution-or-component-generation<br><b>Complexity</b>: Low | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0014/README.md | N/A | 75%<br>- thymeleaf-extras-springsecurity6 is not added in header.html<br>- bootstrap.bundle.min.js is not imported on pages with account menu<br>- the account menu does not expand downwards as intended | 88%<br>- the intended functionality is not accomplished | 1)<br>The account menu does not expand down<br><br>2)<br>The account menu is cut off at the right side of the window<br><br>3)<br>Wouldn't it be better to use Bootstrap to visualize menu instead of custom javascript code?<br><br>4)<br>The account menu is cut off by vertical scrollbar on pages with long content<br><br>5)<br>The account menu is cut off by vertical scrollbar on pages with long content anyway<br><br>6)<br>Prevent cutting off the account menu with a vertical scrollbar appearing on pages with long content | 100% | 90%<br>- The account menu is cut off by vertical scrollbar on pages with long content | Files:<br>2 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>26 insertions(+)<br>4 deletions(-) |  |
| 7 | https://github.com/PolinaTolkachova/golf-application | Id: 0016<br><b>Name</b>: Fix an issue with competition removing in Golf application<br><b>Category</b>: code-bugfixing<br><b>Complexity</b>: Medium | See https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/blob/main/agentic-workflow-tests/0016/README.md | N/A | 100% | 90%<br>- The `deleteCompetition` method is mapped to a `POST` request (`@PostMapping("/{id}/remove"`). According to RESTful best practices, deletion operations should use the `DELETE` HTTP method. | 1)<br>The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method<br><br>2)<br>Use @DeleteMapping("/{id}") instead of @DeleteMapping("/{id}/remove") | 100% | 100% | Files:<br>3 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>19 insertions(+)<br>1 deletions(-) |  |

<p style="text-align: center;">    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
