# OpenAI o1-mini (2024-11-06)

## Introduction

This article presents an analysis of various code-related tasks performed by the OpenAI o1-mini language model. We'll examine the model's performance across different categories of code manipulation, including translation, generation, and
documentation.

## Evaluation Summary

| Experiment         | Category                        | Language | Dataset           | Complexity | Size  | Input | Reasons | Output | Total Output | Time   | Accuracy | Completeness |
|--------------------|---------------------------------|----------|-------------------|------------|-------|-------|---------|--------|--------------|--------|----------|--------------|
| code_translation   | ReactToAngular                  | React    | ToDoApp_ReactJS   | high       | avg   | 3368  | 5248    | 3266   | 8514         | 100.40 | 4        | 4            |
| code_translation   | jQueryToReact                   | jQuery   | ToDoApp_jQuery    | high       | low   | 2350  | 512     | 2992   | 3504         | 19.38  | 4        | 4            |
| code_translation   | AngularToReact                  | Angular  | AngularCosmoPage  | avg        | high  | 5498  | 768     | 4790   | 5558         | 60.27  | 4        | 4            |
| code_translation   | UpdateReact                     | React    | ToDoApp_ReactJS   | high       | avg   | 3358  | 4224    | 3485   | 7709         | 43.44  | 4        | 4            |
| code_translation   | UpdateAngular                   | Angular  | ToDoApp_AngularJS | avg        | avg_2 | 2401  | 832     | 4844   | 5676         | 30.82  | 4        | 4            |
| code_translation   | ReactToAngular                  | React    | ReactSignUp       | high       | low   | 1306  | 2176    | 2136   | 4312         | 22.94  | 2        | 4            |
| code_translation   | VanillaToReact                  | NativeJS | Piano_NativeJS    | high       | low   | 1423  | 4608    | 2135   | 6743         | 34.30  | 4        | 2.85         |
| code_generation    | ModifyReactApp                  | React    | ReactFetchAPI     | avg        | low   | 363   | 1984    | 361    | 2345         | 12.96  | 4        | 4            |
| code_generation    | GenerateBaseComponent           | none     | none              | none       | none  | 168   | 640     | 1275   | 1915         | 10.43  | 4        | 4            |
| code_generation    | GenerateReactApp                | none     | none              | none       | none  | 158   | 448     | 407    | 855          | 4.77   | 3.92     | 4            |
| code_generation    | WriteTestsForLegacyCode         | React    | ReactSignUp       | high       | low   | 1259  | 3200    | 2091   | 5291         | 25.72  | 2.95     | 3.95         |
| code_generation    | WriteTestsForLegacyCode         | React    | ToDoApp_ReactJS   | high       | avg   | 3321  | 448     | 7129   | 7577         | 42.17  | 3        | 4            |
| code_generation    | WriteTestsForLegacyCode         | Angular  | AngularCosmoPage  | avg        | high  | 5469  | 576     | 4900   | 5476         | 30.97  | 2.96     | 2.9          |
| code_generation    | WriteTestsForActualCode         | React    | ReactSelect       | extra_high | high  | 15993 | 1088    | 2572   | 3660         | 29.49  | 4        | 3.01         |
| code_documentation | BusinessFunctionality           | React    | ReactSignUp       | high       | low   | 1270  | 128     | 1333   | 1461         | 7.88   | 4        | 4            |
| code_documentation | BusinessFunctionality           | React    | ToDoApp_ReactJS   | high       | avg   | 3332  | 320     | 1557   | 1877         | 18.39  | 4        | 4            |
| code_documentation | BusinessFunctionality           | Angular  | AngularCosmoPage  | avg        | high  | 5480  | 1088    | 1626   | 2714         | 15.43  | 4        | 4            |
| code_documentation | EvaluateCodeQuality             | React    | ReactSignUp       | high       | low   | 1403  | 128     | 3800   | 3928         | 22.69  | 4        | 4            |
| code_documentation | EvaluateCodeQuality             | React    | ToDoApp_ReactJS   | high       | avg   | 3465  | 3712    | 6441   | 10153        | 60.00  | 4        | 4            |
| code_documentation | EvaluateCodeQuality             | Angular  | AngularCosmoPage  | avg        | high  | 5613  | 128     | 3864   | 3992         | 22.21  | 1.61     | 4            |
| code_documentation | DescribeTechnicalImplementation | Angular  | AngularCosmoPage  | avg        | high  | 5558  | 192     | 2961   | 3153         | 23.41  | 4        | 3.01         |
| code_documentation | DescribeTechnicalImplementation | React    | ReactSignUp       | high       | low   | 1348  | 448     | 2121   | 2569         | 17.20  | 4        | 4            |
| code_documentation | DescribeTechnicalImplementation | React    | ToDoApp_ReactJS   | high       | avg   | 3410  | 320     | 2741   | 3061         | 18.80  | 4        | 4            |

_Table 1. Detailed evaluation of OpenAI o1-mini in EPAM's LLM's Benchmark._

Below is a summary of the overall performance across all experiments:

| Total Input | Total Reasons | Output (payload) | Total Output | Total Time (sec) | Token per Second* | Experiment cost ($) | Average Accuracy | Average Completeness | 
|-------------|---------------|------------------|--------------|------------------|-------------------|---------------------|------------------|----------------------|
| 77314       | 33216         | 68827            | 102043       | 674.05           | 151.39            | 1.46                | 3.67             | 3.81                 |

_Table 2. Summary of OpenAI o1-mini experiment in EPAM's LLM's Benchmark._

This summary shows that the OpenAI o1-mini model has an average accuracy of 3.67 and an average completeness of 3.81 across all experiments. The model processed a total of 77,314 input tokens, generating 102,043 total output tokens in
674.05 seconds, with 33,216 reasoning tokens, resulting in an average speed of 151.39 tokens per second.

## Detailed Analysis

| Experiment         | Average Accuracy | Average Completeness | Average Time   | Average Tokens | Average Tokens/second |
|--------------------|------------------|----------------------|----------------|----------------|-----------------------|
| Code Translation   | 3.714            | 3.836                | 44.505 seconds | 6002.286       | 134.869               |
| Code Generation    | 3.547            | 3.694                | 22.358 seconds | 3874.143       | 173.275               |
| Code Documentation | 3.734            | 3.890                | 22.890 seconds | 3656.444       | 159.739               |

_Table 3. Detailed analysis of OpenAI o1-mini performance._

- Code Translation: The model performs well in translating code between different languages, with an average accuracy of 3.714 and an average completeness of 3.836. The average time taken for translation tasks is 44.505 seconds, with an
  average of 6002.286 tokens processed and a token per second rate of 134.869.
- Code Generation: The model generates code with an average accuracy of 3.547 and an average completeness of 3.694. The average time taken for code generation tasks is 22.358 seconds, with an average of 3874.143 tokens processed and a
  token per second rate of 173.275.
- Code Documentation: The model provides documentation for code with an average accuracy of 3.734 and an average completeness of 3.890. The average time taken for documentation tasks is 22.890 seconds, with an average of 3656.444 tokens
  processed and a token per second rate of 159.739.

Large Context Instruction Following (LCIF) score: 87.5%

| Experiment       | Accuracy | Completeness | Time        | Input Tokens | Reasoning | Output Tokens | Output Total Tokens |
|------------------|----------|--------------|-------------|--------------|-----------|---------------|---------------------|
| TranslateToReact | 4        | 3            | 976 seconds | 105948       | 76608     | 6551          | 83159               |
| UpdateReact      | 3        | 4            | 644 seconds | 58623        | 52096     | 6527          | 56065               |

_Table 4. Large Context Instruction Following (LCIF) score for OpenAI o1-mini._

1. TranslateToReact: The model achieved an accuracy of 4 and a completeness of 3 in translating code to React. The task took 976 seconds to complete, with 105948 input tokens, 76608 tokens for reasoning, and 6551 output tokens.
2. UpdateReact: The model achieved an accuracy of 3 and a completeness of 4 in updating React code. The task took 644 seconds to complete, with 58623 input tokens, 52096 tokens for reasoning, and 6527 output tokens.

## Conclusion

The OpenAI o1-mini model demonstrates strong performance across various code-related tasks, showcasing its versatility and effectiveness in handling complex programming challenges. Here are the key takeaways from the evaluation:

1. Overall Performance:
    - The model achieves high average scores in both accuracy (3.67) and completeness (3.81) across all experiments, indicating reliable and thorough code manipulation capabilities.
    - With an average processing speed of 151.39 tokens per second, o1-mini demonstrates efficient performance, especially considering the complexity of the tasks.

2. Code Translation:
    - O1-mini excels in code translation tasks, with an average accuracy of 3.714 and completeness of 3.836.
    - The model effectively handles translations between various frameworks (React, Angular, jQuery, Vanilla JS), showcasing its versatility.
    - While translation tasks take longer on average (44.505 seconds), this is likely due to the complexity of cross-framework conversions.

3. Code Generation:
    - In code generation tasks, the model performs well with an average accuracy of 3.547 and completeness of 3.694.
    - O1-mini shows particular strength in generating React components and writing tests for legacy code.
    - The faster average time (22.358 seconds) and higher tokens/second rate (173.275) for generation tasks indicate efficient performance in this category.

4. Code Documentation:
    - Documentation tasks see the highest performance, with average accuracy of 3.734 and completeness of 3.890.
    - The model excels in describing business functionality and evaluating code quality across different frameworks.
    - Documentation tasks are processed most efficiently, with the highest tokens/second rate (159.739) among all categories.

5. Large Context Instruction Following (LCIF):
    - O1-mini achieves a solid LCIF score of 87.5%, demonstrating good capability in handling large, complex code bases.
    - The model maintains high accuracy and completeness even with substantial input (over 100,000 tokens in one case), showcasing its ability to manage extensive contexts.

6. Areas for Improvement:
    - While generally strong, there's room for improvement in certain specific tasks, such as evaluating code quality for Angular (accuracy of 1.61 in one instance).
    - The model could potentially be optimized for faster processing in code translation tasks, which currently have the lowest tokens/second rate.

In conclusion, OpenAI o1-mini proves to be a highly capable model for a wide range of code-related tasks. Its consistent performance across translation, generation, and documentation, coupled with strong LCIF capabilities, makes it a
versatile tool for developers. The model's efficiency in processing complex programming tasks, particularly in documentation and code generation, is noteworthy. While there are minor areas for potential improvement, o1-mini's overall
performance indicates that it's a robust and reliable option for advanced code manipulation and analysis tasks.

<p style="text-align: center;">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>