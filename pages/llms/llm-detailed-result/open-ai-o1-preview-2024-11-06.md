# OpenAI o1-preview (2024-11-06)

## Introduction

This article presents an analysis of various code-related tasks performed by the OpenAI o1-preview language model. We'll examine the model's performance across different categories of code manipulation, including translation, generation,
and documentation.

## Evaluation Summary

| Experiment         | Category                        | Language | Dataset           | Complexity | Size  | Input | Reasons | Output | Total Output | Time   | Accuracy | Completeness |
|--------------------|---------------------------------|----------|-------------------|------------|-------|-------|---------|--------|--------------|--------|----------|--------------|
| code_translation   | ReactToAngular                  | React    | ToDoApp_ReactJS   | high       | avg   | 3368  | 9728    | 3646   | 13374        | 634.97 | 4        | 4            |
| code_translation   | jQueryToReact                   | jQuery   | ToDoApp_jQuery    | high       | low   | 2350  | 5120    | 2518   | 7638         | 83.39  | 4        | 4            |
| code_translation   | AngularToReact                  | Angular  | AngularCosmoPage  | avg        | high  | 5498  | 7296    | 3156   | 10452        | 111.06 | 4        | 1.22         |
| code_translation   | UpdateReact                     | React    | ToDoApp_ReactJS   | high       | avg   | 3358  | 6720    | 2794   | 9514         | 651.32 | 4        | 4            |
| code_translation   | UpdateAngular                   | Angular  | ToDoApp_AngularJS | avg        | avg_2 | 2401  | 6144    | 3448   | 9592         | 87.00  | 3.99     | 4            |
| code_translation   | ReactToAngular                  | React    | ReactSignUp       | high       | low   | 1306  | 5632    | 1142   | 6774         | 71.02  | 3.96     | 3            |
| code_translation   | VanillaToReact                  | NativeJS | Piano_NativeJS    | high       | low   | 1423  | 6400    | 2688   | 9088         | 79.54  | 4        | 4            |
| code_generation    | ModifyReactApp                  | React    | ReactFetchAPI     | avg        | low   | 363   | 1472    | 350    | 1822         | 16.99  | 4        | 4            |
| code_generation    | GenerateBaseComponent           | none     | none              | none       | none  | 168   | 2176    | 1231   | 3407         | 146.66 | 4        | 4            |
| code_generation    | GenerateReactApp                | none     | none              | none       | none  | 158   | 2304    | 832    | 3136         | 36.59  | 3.38     | 4            |
| code_generation    | WriteTestsForLegacyCode         | React    | ReactSignUp       | high       | low   | 1259  | 6336    | 1711   | 8047         | 63.00  | 3.01     | 3.07         |
| code_generation    | WriteTestsForLegacyCode         | React    | ToDoApp_ReactJS   | high       | avg   | 3321  | 5376    | 6127   | 11503        | 99.21  | 4        | 4            |
| code_generation    | WriteTestsForLegacyCode         | Angular  | AngularCosmoPage  | avg        | high  | 5469  | 3072    | 2704   | 5776         | 55.76  | 1.82     | 1.99         |
| code_generation    | WriteTestsForActualCode         | React    | ReactSelect       | extra_high | high  | 15993 | 704     | 2767   | 3471         | 41.84  | 4        | 3            |
| code_documentation | BusinessFunctionality           | React    | ReactSignUp       | high       | low   | 1270  | 2624    | 1754   | 4378         | 40.50  | 4        | 3.27         |
| code_documentation | BusinessFunctionality           | React    | ToDoApp_ReactJS   | high       | avg   | 3332  | 896     | 1463   | 2359         | 17.86  | 3        | 4            |
| code_documentation | BusinessFunctionality           | Angular  | AngularCosmoPage  | avg        | high  | 5480  | 1728    | 1641   | 3369         | 30.01  | 2.97     | 4            |
| code_documentation | EvaluateCodeQuality             | React    | ReactSignUp       | high       | low   | 1403  | 4992    | 3066   | 8058         | 90.11  | 4        | 4            |
| code_documentation | EvaluateCodeQuality             | React    | ToDoApp_ReactJS   | high       | avg   | 3465  | 4224    | 2688   | 6912         | 97.23  | 4        | 4            |
| code_documentation | EvaluateCodeQuality             | Angular  | AngularCosmoPage  | avg        | high  | 5613  | 6400    | 3657   | 10057        | 104.58 | 3.85     | 4            |
| code_documentation | DescribeTechnicalImplementation | Angular  | AngularCosmoPage  | avg        | high  | 5558  | 960     | 2724   | 3684         | 41.09  | 4        | 2.27         |
| code_documentation | DescribeTechnicalImplementation | React    | ReactSignUp       | high       | low   | 1348  | 576     | 1959   | 2535         | 20.99  | 2.88     | 4            |
| code_documentation | DescribeTechnicalImplementation | React    | ToDoApp_ReactJS   | high       | avg   | 3410  | 2752    | 2605   | 5357         | 183.04 | 4        | 4            |

_Table 1. Detailed evaluation of OpenAI o1-preview in EPAM's LLM's Benchmark._

Below is a summary of the overall performance across all experiments:

| Total Input | Total Reasons | Output (payload) | Total Output | Total Time (sec) | Token per Second* | Experiment cost ($) | Average Accuracy | Average Completeness |
|-------------|---------------|------------------|--------------|------------------|-------------------|---------------------|------------------|----------------------|
| 77409       | 95680         | 57959            | 153639       | 2848.76          | 20.35             | 10.38               | 3.69             | 3.56                 |

_Table 2. Summary of OpenAI o1-preview experiment in EPAM's LLM's Benchmark._

This summary shows that the OpenAI o1-preview model has an average accuracy of 3.69 and an average completeness of 3.56 across all experiments. The model's performance is consistent across different categories of code manipulation tasks,
with a token per second rate of 20.35 and an experiment cost of 10.38 USD.

## Detailed Analysis

| Experiment         | Average Accuracy | Average Completeness | Average Time    | Average Tokens | Average Tokens/second |
|--------------------|------------------|----------------------|-----------------|----------------|-----------------------|
| Code Translation   | 3.993            | 3.460                | 245.472 seconds | 2770.286       | 11.286                |
| Code Generation    | 3.459            | 3.437                | 65.719 seconds  | 2246.000       | 34.176                |
| Code Documentation | 3.633            | 3.727                | 69.490 seconds  | 2395.222       | 34.469                |

_Table 3. Average performance of OpenAI o1-preview in different categories of code manipulation tasks._

- Code Translation: The model performs well in translating code between different languages, with an average accuracy of 3.993 and an average completeness of 3.460. The average time taken for translation tasks is 245.472 seconds, with an
  average of 2770.286 tokens processed and a token per second rate of 11.286.
- Code Generation: The model shows good performance in generating code, with an average accuracy of 3.459 and an average completeness of 3.437. The average time taken for generation tasks is 65.719 seconds, with an average of 2246.000
  tokens
  processed and a token per second rate of 34.176.
- Code Documentation: The model performs well in generating code documentation, with an average accuracy of 3.633 and an average completeness of 3.727. The average time taken for documentation tasks is 69.490 seconds, with an average of
  2395.222 tokens processed and a token per second rate of 34.469.

Large Context Instruction Following (LCIF) score: 87.5%

| Experiment       | Accuracy | Completeness | Time        | Input Tokens | Reasoning | Output Tokens | Output Total Tokens |
|------------------|----------|--------------|-------------|--------------|-----------|---------------|---------------------|
| TranslateToReact | 3        | 3            | 976 seconds | 105948       | 76608     | 6551          | 83159               |
| UpdateReact      | 4        | 4            | 644 seconds | 58623        | 52096     | 3969          | 56065               |

_Table 4. Large Context Instruction Following (LCIF) score for OpenAI o1-preview._

1. TranslateToReact: The model achieved an accuracy of 3 and a completeness of 3 in 976 seconds. It processed 105948 input tokens and generated 6551 output tokens, resulting in a total of 83159 tokens. Reasoning took 76608 tokens from 83159
   which is 92% of the output.
2. UpdateReact: The model achieved an accuracy of 4 and a completeness of 4 in 644 seconds. It processed 58623 input tokens and generated 3969 output tokens, resulting in a total of 56065 tokens. Reasoning took 52096 tokens from 56065 which
   is 93% of the output.

Based on the detailed report for OpenAI o1-preview, here's a comprehensive conclusion:

## Conclusion

The OpenAI o1-preview model demonstrates strong performance across various code-related tasks, showcasing its capabilities in code translation, generation, and documentation. Here are the key takeaways from the evaluation:

1. Overall Performance:
    - The model achieves high average scores in both accuracy (3.69) and completeness (3.56) across all experiments, indicating reliable and thorough code manipulation capabilities.
    - With an average processing speed of 20.35 tokens per second, o1-preview shows consistent performance across complex tasks, though it's notably slower than some other models like o1-mini.

2. Code Translation:
    - O1-preview excels in code translation tasks, with the highest average accuracy (3.993) among all categories.
    - The model effectively handles translations between various frameworks (React, Angular, jQuery, Vanilla JS), showcasing its versatility.
    - However, translation tasks take significantly longer on average (245.472 seconds) and have the lowest tokens/second rate (11.286), indicating a trade-off between accuracy and speed in this category.

3. Code Generation:
    - In code generation tasks, the model performs well with an average accuracy of 3.459 and completeness of 3.437.
    - O1-preview shows strength in generating React components and writing tests for legacy code, though it struggled with some specific tasks (e.g., writing tests for Angular code).
    - Generation tasks are processed more efficiently than translation tasks, with a higher tokens/second rate (34.176).

4. Code Documentation:
    - Documentation tasks see strong performance, with high average accuracy (3.633) and the highest average completeness (3.727) among all categories.
    - The model excels in describing business functionality and evaluating code quality across different frameworks.
    - Documentation tasks are processed most efficiently, with the highest tokens/second rate (34.469) among all categories.

5. Large Context Instruction Following (LCIF):
    - O1-preview achieves a solid LCIF score of 87.5%, demonstrating good capability in handling large, complex code bases.
    - The model maintains high accuracy and completeness even with substantial input (over 100,000 tokens in one case), showcasing its ability to manage extensive contexts.
    - Notably, a large portion of the output tokens (92-93%) is dedicated to reasoning, indicating thorough analysis of the input.

6. Areas for Improvement:
    - The model's processing speed, particularly for translation tasks, could be optimized to improve overall efficiency.
    - There's room for improvement in certain specific tasks, such as writing tests for Angular code (accuracy of 1.82 in one instance).
    - The higher experiment cost ($10.38) compared to some other models might be a consideration for large-scale applications.

In conclusion, OpenAI o1-preview demonstrates robust capabilities across various code-related tasks, with particular strengths in code translation accuracy and documentation completeness. Its ability to handle large contexts and maintain
high accuracy in complex tasks is noteworthy. While the model excels in accuracy and completeness, there's a trade-off with processing speed, especially in translation tasks. The o1-preview model proves to be a powerful tool for developers
needing high-quality code manipulation, particularly when accuracy is prioritized over speed. Future optimizations could focus on improving processing efficiency without compromising the model's strong performance in accuracy and
completeness.

<p style="text-align: center;">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>