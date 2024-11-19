# Gemini, Copilot and Amazon Q Golf App tests - April 2024

- [Test Execution Results](#test-execution-results)
- [Summary](#summary)
- [Reports](#reports)
- [General Comments](#general-comments)
    - [Amazon Q Developer](#amazon-q-developer)
    - [Copilot](#copilot)

## Test Execution Results:

| #  | Category                        | Test Name                   | Language | AI Tool            | Result | Comments                                              |
|----|---------------------------------|-----------------------------|----------|--------------------|--------|-------------------------------------------------------|
| 1  | code-refactoring                | long-method                 | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | model-mapper-library        | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | constant-alphabetical-order | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Failed | Didn't understand the task                            |
|    |                                 | dto-encapsulation           | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | library-version-update      | Java     | Gemini             | Failed | Wrong result for all library versions                 |
|    |                                 |                             |          | Copilot            | Failed | The code was not offered due to an error              |
|    |                                 |                             |          | Amazon Q Developer | Failed | Correct result for 1 library                          |
| 2  | test-creation                   | unit-test                   | Java     | Gemini             | Passed | Generated 5 tests for different cases. 1 test failed  |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Failed | Generated unit tests failed                           |
|    |                                 | integration-test            | Java     | Gemini             | Failed | 1 test passed from 2 generated integration tests      |
|    |                                 |                             |          | Copilot            | Failed | 1 test passed from 2 generated integration tests      |
|    |                                 |                             |          | Amazon Q Developer | Failed | The code could not be compiled                        |
| 3  | solution-or-component-generation| repository-service-generation| Java   | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | exception-handling          | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed | After removing an extra parameter, the test passed    |
|    |                                 | server-side-data-validation-concrete | Java | Gemini | Failed | Incorrect suggestion (not a complete answer)          |
|    |                                 |                             |          | Copilot            | Passed | Returned to error/error page instead of error         |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | server-side-data-validation-abstract | Java | Gemini | Failed | Incorrect suggestion (not a complete answer)          |
|    |                                 |                             |          | Copilot            | Passed | Returned to error/error page instead of error         |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | logging                     | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | security-config             | Java     | Gemini             | Passed | After replacing antMatchers() with requestMatchers()  |
| 4  | code-bugfixing                  | validation-error            | Java     | Gemini             | Failed | The code was not compiled                             |
|    |                                 |                             |          | Copilot            | Passed | Error resolved with a suggested change                |
|    |                                 |                             |          | Amazon Q Developer | Passed | Bug fixed but not optimized                           |
|    |                                 | controller-error            | Java     | Gemini             | Failed | Suggested the incorrect solution                      |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Failed | Suggested the incorrect solution                      |
| 5  | solution-migration              | maven-to-gradle-migration   | Java     | Gemini             | Failed | Versions were not specified for all libraries         |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
| 6  | solution-documentation          | update-properties-for-readme-file | Java | Gemini       | Failed | Properties not grouped using the markdown format      |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Passed |                                                       |
|    |                                 | javadoc-generation          | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Passed |                                                       |
|    |                                 |                             |          | Amazon Q Developer | Failed | Generated a short version of the class with Javadoc   |
| 7  | code-explanation                | complex-method-explanation  | Java     | Gemini             | Passed |                                                       |
|    |                                 |                             |          | Copilot            | Failed | Comments not added to all logical blocks              |
|    |                                 |                             |          | Amazon Q Developer | Failed | Generated a short version of the method with comments |
|    |                                 | point-to-html-page          | Java     | Gemini             | Failed | Did not point to the HTML file                       |
|    |                                 |                             |          | Copilot            | Failed | Did not point to the HTML file                       |
|    |                                 |                             |          | Amazon Q Developer | Failed | Did not point to the HTML file                       |

## Summary:

| AI tool           | Pass Rate, % | Java Tests | Overall | Failed Tests |
|-------------------|--------------|------------|---------|--------------|
| Gemini            | 55           | 20         | 20      | 9            |
| Copilot           | 80           | 20         | 20      | 4            |
| Amazon Q Developer| 60           | 20         | 20      | 8            |

## Reports:

- [ReportGeminiApril2024.xlsx](../../../reports/ReportGeminiApril2024.xlsx)
- [ReportCopilotApril2024.xlsx](../../../reports/ReportCopilotApril2024.xlsx)
- [ReportCodeWhisperApril2024.xlsx](../../../reports/ReportCodeWhisperApril2024.xlsx)

## General Comments:

### Amazon Q Developer:
- The code for some tests must be copied into the chat window because Amazon Q Developer doesn't see the opened file.

### Copilot:
- Issue with the "Sorry, the response matched public code so it was blocked. Please rephrase your prompt" error.

---
<p style="text-align: center;">    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>    This report is licensed under CC BY-SA 4.0<br/></p>
