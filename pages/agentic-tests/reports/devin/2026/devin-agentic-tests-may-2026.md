# Devin AI Agent Tests — May 2026

## Summary

This is a next round of agentic testing of Devin, a coding agent from Cognition. The tests were performed on cloud-based Devin instance running in a virtual machine in cloud.

The agent has shown better results than in February 2026 and returned back to the top-performers.

The agent has been examined with tasks belonging to various categories such as solution-or-component-generation, solution-migration, code-refactoring, code-bugfixing. The agent responded reasonably to the feedback, which allowed to successfully achieve a goal in a minimum number of steps. However the agent may suggest plain straightforward solutions. The generated code should be supervised by an experienced developer to prevent defects and technical debt introduction.

## Distinctive Features

- Since beginning Devin is provided as Software as a Service. The agent works in cloud and generates solutions as pull requests to a client project GitHub repository. Also Devin is built directly into Windsurf IDE since 2.0 version so the work can be delegated to the cloud and the results are reviewed without leaving the IDE.
- Devin cloud agent integrates into the repository as a GitHub App and can respond to pull request comments.
- Recently Devin for Terminal is introduced. It is a local coding agent running directly in terminal and working with local files and environment, giving fast, interactive assistance right on local workstation. Devin for Terminal is built into Windsurf IDE too.
- Devin cloud-based agent runs in a virtual machine. It includes features like Playbooks, Secrets, Knowledge, and other capabilities that are not available in Devin for Terminal.

## Testing

### Environment

| Component | Version |
|---|---|
| Devin AI | 2.2 |
| Payment Plan | Pro |
| Model(s) | Auto-selected by agent |

## Code Generation Findings

- Supports guided agent-assisted setup of the repository and development environment.
- May generate unnecessary custom code replacing the library/framework capabilities.
- May suggest a simplified straightforward solution. It is laborious and time-consuming to force the agent to rework the solution following a better approach. A developer has to provide a lot of granular instructions how to improve and/or fix the solution code.
- Has a Test The App functionality (beta) running the developed feature testing by explicit request. Creates a test plan and performs testing against it. Creates a test report with testing results. However the testing process is boring and long-running. An experienced developer able to complete the testing 5x..10x quicker. In any case, it allows to find and fix most trivial and/or spillover issues in the generated solution.
- Able to set up the test environment, for instance launch Docker container for MySql.
- May create tests to validate the generated solution.
- Able to control the browser to test the application UI features.
- Can create a skill memorizing the obtained development experience.
- Has a Review with Devin functionality allowing to review the generated solution.
- A task solving session can be quite expensive, especially within purchased on-demand usage (after the quota included in the plan has been spent).

## Testing Customization

General golf-application rules for agents are added as file `AGENTS.md`.

## Testing Approach

Due to SaaS nature of Devin we have to develop a specific setup for the testing.

Devin works with GitHub repository as a GitHub App, so a new repository is created to perform set of test on Golf application codebase.

### Repository Initialization

```bash
Create github repo in github
Download zip from https://github.com/PolinaTolkachova/golf-application/
git clone git@github.com:user/golfapp-devin-20260212-01.git
cd golfapp-devin-20260212-01
ln -s . golf-application-main
unzip golf-application-main.zip
rm golf-application-main
git status
git add src pom.xml README.md LICENSE .gitignore AGENTS.md
git commit -m "initial commit"
git push origin main
```

### Repository Indexing

Index the repository on https://app.devin.ai.

### Repository Setup

Custom configurations:

#### Gil pull

```bash
cd ~/repos/golfapp-devin-20260512-01 && git pull && git submodule update --init --recursive
```

#### Install Dependencies

```bash
sudo apt install maven -y
```

#### Maintain Dependencies

```bash
mvn dependency:resolve -q
```

#### Setup Lint

```bash
mvn clean compile -DskipTests
```

#### Setup Tests

```bash
mvn test
```

#### Local App Testing instructions

```bash
# App listens on http://localhost:8082
mvn spring-boot:run
```

## Test Report

| # | Run | Sourcecode Repository | Task Summary | Task Description<br>(Initial Prompt) | First-Shot Effort | First-Shot Completeness | First-Shot Accuracy | Subsequent Prompts<br>(Feedback, Comments) | Final Completeness | Final Accuracy | Statistics | Comments |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | VM01 | https://github.com/PolinaTolkachova/golf-application | **Id:** 0001<br><br>**Name:** Make reverse engineering of DB schema and make it manageable with Flyway<br><br>**Category:** code-refactoring<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0001/README.md` | N/A | 85%<br><br>- Hibernate configuration is not changed from updating database schema to validating database schema. | 89%<br><br>- Using the root user as the application database user leads to security risks.<br>- Exposes sensitive data in sources. | 1) Hibernate configuration is not changed from updating database schema to validating database schema.<br><br>2) Prevent user credentials expose in docker-compose.yml, flyway.conf.<br><br>3) Using the root user as the application database user leads to security risks. | 100% | 100% | Files:<br>2 modified(M)<br>4 added(A)<br>0 deleted(D)<br><br>Lines:<br>398 insertions(+)<br>4 deletions(-) | |
| 2 | VM01 | https://github.com/PolinaTolkachova/golf-application | **Id:** 0003<br><br>**Name:** Refactor Golf application access-control layer, replace Basic Authentication with Oauth2 Authorization<br><br>**Category:** code-refactoring<br><br>**Complexity:** High | See `agentic-workflow-tests/0003/README.md` | N/A | 100% | 100% | Not required | 100% | 100% | Files:<br>4 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>156 insertions(+)<br>94 deletions(-) | |
| 3 | VM01 | https://github.com/PolinaTolkachova/golf-application | **Id:** 0004<br><br>**Name:** Return round scores in CSV format in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See `agentic-workflow-tests/0004/README.md` | N/A | 52%<br><br>- The default RoundScoreController GET endpoint was not preserved, but restricted to "text/html".<br>- Spring HTTP Message Conversion is not utilized.<br>- The code uses raw `StringBuilder` concatenation instead of a proven CSV processing library. | 72%<br><br>- Custom CSV generation code does not handle edge cases, exceptions.<br>- CSV generation is embedded in the controller.<br>- The CSV generation logic lacks necessary documentation. | 1) Spring's message conversion mechanism is not utilized.<br><br>2) Using StringBuilder is a poor and error-prone choice for CVS generation.<br><br>3) Regression: the default RoundScoreController GET endpoint is narrowed to "text/html" media type only. | 100% | 83%<br><br>- The CSV generation logic lacks necessary documentation. | Files:<br>2 modified(M)<br>2 added(A)<br>0 deleted(D)<br><br>Lines:<br>112 insertions(+)<br>0 deletions(-) | |
| 4 | VM01 | https://github.com/PolinaTolkachova/golf-application | **Id:** 0008<br><br>**Name:** Refactor Golf application, replace logback logging with Log4j 2.x logging framework and SLF4J as logging facade<br><br>**Category:** solution-migration<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0008/README.md` | N/A | 78%<br><br>- LMAX Disruptor is not added as dependency and it is not utilized.<br>- The application.properties still contains logging.level settings.<br>- Logging is not asynchronous in Log4j2 configuration.<br>- The configuration uses a `<RollingFile>` appender rather than a `<RollingRandomAccessFile>` appender.<br>- Log4j2 loggers are not configured as asynchronous. | 97%<br><br>- Logging within loop degrades performance. | 1) `logging.level.*` properties are not removed from application.properties. The created loggers are synchronous by default. It affects the logging performance.<br><br>2) Configure Log4j2 for maximum performance as it has been requested.<br><br>3) Logging within loop degrades performance. | 100% | 100% | Files:<br>7 modified(M)<br>2 added(A)<br>2 deleted(D)<br><br>Lines:<br>99 insertions(+)<br>85 deletions(-) | |
| 5 | VM01 | https://github.com/PolinaTolkachova/golf-application | **Id:** 0011<br><br>**Name:** Migrate in-memory user and role definitions to database in Golf application<br><br>**Category:** code-refactoring<br><br>**Complexity:** Low | See `agentic-workflow-tests/0011/README.md` | N/A | 100% | 100% | Not required | 100% | 100% | Files:<br>2 modified(M)<br>2 added(A)<br>0 deleted(D)<br><br>Lines:<br>44 insertions(+)<br>24 deletions(-) | |
| 6 | VM01 | https://github.com/PolinaTolkachova/golf-application | **Id:** 0014<br><br>**Name:** User Account Menu in Golf application<br><br>**Category:** solution-or-component-generation<br><br>**Complexity:** Low | See `agentic-workflow-tests/0014/README.md` | N/A | 85%<br><br>- Bootstrap bundle is not utilized to create the account menu.<br>- The account menu is not expandable sub-menu of main menu but just main menu items.<br>- An user is not redirected to proper login page after logout. | 88%<br><br>- The intended functionality is not fully accomplished.<br>- Custom CSS is generated instead of using Bootstrap adopted in the project. | 1) Try to rework the account menu using Bootstrap adopted in the project instead of custom JavaScript and CSS.<br><br>2) The account menu should be an expandable submenu, not just a few main menu items.<br><br>3) An user is redirected to unused sign in page instead of actual login page after logout where he can not login again: http://localhost:8082/login?logout | 100% | 100% | Files:<br>4 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>21 insertions(+)<br>1 deletions(-) | |
| 7 | VM01 | https://github.com/PolinaTolkachova/golf-application | **Id:** 0016<br><br>**Name:** Fix an issue with competition removing in Golf application<br><br>**Category:** code-bugfixing<br><br>**Complexity:** Medium | See `agentic-workflow-tests/0016/README.md` | N/A | 83%<br><br>- Using POST instead of DELETE HTTP method violates RESTful principles. | 100% | 1) The deletion endpoint uses the `POST` HTTP method instead of the more semantically appropriate `DELETE` method.<br><br>2) Please rewrite deletion using `@DeleteMapping("/{id}")` instead of `@DeleteMapping("/{id}/remove")`. | 100% | 100% | Files:<br>4 modified(M)<br>0 added(A)<br>0 deleted(D)<br><br>Lines:<br>14 insertions(+)<br>1 deletions(-) | |

## Agent's Final Grade

The agent's final grade is **83%**.

| Number | Tag | Subsequent Prompts Count | Performance | accuracy.first | completeness.first | accuracy.final | completeness.final | Grade |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 0001 | VM01 | 3 | 0.67 | 0.89 | 0.85 | 1.00 | 1.00 | 0.77 |
| 0003 | VM01 | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0004 | VM01 | 3 | 0.67 | 0.72 | 0.52 | 0.83 | 1.00 | 0.62 |
| 0008 | VM01 | 3 | 0.67 | 0.97 | 0.78 | 1.00 | 1.00 | 0.77 |
| 0011 | VM01 | 0 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| 0014 | VM01 | 3 | 0.67 | 0.88 | 0.85 | 1.00 | 1.00 | 0.77 |
| 0016 | VM01 | 2 | 0.82 | 1.00 | 0.83 | 1.00 | 1.00 | 0.87 |

<p style="text-align: center;">    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
