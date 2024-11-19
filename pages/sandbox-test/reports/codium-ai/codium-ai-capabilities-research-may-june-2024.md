# CodiumAI Capabilities Research May-June 2024

- [Executive Summary](#executive-summary)
- [Code Completion](#code-completion)
    - [Test Run Summary](#test-run-summary)
- [Implementation Plans](#implementation-plans)
    - [Generic standard Java web application](#generic-standard-java-web-application)
    - [Findings](#findings)
- [Test Generation](#test-generation)
    - [Generic standard Java web application tests](#generic-standard-java-web-application-tests)
    - [Common Advantages](#common-advantages)
    - [Common Issues](#common-issues)
- [PR Review](#pr-review)
    - [PR Review Testing](#pr-review-testing)
        - [Case 1](#case-1)
        - [Case 2](#case-2)
    - [PR Review Findings](#pr-review-findings)

## Executive Summary
Niche product (VS Code and JetBrains IDEs Plugin) that has many capabilities including agentic features but did not impress overall in any of areas. Benchmark score is low. Can generate not bad unit test suites - but this is on the level of major players in the field. Code reviews functionality is worse by quality than unit tests generation.

## Code Completion
[CodiumAI code completion](https://codiumate-docs.codium.ai/code-completion/) performance was evaluated by running [EPAM proprietary set of development cases](https://github.com/epam/AIRUN-Assistants-Benchmark-CodeBase) in Visual Studio Code with Codiumate plugin.

### Test Run Summary
| Date       | Code Generator | Language   | Overall | Passed Tests | Success Rate, %% |
|------------|----------------|------------|---------|--------------|------------------|
| May 2024   | Codiumate      | Java       | 36      | 17           | 47.22            |
| May 2024   | Codiumate      | C#         | 34      | 16           | 47.06            |
| May 2024   | Codiumate      | TypeScript | 7       | 5            | 71.43            |
| May 2024   | Codiumate      | In all     | 77      | 38           | 49.35            |

Detailed report:
[ReportCodiumMay2024.xlsx](../../../../reports/ReportCodiumMay2024.xlsx)

## Implementation Plans
CodiumAI provides [Coding Agent](https://codiumate-docs.codium.ai/chat/coding-agent/) as AI-powered assistant allowing to generate implementation plan for a common task description enriched by code context and assist with task implementation following the generated plan.

The capability efficiency was evaluated with a set of tasks created for a generic standard Java web application aka pet-project.

### Generic standard Java web application

The testing was performed on [golf application codebase](https://github.com/PolinaTolkachova/golf-application) following adopted [test instructions](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions/tree/main/golf-application-tests). 
A testing protocol is attached to the page as free text file: [golf.impl-plan.txt](../../../../files/sandbox-test/codium-ai/golf.impl-plan.txt)

| Date           | Tests Count | Programming Languages | IDEs    | Interface    | AI Tools            | Final Score (%) |
|----------------|-------------|-----------------------|---------|--------------|---------------------|-----------------|
| June 10th 2024 | 18          | Java                  | VS Code | Coding Agent | Codium.AI Codiumate | 61.11           |

Detailed report:
[GolfAppTestsCodiumJune2024.xlsx](../../../../reports/GolfAppTestsCodiumJune2024.xlsx)

### Findings
- Coding Agent is not able to generate proper development plan by abstract task description.
- Coding Agent works better with technical task description, but it requires to provide too many details.
- Source code context should be filled with all files related to task development. Critical code parts should be additionally added as fragments.
- Complex system consisting of multiple components with own data dictionaries and own data models requires enormous exertion to give a clear consistent description.
- Effort to provide qualified description and full source code context is too high.

## Test Generation
CodiumAI provides [Iterative Test Generation capability](https://codiumate-docs.codium.ai/tests/) as AI-powered assistant allowing to generate comprehensive test suites.

The capability efficiency was evaluated with a set of tasks on a generic standard Java web application aka pet-project.

### Generic standard Java web application tests

The testing was performed on [golf application codebase](https://github.com/PolinaTolkachova/golf-application). In general test generation was good enough. Codiumate generated complete set of test cases including happy path cases and edge cases. Test generation was accompanied by qualified description of tested code. The plugin allowed to choose test cases to generate and to set own test cases. It is possible to configure test generation either by setting properties or by providing exemplar test.

### Common Advantages
- Codiumate generates a good code explanation.
- Codiumate suggests inspiring test plan consisting of wide list of test cases. The test plan promises 100% test coverage.

### Common Issues
- Minor: Codiumate follows configuration while generating tests, but generated code needs manual correction. For instance, it generated tests for JUnit 5 as configured, but imports JUnit 4 classes.
- Many suggested test cases are created just for increasing total number of tests. Some tests can be combined in one without decreasing of code coverage.
- Codiumate can fail with generation of test for suggested test case even if a case is similar to successfully generated one. Test generation is blocked after fail. 
- Complex code logic is not followed by generated tests.
- References made-up constants, methods, classes in tests.
- Complex code tests have many issues, completeness can be evaluated as 20-30%.

## PR Review
CodiumAI provides [PR-Agent](https://pr-agent-docs.codium.ai/) as AI-powered assistant allowing efficiently review and handle pull requests.

Generic standard Java web application codebase was chosen to test the capability. The application is a REST service written on Spring Boot with Spring MVC web layer and Spring Data JDBC data access layer.

The tool performance was evaluated with two pull-request having some issues.

### PR Review Testing

#### Case 1
- **Description**: PR adds processing for new business object including controller, service, repository. The repository class is implemented with plain JDBC, although the existing repository is written as Spring Data Repository. The new repository suffer from SQL injection.

<details>
<summary>PR Changes...</summary>

#### File Changes as Patch

```diff
Date: Mon, 17 Jun 2024 19:32:40 +0300
Subject: [PATCH] add part management

---
 build.gradle                                  |   1 +
 run.txt                                       |   9 +-
 .../jz/example/restpageable/domain/Part.java  |  59 ++++++++
 .../example/restpageable/model/PartDTO.java   |  20 +++
 .../repository/PartRepository.java            | 127 ++++++++++++++++++
 .../restpageable/rest/PartResource.java       |  42 ++++++
 .../restpageable/service/PartService.java     |  57 ++++++++
 src/main/resources/data.sql                   |   1 +
 src/main/resources/schema.sql                 |   8 ++
 9 files changed, 323 insertions(+), 1 deletion(-)
 create mode 100644 src/main/java/jz/example/restpageable/domain/Part.java
 create mode 100644 src/main/java/jz/example/restpageable/model/PartDTO.java
 create mode 100644 src/main/java/jz/example/restpageable/repository/PartRepository.java
 create mode 100644 src/main/java/jz/example/restpageable/rest/PartResource.java
 create mode 100644 src/main/java/jz/example/restpageable/service/PartService.java
 create mode 100644 src/main/resources/data.sql
 create mode 100644 src/main/resources/schema.sql

diff --git a/build.gradle b/build.gradle
index 95b79e8..b836268 100644
--- a/build.gradle
+++ b/build.gradle
@@ -21,6 +21,7 @@ dependencies {
     implementation('org.springframework.boot:spring-boot-starter-web')
     implementation('org.springframework.boot:spring-boot-starter-validation')
     implementation('org.springframework.boot:spring-boot-starter-data-jpa')
+    implementation('org.springframework.boot:spring-boot-starter-jdbc')
     runtimeOnly('com.h2database:h2')
     compileOnly('org.projectlombok:lombok')
     annotationProcessor('org.projectlombok:lombok')
diff --git a/run.txt b/run.txt
index e89a505..de1ddaf 100644
--- a/run.txt
+++ b/run.txt
@@ -5,4 +5,11 @@ done
 
 curl http://localhost:8080/api/items
 
-curl http://localhost:8080/api/items/page?page=0\&key=name
\ No newline at end of file
+curl http://localhost:8080/api/items/page?page=0\&key=name
+
+#
+
+curl http://localhost:8080/api/parts/0
+
+curl -d "{\"id\":1, \"name\":\"xx1\"}" -H "Content-Type: application/json" -X POST http://localhost:8080/api/parts
+
diff --git a/src/main/java/jz/example/restpageable/domain/Part.java b/src/main/java/jz/example/restpageable/domain/Part.java
new file mode 100644
index 0000000..5e3388b
--- /dev/null
+++ b/src/main/java/jz/example/restpageable/domain/Part.java
@@ -0,0 +1,59 @@
+package jz.example.restpageable.domain;
+
+import java.util.Objects;
+
+public class Part
+{
+    private Long id;
+
+    private String name;
+
+    public Part()
+    {
+    }
+
+    public Part(Long id, String name)
+    {
+        this.id = id;
+        this.name = name;
+    }
+
+    public Long getId()
+    {
+        return id;
+    }
+
+    public void setId( Long id )
+    {
+        this.id = id;
+    }
+
+    public String getName()
+    {
+        return name;
+    }
+
+    public void setName( String name )
+    {
+        this.name = name;
+    }
+
+    @Override
+    public int hashCode()
+    {
+        return Objects.hash( id, name );
+    }
+
+    @Override
+    public boolean equals( Object obj )
+    {
+        if( this == obj )
+            return true;
+        if( obj == null )
+            return false;
+        if( getClass() != obj.getClass() )
+            return false;
+        Part other = (Part) obj;
+        return Objects.equals( id, other.id ) && Objects.equals( name, other.name );
+    }
+}
diff --git a/src/main/java/jz/example/restpageable/model/PartDTO.java b/src/main/java/jz/example/restpageable/model/PartDTO.java
new file mode 100644
index 0000000..0ab7f09
--- /dev/null
+++ b/src/main/java/jz/example/restpageable/model/PartDTO.java
@@ -0,0 +1,20 @@
+package jz.example.restpageable.model;
+
+import javax.validation.constraints.NotNull;
+import javax.validation.constraints.Size;
+
+import lombok.Getter;
+import lombok.Setter;
+
+
+@Getter
+@Setter
+public class PartDTO {
+
+    private Long id;
+
+    @NotNull
+    @Size(max = 255)
+    private String name;
+
+}
diff --git a/src/main/java/jz/example/restpageable/repository/PartRepository.java b/src/main/java/jz/example/restpageable/repository/PartRepository.java
new file mode 100644
index 0000000..e8c0ac4
--- /dev/null
+++ b/src/main/java/jz/example/restpageable/repository/PartRepository.java
@@ -0,0 +1,127 @@
+package jz.example.restpageable.repository;
+
+import java.sql.Connection;
+import java.sql.ResultSet;
+import java.sql.SQLException;
+import java.sql.Statement;
+
+import javax.sql.DataSource;
+
+import org.springframework.beans.factory.annotation.Autowired;
+import org.springframework.stereotype.Component;
+
+import jz.example.restpageable.domain.Part;
+
+@Component
+public class PartRepository
+{
+    @Autowired
+    private DataSource dataSource;
+
+    public Part findById( Long id )
+    {
+        Connection connection = null;
+        Statement statement = null;
+        ResultSet rs = null;
+        try
+        {
+            connection = dataSource.getConnection();
+
+            String sql = "SELECT * FROM part WHERE id = " + id;
+            statement = connection.createStatement();
+            rs = statement.executeQuery( sql );
+
+            if( rs.next() )
+            {
+                Part part = new Part( rs.getLong( 1 ), rs.getString( 2 ) );
+                return part;
+            }
+        }
+        catch( SQLException e )
+        {
+            e.printStackTrace();
+        }
+        finally
+        {
+            if( rs != null )
+            {
+                try
+                {
+                    rs.close();
+                }
+                catch( SQLException e )
+                {
+                    e.printStackTrace();
+                }
+            }
+            if( statement != null )
+            {
+                try
+                {
+                    statement.close();
+                }
+                catch( SQLException e )
+                {
+                    e.printStackTrace();
+                }
+            }
+            if( connection != null )
+            {
+                try
+                {
+                    connection.close();
+                }
+                catch( SQLException e )
+                {
+                    e.printStackTrace();
+                }
+            }
+        }
+        return null;
+    }
+
+    public Part save( Part part )
+    {
+        Connection connection = null;
+        Statement statement = null;
+        int count = 0;
+        try
+        {
+            connection = dataSource.getConnection();
+
+            String sql = "INSERT INTO part (id, name) VALUES (" + part.getId() + ", '" + part.getName() + "')";
+            statement = connection.createStatement();
+            count = statement.executeUpdate( sql );
+        }
+        catch( SQLException e )
+        {
+            e.printStackTrace();
+        }
+        finally
+        {
+            if( statement != null )
+            {
+                try
+                {
+                    statement.close();
+                }
+                catch( SQLException e )
+                {
+                    e.printStackTrace();
+                }
+            }
+            if( connection != null )
+            {
+                try
+                {
+                    connection.close();
+                }
+                catch( SQLException e )
+                {
+                    e.printStackTrace();
+                }
+            }
+        }
+        return count == 0 ? null : findById( part.getId() );
+    }
+}
diff --git a/src/main/java/jz/example/restpageable/rest/PartResource.java b/src/main/java/jz/example/restpageable/rest/PartResource.java
new file mode 100644
index 0000000..dae25dd
--- /dev/null
+++ b/src/main/java/jz/example/restpageable/rest/PartResource.java
@@ -0,0 +1,42 @@
+package jz.example.restpageable.rest;
+
+import javax.validation.Valid;
+
+import org.springframework.http.HttpStatus;
+import org.springframework.http.MediaType;
+import org.springframework.http.ResponseEntity;
+import org.springframework.web.bind.annotation.GetMapping;
+import org.springframework.web.bind.annotation.PathVariable;
+import org.springframework.web.bind.annotation.PostMapping;
+import org.springframework.web.bind.annotation.RequestBody;
+import org.springframework.web.bind.annotation.RequestMapping;
+import org.springframework.web.bind.annotation.RestController;
+
+import jz.example.restpageable.model.PartDTO;
+import jz.example.restpageable.service.PartService;
+import lombok.extern.slf4j.Slf4j;
+
+@Slf4j
+@RestController()
+@RequestMapping(value = "/api/parts", produces = MediaType.APPLICATION_JSON_VALUE)
+public class PartResource
+{
+    private final PartService partService;
+
+    public PartResource(PartService partService)
+    {
+        this.partService = partService;
+    }
+
+    @GetMapping("/{id}")
+    public ResponseEntity<PartDTO> getPart( @PathVariable final Long id )
+    {
+        return ResponseEntity.ok( partService.get( id ) );
+    }
+
+    @PostMapping
+    public ResponseEntity<Long> createPart( @RequestBody @Valid final PartDTO partDTO )
+    {
+        return new ResponseEntity<>( partService.create( partDTO ), HttpStatus.CREATED );
+    }
+}
diff --git a/src/main/java/jz/example/restpageable/service/PartService.java b/src/main/java/jz/example/restpageable/service/PartService.java
new file mode 100644
index 0000000..90e8364
--- /dev/null
+++ b/src/main/java/jz/example/restpageable/service/PartService.java
@@ -0,0 +1,57 @@
+package jz.example.restpageable.service;
+
+import javax.validation.Valid;
+
+import org.springframework.http.HttpStatus;
+import org.springframework.stereotype.Service;
+import org.springframework.transaction.annotation.Transactional;
+import org.springframework.web.server.ResponseStatusException;
+
+import jz.example.restpageable.domain.Part;
+import jz.example.restpageable.model.PartDTO;
+import jz.example.restpageable.repository.PartRepository;
+
+@Transactional
+@Service
+public class PartService
+{
+    private final PartRepository partRepository;
+
+    public PartService(PartRepository partRepository)
+    {
+        this.partRepository = partRepository;
+    }
+
+    public PartDTO get( final Long id )
+    {
+        Part part = partRepository.findById( id );
+        if( part != null )
+        {
+            PartDTO partDTO = mapToDTO( part );
+            return partDTO;
+        }
+        throw new ResponseStatusException( HttpStatus.NOT_FOUND );
+    }
+
+    public Long create( @Valid PartDTO partDTO )
+    {
+        Part part = mapToEntity( partDTO );
+        return partRepository.save( part ).getId();
+    }
+
+    private PartDTO mapToDTO( final Part part )
+    {
+        PartDTO partDTO = new PartDTO();
+        partDTO.setId( part.getId() );
+        partDTO.setName( part.getName() );
+        return partDTO;
+    }
+
+    private Part mapToEntity( final PartDTO partDTO )
+    {
+        Part part = new Part();
+        part.setId( partDTO.getId() );
+        part.setName( partDTO.getName() );
+        return part;
+    }
+}
diff --git a/src/main/resources/data.sql b/src/main/resources/data.sql
new file mode 100644
index 0000000..f9f168e
--- /dev/null
+++ b/src/main/resources/data.sql
@@ -0,0 +1 @@
+INSERT INTO part (id, name) VALUES (0, 'ww0');
\ No newline at end of file
diff --git a/src/main/resources/schema.sql b/src/main/resources/schema.sql
new file mode 100644
index 0000000..c9e1812
--- /dev/null
+++ b/src/main/resources/schema.sql
@@ -0,0 +1,8 @@
+DROP TABLE IF EXISTS part;
+
+
+CREATE TABLE part
+(  
+    id INT PRIMARY KEY,  
+    name VARCHAR(255) NOT NULL
+);
\ No newline at end of file
-- 
2.45.1
```

</details>

<details>
<summary>PR-Agent Review...</summary>

## PR Reviewer Guide 🔍

| **Category**                       | **Details**                                                                                                                                                                                                 |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ⏱️ **Estimated effort to review [1-5]** | 4                                                                                                                                                                                                          |
| 🧪 **Relevant tests**              | No                                                                                                                                                                                                         |
| 🔒 **Security concerns**           | **- SQL Injection:**<br />As mentioned, the current implementation of SQL queries in `PartRepository` is susceptible to SQL injection attacks. This needs to be addressed by using prepared statements or other secure methods of constructing SQL queries. |
| ⚡ **Key issues to review**        | **SQL Injection Risk:**<br />The `PartRepository` class methods `findById` and `save` use string concatenation to build SQL queries, which can lead to SQL injection vulnerabilities. Consider using prepared statements or another form of query parameterization to mitigate this risk.<br /><br />**Error Handling:**<br />The `PartRepository` class methods catch `SQLException` and print the stack trace, but do not rethrow or handle the exception in a way that would inform the calling service of the issue. This could lead to failures that are hard to debug or inconsistent application state.<br /><br />**Resource Management:**<br />The `PartRepository` class manually manages database resources such as connections, statements, and result sets. Consider using a try-with-resources statement to ensure these resources are closed properly, reducing the risk of resource leaks. |

## PR Code Suggestions ✨

| Category        | Suggestion                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Score |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| **Security**     | Use prepared statements to prevent SQL injection<br>**Replace the string concatenation in SQL queries with prepared statements to prevent SQL**<br>**injection vulnerabilities.**<br>[src/main/java/jz/example/restpageable/repository/PartRepository.java [30-32]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/1/files*diff-f87fe0936b8b2d2c652110f0300a3ded76e097119094421bb27477e32c70ad88R30-R32__;Iw!!GF_29dbcQIUBPA!3AOwc90Crpknk5CWheWoLw-67hi-w0kn3cdgVEV6XWDSA0JIeI4pS6lDJ3JFdEe3wug-76tEcuDBIF2HJkjXQs582SeYaRw$)<br>-String sql = "SELECT * FROM part WHERE id = " + id;<br>-statement = connection.createStatement();<br>-rs = statement.executeQuery( sql );<br>+String sql = "SELECT * FROM part WHERE id = ?";<br>+statement = connection.prepareStatement(sql);<br>+statement.setLong(1, id);<br>+rs = statement.executeQuery();<br>**Suggestion importance[1-10]: 10**<br>Why: This suggestion addresses a critical security vulnerability by replacing string concatenation in SQL queries with prepared statements, which helps prevent SQL injection attacks. | 10    |
| **Best practice** | Use try-with-resources for better resource management<br>**Use try-with-resources to ensure that resources like Connection, Statement, and ResultSet**<br>**are closed properly, which simplifies the code and improves reliability.**<br>[src/main/java/jz/example/restpageable/repository/PartRepository.java [23-78]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/1/files*diff-f87fe0936b8b2d2c652110f0300a3ded76e097119094421bb27477e32c70ad88R23-R78__;Iw!!GF_29dbcQIUBPA!3AOwc90Crpknk5CWheWoLw-67hi-w0kn3cdgVEV6XWDSA0JIeI4pS6lDJ3JFdEe3wug-76tEcuDBIF2HJkjXQs58-GP-Bfo$)<br>-Connection connection = null;<br>-Statement statement = null;<br>-ResultSet rs = null;<br>-try<br>+try (Connection connection = dataSource.getConnection();<br>+     Statement statement = connection.createStatement();<br>+     ResultSet rs = statement.executeQuery(sql)) {<br>-    connection = dataSource.getConnection(); ... }<br>-finally<br>-{<br>-    if( rs != null )<br>-        rs.close();<br>-    if( statement != null )<br>-        statement.close();<br>-    if( connection != null )<br>-        connection.close();<br>-}<br>**Suggestion importance[1-10]: 9**<br>Why: Using try-with-resources ensures that resources are closed automatically, simplifying the code and improving reliability by preventing resource leaks. | 9     |
|                  | Replace printStackTrace with logging<br>**Avoid using printStackTrace() for exception handling; instead, use a logger to log**<br>**exceptions.**<br>[src/main/java/jz/example/restpageable/repository/PartRepository.java [40-43]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/1/files*diff-f87fe0936b8b2d2c652110f0300a3ded76e097119094421bb27477e32c70ad88R40-R43__;Iw!!GF_29dbcQIUBPA!3AOwc90Crpknk5CWheWoLw-67hi-w0kn3cdgVEV6XWDSA0JIeI4pS6lDJ3JFdEe3wug-76tEcuDBIF2HJkjXQs58I1_1NhU$)<br>catch( SQLException e ) {<br>-    e.printStackTrace();<br>+    logger.error("SQL Exception occurred", e); }<br>**Suggestion importance[1-10]: 8**<br>Why: Replacing printStackTrace with proper logging improves the maintainability and readability of the code, and provides better control over logging levels and outputs. | 8     |
| **Enhancement**  | Add toString method for better object representation<br>**Implement toString method in the Part class to improve debugging and logging capabilities.**<br>[src/main/java/jz/example/restpageable/domain/Part.java [41-45]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/1/files*diff-1900d0bfd75a9ebd7f9dc933f706f12aa417120a4b0e29a633913b246d2a18eeR41-R45__;Iw!!GF_29dbcQIUBPA!3AOwc90Crpknk5CWheWoLw-67hi-w0kn3cdgVEV6XWDSA0JIeI4pS6lDJ3JFdEe3wug-76tEcuDBIF2HJkjXQs58J5zWkgM$)<br>@Override<br>-public int hashCode()<br>+public String toString() {<br>-    return Objects.hash( id, name );<br>+    return "Part{" <br>+           "id=" + id +<br>+           ", name='" + name + '\'' <br>+           '}'; }<br>**Suggestion importance[1-10]: 7**<br>Why: Adding a toString method enhances debugging and logging capabilities by providing a clear and formatted string representation of the Part object. | 7     |


</details>

- **Review Missed Points**:
    - No tests added
    - PR uses plain JDBC instead of Spring Data repository
    - Direct DB schema definition and data initialization instead of higher-level migration tools like Flyway or Liquibase.

#### Case 2
- **Description**: PR secures REST service with basic authentication and authorization. PR used in memory user database with plan text user passwords. PR mixes the task implementation with Spring Boot version upgrade.

<details>
<summary>PR Changes...</summary>

```diff
Date: Tue, 18 Jun 2024 12:16:41 +0300
Subject: [PATCH] securing service

---
 build.gradle                                  |  5 ++-
 run.txt                                       |  4 +-
 .../restpageable/config/SecurityConfig.java   | 44 +++++++++++++++++++
 .../jz/example/restpageable/domain/Item.java  | 13 +++---
 .../example/restpageable/model/ItemDTO.java   |  5 +--
 .../repository/ItemRepository.java            |  3 +-
 .../restpageable/rest/ItemResource.java       | 10 ++++-
 .../rest/RestExceptionHandler.java            |  4 +-
 src/main/resources/application.properties     |  9 +---
 9 files changed, 70 insertions(+), 27 deletions(-)
 create mode 100644 src/main/java/jz/example/restpageable/config/SecurityConfig.java

diff --git a/build.gradle b/build.gradle
index 95b79e8..99b06c2 100644
--- a/build.gradle
+++ b/build.gradle
@@ -1,6 +1,6 @@
 plugins {
-    id 'org.springframework.boot' version '2.7.5'
-    id 'io.spring.dependency-management' version '1.1.0'
+    id 'org.springframework.boot' version '3.3.0'
+    id 'io.spring.dependency-management' version '1.1.5'
     id 'java'
     id 'eclipse'
 }
@@ -21,6 +21,7 @@ dependencies {
     implementation('org.springframework.boot:spring-boot-starter-web')
     implementation('org.springframework.boot:spring-boot-starter-validation')
     implementation('org.springframework.boot:spring-boot-starter-data-jpa')
+    implementation('org.springframework.boot:spring-boot-starter-security')
     runtimeOnly('com.h2database:h2')
     compileOnly('org.projectlombok:lombok')
     annotationProcessor('org.projectlombok:lombok')
diff --git a/run.txt b/run.txt
index e89a505..3b98c29 100644
--- a/run.txt
+++ b/run.txt
@@ -1,8 +1,8 @@
 for i in {0..10}
 do
-    curl -d "{\"name\":\"name$i\"}" -H "Content-Type: application/json" -X POST http://localhost:8080/api/items
+    curl -u user2:pass2 -d "{\"name\":\"name$i\"}" -H "Content-Type: application/json" -X POST http://localhost:8080/api/items
 done
 
-curl http://localhost:8080/api/items
+curl -u user1:pass1 http://localhost:8080/api/items
 
 curl http://localhost:8080/api/items/page?page=0\&key=name
\ No newline at end of file
diff --git a/src/main/java/jz/example/restpageable/config/SecurityConfig.java b/src/main/java/jz/example/restpageable/config/SecurityConfig.java
new file mode 100644
index 0000000..b04e1d3
--- /dev/null
+++ b/src/main/java/jz/example/restpageable/config/SecurityConfig.java
@@ -0,0 +1,44 @@
+package jz.example.restpageable.config;
+
+import static org.springframework.security.config.Customizer.withDefaults;
+
+import org.springframework.context.annotation.Bean;
+import org.springframework.context.annotation.Configuration;
+import org.springframework.security.config.annotation.method.configuration.EnableMethodSecurity;
+import org.springframework.security.config.annotation.web.builders.HttpSecurity;
+import org.springframework.security.config.annotation.web.configuration.EnableWebSecurity;
+import org.springframework.security.config.http.SessionCreationPolicy;
+import org.springframework.security.core.userdetails.User;
+import org.springframework.security.core.userdetails.User.UserBuilder;
+import org.springframework.security.core.userdetails.UserDetails;
+import org.springframework.security.core.userdetails.UserDetailsService;
+import org.springframework.security.provisioning.InMemoryUserDetailsManager;
+import org.springframework.security.web.SecurityFilterChain;
+
+@Configuration
+@EnableWebSecurity
+@EnableMethodSecurity(securedEnabled = true)
+public class SecurityConfig
+{
+    @Bean
+    UserDetailsService users()
+    {
+        UserBuilder users = User.withDefaultPasswordEncoder();
+        UserDetails user1 = users.username( "user1" ).password( "pass1" ).roles( "VIEWER" ).build();
+        UserDetails user2 = users.username( "user2" ).password( "pass2" ).roles( "EDITOR" ).build();
+        UserDetails admin = users.username( "admin" ).password( "passA" ).roles( "EDITOR", "ADMIN" ).build();
+        return new InMemoryUserDetailsManager( user1, user2, admin );
+    }
+
+    @Bean
+    SecurityFilterChain filterChain( HttpSecurity http ) throws Exception
+    {
+        http.csrf( ( csrf ) -> csrf.disable() )
+                .sessionManagement( ( session ) -> session.sessionCreationPolicy( SessionCreationPolicy.STATELESS ) )
+                .authorizeHttpRequests(
+                        ( authorize ) -> authorize.anyRequest().authenticated() )
+                .httpBasic( withDefaults() );
+        return http.build();
+    }
+
+}
diff --git a/src/main/java/jz/example/restpageable/domain/Item.java b/src/main/java/jz/example/restpageable/domain/Item.java
index ce589d7..4c5ea7d 100644
--- a/src/main/java/jz/example/restpageable/domain/Item.java
+++ b/src/main/java/jz/example/restpageable/domain/Item.java
@@ -2,15 +2,14 @@ package jz.example.restpageable.domain;
 
 import java.util.Objects;
 
-import javax.persistence.Column;
-import javax.persistence.Entity;
-import javax.persistence.GeneratedValue;
-import javax.persistence.GenerationType;
-import javax.persistence.Id;
-import javax.persistence.Table;
-
 import org.hibernate.annotations.NaturalId;
 
+import jakarta.persistence.Column;
+import jakarta.persistence.Entity;
+import jakarta.persistence.GeneratedValue;
+import jakarta.persistence.GenerationType;
+import jakarta.persistence.Id;
+import jakarta.persistence.Table;
 import lombok.Getter;
 import lombok.Setter;
 
diff --git a/src/main/java/jz/example/restpageable/model/ItemDTO.java b/src/main/java/jz/example/restpageable/model/ItemDTO.java
index add1a05..3b7518f 100644
--- a/src/main/java/jz/example/restpageable/model/ItemDTO.java
+++ b/src/main/java/jz/example/restpageable/model/ItemDTO.java
@@ -1,8 +1,7 @@
 package jz.example.restpageable.model;
 
-import javax.validation.constraints.NotNull;
-import javax.validation.constraints.Size;
-
+import jakarta.validation.constraints.NotNull;
+import jakarta.validation.constraints.Size;
 import lombok.Getter;
 import lombok.Setter;
 
diff --git a/src/main/java/jz/example/restpageable/repository/ItemRepository.java b/src/main/java/jz/example/restpageable/repository/ItemRepository.java
index f4c9e03..9d2693b 100644
--- a/src/main/java/jz/example/restpageable/repository/ItemRepository.java
+++ b/src/main/java/jz/example/restpageable/repository/ItemRepository.java
@@ -1,10 +1,11 @@
 package jz.example.restpageable.repository;
 
+import org.springframework.data.repository.CrudRepository;
 import org.springframework.data.repository.PagingAndSortingRepository;
 
 import jz.example.restpageable.domain.Item;
 
-public interface ItemRepository extends PagingAndSortingRepository<Item, Long>
+public interface ItemRepository extends PagingAndSortingRepository<Item, Long>, CrudRepository<Item, Long>
 {
 
 }
diff --git a/src/main/java/jz/example/restpageable/rest/ItemResource.java b/src/main/java/jz/example/restpageable/rest/ItemResource.java
index 96d1366..d64ed12 100644
--- a/src/main/java/jz/example/restpageable/rest/ItemResource.java
+++ b/src/main/java/jz/example/restpageable/rest/ItemResource.java
@@ -2,13 +2,12 @@ package jz.example.restpageable.rest;
 
 import java.util.List;
 
-import javax.validation.Valid;
-
 import org.springframework.beans.factory.annotation.Autowired;
 import org.springframework.data.domain.Page;
 import org.springframework.http.HttpStatus;
 import org.springframework.http.MediaType;
 import org.springframework.http.ResponseEntity;
+import org.springframework.security.access.annotation.Secured;
 import org.springframework.web.bind.annotation.DeleteMapping;
 import org.springframework.web.bind.annotation.GetMapping;
 import org.springframework.web.bind.annotation.PathVariable;
@@ -18,6 +17,7 @@ import org.springframework.web.bind.annotation.RequestBody;
 import org.springframework.web.bind.annotation.RequestMapping;
 import org.springframework.web.bind.annotation.RestController;
 
+import jakarta.validation.Valid;
 import jz.example.restpageable.domain.Item;
 import jz.example.restpageable.mapper.PageToPageDTOMapper;
 import jz.example.restpageable.model.ItemDTO;
@@ -43,6 +43,7 @@ public class ItemResource
     }
 
     @GetMapping("/page")
+    @Secured({ "ROLE_VIEWER" })
     public PageDTO<Item> getItemPage( PageSettings pageSettings )
     {
         log.info( "Request for page received with data : " + pageSettings );
@@ -53,24 +54,28 @@ public class ItemResource
     }
 
     @GetMapping
+    @Secured({ "ROLE_VIEWER"})
     public ResponseEntity<List<ItemDTO>> getAllItems()
     {
         return ResponseEntity.ok( itemService.findAll() );
     }
 
     @GetMapping("/{id}")
+    @Secured({ "ROLE_VIEWER" })
     public ResponseEntity<ItemDTO> getItem( @PathVariable final Long id )
     {
         return ResponseEntity.ok( itemService.get( id ) );
     }
 
     @PostMapping
+    @Secured({ "ROLE_EDITOR" })
     public ResponseEntity<Long> createItem( @RequestBody @Valid final ItemDTO itemDTO )
     {
         return new ResponseEntity<>( itemService.create( itemDTO ), HttpStatus.CREATED );
     }
 
     @PutMapping("/{id}")
+    @Secured({ "ROLE_EDITOR" })
     public ResponseEntity<Void> updateItem( @PathVariable final Long id, @RequestBody @Valid final ItemDTO itemDTO )
     {
         itemService.update( id, itemDTO );
@@ -78,6 +83,7 @@ public class ItemResource
     }
 
     @DeleteMapping("/{id}")
+    @Secured({ "ROLE_EDITOR" })
     public ResponseEntity<Void> deleteItem( @PathVariable final Long id )
     {
         itemService.delete( id );
diff --git a/src/main/java/jz/example/restpageable/rest/RestExceptionHandler.java b/src/main/java/jz/example/restpageable/rest/RestExceptionHandler.java
index 0d5ac47..70772b9 100644
--- a/src/main/java/jz/example/restpageable/rest/RestExceptionHandler.java
+++ b/src/main/java/jz/example/restpageable/rest/RestExceptionHandler.java
@@ -23,10 +23,10 @@ public class RestExceptionHandler
     public ResponseEntity<ErrorResponse> handleNotFound( final ResponseStatusException exception )
     {
         final ErrorResponse errorResponse = new ErrorResponse();
-        errorResponse.setHttpStatus( exception.getStatus().value() );
+        errorResponse.setHttpStatus( exception.getStatusCode().value() );
         errorResponse.setException( exception.getClass().getSimpleName() );
         errorResponse.setMessage( exception.getMessage() );
-        return new ResponseEntity<>( errorResponse, exception.getStatus() );
+        return new ResponseEntity<>( errorResponse, exception.getStatusCode() );
     }
 
     @ExceptionHandler(MethodArgumentNotValidException.class)
diff --git a/src/main/resources/application.properties b/src/main/resources/application.properties
index 81722da..4fbece0 100644
--- a/src/main/resources/application.properties
+++ b/src/main/resources/application.properties
@@ -1,8 +1 @@
-server:
-  port: 9000
-
-spring:
-  datasource:
-    url: jdbc:h2:mem:mydb
-    username: user
-    password: password
+logging.level.org.springframework.security=TRACE
-- 
2.45.1
```

</details>


<details>
<summary>PR-Agent Review...</summary>

## PR Reviewer Guide 🔍

| **Category**                           | **Details**                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ⏱️ **Estimated effort to review [1-5]** | 4                                                                                                                                                                                                                                                                                                                                           |
| 🧪 **Relevant tests**                  | No                                                                                                                                                                                                                                                                                                                                          |
| 🔒 **Security concerns**               | **- Hardcoded Credentials:**<br />The use of hardcoded credentials in `SecurityConfig.java` poses a risk of credential leakage.<br />**- Weak Password Encoding:**<br />The use of `User.withDefaultPasswordEncoder()` in `SecurityConfig.java` could allow attackers to more easily compromise user passwords. Consider using a stronger password encoding mechanism. |
| ⚡ **Key issues to review**            | **Insecure Password Handling:**<br />The method `User.withDefaultPasswordEncoder()` is used, which is not recommended for production as it uses a weak password encoding. Consider using a stronger password encoder.<br /><br />**Hardcoded Credentials:**<br />User credentials are hardcoded in the `SecurityConfig.java`, which could lead to security risks if the code is exposed. Consider externalizing credentials or using a more secure method of managing them.<br /><br />**Migration Impact:**<br />Ensure that the migration from `javax.persistence` and `javax.validation` to `jakarta.persistence` and `jakarta.validation` does not affect existing functionalities or integrations.<br /><br />**Role Configuration:**<br />Verify that the roles assigned (VIEWER, EDITOR, ADMIN) are correctly implemented across the application to prevent unauthorized access. |

## PR Code Suggestions ✨

| Category        | Suggestion                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Score |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| **Security**     | Improve password security by using a stronger password encoder<br>**Replace the usage of** `withDefaultPasswordEncoder()` **with a stronger password encoder like** `BCryptPasswordEncoder`. **Using** `withDefaultPasswordEncoder()` **is not recommended for production as it is insecure.**<br>[src/main/java/jz/example/restpageable/config/SecurityConfig.java [26]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/2/files*diff-b4568555eb90be02c03ee3378059947a9eefd3381ea38fc2e8e9c2b7f7a182b4R26-R26__;Iw!!GF_29dbcQIUBPA!218RbDeTYMmtc_ImqhZkoNC3cysFo-vQsqhabQ2KeBdhE6L-c67xXkueLMdD7UP627BNIKSI2u_SXerD1AFaPLksDcSu8hE$)<br>-UserBuilder users = User.withDefaultPasswordEncoder();<br>+UserBuilder users = User.builder().passwordEncoder(password -> new BCryptPasswordEncoder().encode(password));<br>**Suggestion importance[1-10]: 10**<br>Why: This suggestion addresses a significant security concern by recommending the use of a stronger password encoder, which is crucial for protecting user credentials in a production environment. | 10    |
|                  | Enable CSRF protection to prevent cross-site request forgery attacks<br>**Consider enabling CSRF protection unless there's a specific reason to disable it, as** disabling CSRF **can make the application vulnerable to cross-site request forgery attacks.**<br>[src/main/java/jz/example/restpageable/config/SecurityConfig.java [36]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/2/files*diff-b4568555eb90be02c03ee3378059947a9eefd3381ea38fc2e8e9c2b7f7a182b4R36-R36__;Iw!!GF_29dbcQIUBPA!218RbDeTYMmtc_ImqhZkoNC3cysFo-vQsqhabQ2KeBdhE6L-c67xXkueLMdD7UP627BNIKSI2u_SXerD1AFaPLksnHZlj1U$)<br>-http.csrf((csrf) -> csrf.disable())<br>+http.csrf((csrf) -> csrf.enable())<br>**Suggestion importance[1-10]: 9**<br>Why: Enabling CSRF protection is important for preventing cross-site request forgery attacks, which can be a serious security vulnerability. This suggestion improves the security posture of the application. | 9     |
| **Maintainability** | Ensure consistency in exception handling by using the same method to retrieve status codes<br>**Update the method to use** `exception.getStatus()` **instead of** `exception.getStatusCode()` **for consistency with other exception handling in the project.**<br>[src/main/java/jz/example/restpageable/rest/RestExceptionHandler.java [26-29]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/2/files*diff-d0023a33c8a6b1e65763203e910a4cac4956eeb47fb047bf01e2874d70cf7935R26-R29__;Iw!!GF_29dbcQIUBPA!218RbDeTYMmtc_ImqhZkoNC3cysFo-vQsqhabQ2KeBdhE6L-c67xXkueLMdD7UP627BNIKSI2u_SXerD1AFaPLkstdqyz6w$)<br>-errorResponse.setHttpStatus(exception.getStatusCode().value());<br>-return new ResponseEntity<>(errorResponse, exception.getStatusCode());<br>+errorResponse.setHttpStatus(exception.getStatus().value());<br>+return new ResponseEntity<>(errorResponse, exception.getStatus());<br>**Suggestion importance[1-10]: 8**<br>Why: Ensuring consistency in exception handling methods improves code maintainability and reduces potential confusion or errors in the future. | 8     |
| **Enhancement**  | Use more appropriate HTTP status codes for specific actions<br>**Use more specific HTTP status codes for different actions. For example, use** `HttpStatus.NO_CONTENT` **for successful delete operations which do not return content.**<br>[src/main/java/jz/example/restpageable/rest/ItemResource.java [82]](https://urldefense.com/v3/__https:/github.com/siarhei-z1-0001/restpageable/pull/2/files*diff-8dad858a5d5ca73996a363a9d02df8875342258c6aa9e9757b5d09b5284c8617R82-R82__;Iw!!GF_29dbcQIUBPA!218RbDeTYMmtc_ImqhZkoNC3cysFo-vQsqhabQ2KeBdhE6L-c67xXkueLMdD7UP627BNIKSI2u_SXerD1AFaPLkstjUFaLQ$)<br>-return ResponseEntity.ok().build();<br>+return ResponseEntity.noContent().build();<br>**Suggestion importance[1-10]: 7**<br>Why: Using more specific HTTP status codes improves the clarity and correctness of API responses, which is beneficial for client applications and overall API design. | 7     |


</details>

- **Review Missed Points**:
    - No tests added
    - Migration to Spring Boot 3 mixed with feature development in one PR
    - An user with EDITOR role isn't provided with access to read only requests
    - Hardcoded password in text file
    - Trace logging is enabled in application properties

### PR Review Findings
- PR-Agent can be a useful addition to a team toolset. It can reduce senior team staff effort by automation of pre-review of PR to discover low-level common issues in code changes. However the benefit is controversial. It does the same things static analysis tools do.
- PR-Agent don't reveal high-level issues in code changes.
- PR-Agent can slow team development by reducing team collaboration, junior member mentoring, sharing expertise and good practices since the important part of team building is farmed out.

---
<p style="text-align: center;">    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>