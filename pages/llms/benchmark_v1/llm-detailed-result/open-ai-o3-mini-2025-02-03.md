# OpenAI o3-mini (2025-01-31)

## Introduction

This article presents a comprehensive analysis of OpenAI's o3-mini language model, evaluated across various code-related tasks. The o3-mini model represents a significant advancement in the OpenAI model lineup, combining high performance
with improved cost-efficiency and new capabilities including tool calling, structured outputs, and developer messages. This evaluation examines the model's performance in code translation, generation, documentation, and
large context instruction following (LCIF).

## Evaluation Summary

| Experiment         | Category                        | Language | Dataset           | Complexity | Size  | Input | Reasons | Output | Total Output | Time  | Accuracy | Completeness |
|--------------------|---------------------------------|----------|-------------------|------------|-------|-------|---------|--------|--------------|-------|----------|--------------|
| code_translation   | ReactToAngular                  | React    | ToDoApp_ReactJS   | high       | avg   | 3268  | 3328    | 2552   | 5880         | 42.67 | 3.78     | 4            |
| code_translation   | jQueryToReact                   | jQuery   | ToDoApp_jQuery    | high       | low   | 2342  | 1344    | 2705   | 4049         | 19.98 | 4        | 4            |
| code_translation   | AngularToReact                  | Angular  | AngularCosmoPage  | avg        | high  | 5412  | 1728    | 4728   | 6456         | 36.74 | 4        | 4            |
| code_translation   | UpdateReact                     | React    | ToDoApp_ReactJS   | high       | avg   | 3257  | 3840    | 2870   | 6710         | 32.57 | 4        | 4            |
| code_translation   | UpdateAngular                   | Angular  | ToDoApp_AngularJS | avg        | avg_2 | 2274  | 3776    | 3002   | 6778         | 28.06 | 3.12     | 4            |
| code_translation   | ReactToAngular                  | React    | ReactSignUp       | high       | low   | 1272  | 1920    | 1437   | 3357         | 20.54 | 2.92     | 3.01         |
| code_translation   | VanillaToReact                  | NativeJS | Piano_NativeJS    | high       | low   | 1401  | 4992    | 2351   | 7343         | 43.08 | 4        | 4            |
| code_generation    | ModifyReactApp                  | React    | ReactFetchAPI     | avg        | low   | 378   | 896     | 334    | 1230         | 6.14  | 4        | 4            |
| code_generation    | GenerateBaseComponent           | none     | none              | none       | none  | 198   | 2624    | 1613   | 4237         | 21.68 | 4        | 4            |
| code_generation    | GenerateReactApp                | none     | none              | none       | none  | 187   | 832     | 313    | 1145         | 13.02 | 3.01     | 3            |
| code_generation    | WriteTestsForLegacyCode         | React    | ReactSignUp       | high       | low   | 1229  | 2624    | 1336   | 3960         | 50.04 | 3.32     | 2.02         |
| code_generation    | WriteTestsForLegacyCode         | React    | ToDoApp_ReactJS   | high       | avg   | 3225  | 3776    | 5977   | 9753         | 54.83 | 4        | 3.18         |
| code_generation    | WriteTestsForLegacyCode         | Angular  | AngularCosmoPage  | avg        | high  | 5388  | 1408    | 3722   | 5130         | 40.84 | 1.98     | 2.18         |
| code_generation    | WriteTestsForActualCode         | React    | ReactSelect       | extra_high | high  | 15763 | 2688    | 2645   | 5333         | 31.11 | 3        | 1.15         |
| code_documentation | BusinessFunctionality           | React    | ReactSignUp       | high       | low   | 1222  | 320     | 731    | 1051         | 10.88 | 4        | 4            |
| code_documentation | BusinessFunctionality           | React    | ToDoApp_ReactJS   | high       | avg   | 3218  | 256     | 728    | 984          | 8.50  | 4        | 3.32         |
| code_documentation | BusinessFunctionality           | Angular  | AngularCosmoPage  | avg        | high  | 5381  | 512     | 1136   | 1648         | 13.55 | 4        | 2.21         |
| code_documentation | EvaluateCodeQuality             | React    | ReactSignUp       | high       | low   | 1346  | 320     | 2312   | 2632         | 18.24 | 2.05     | 4            |
| code_documentation | EvaluateCodeQuality             | React    | ToDoApp_ReactJS   | high       | avg   | 3342  | 704     | 2635   | 3339         | 15.70 | 3.05     | 4            |
| code_documentation | EvaluateCodeQuality             | Angular  | AngularCosmoPage  | avg        | high  | 5505  | 768     | 2597   | 3365         | 21.12 | 4        | 4            |
| code_documentation | DescribeTechnicalImplementation | Angular  | AngularCosmoPage  | avg        | high  | 5459  | 448     | 1936   | 2384         | 10.25 | 4        | 4            |
| code_documentation | DescribeTechnicalImplementation | React    | ReactSignUp       | high       | low   | 1300  | 384     | 1313   | 1697         | 16.73 | 4        | 4            |
| code_documentation | DescribeTechnicalImplementation | React    | ToDoApp_ReactJS   | high       | avg   | 3296  | 448     | 1625   | 2073         | 13.30 | 4        | 4            |

_Table 1. Detailed evaluation of OpenAI o3-mini in EPAM's LLM's Benchmark._

Below is a summary of the overall performance across all experiments:

| Total Input | Total Reasons | Output (payload) | Total Output | Total Time (sec) | Token per Second | Experiment cost ($) | Average Accuracy | Average Completeness | 
|-------------|---------------|------------------|--------------|------------------|------------------|---------------------|------------------|----------------------|
| 75663       | 39936         | 50598            | 90534        | 569.57           | 158.95           | 0.48                | 3.58             | 3.48                 |

_Table 2. Summary of OpenAI o3-mini experiment in EPAM's LLM's Benchmark._

This summary demonstrates that the OpenAI o3-mini model achieves an impressive average accuracy of 3.58 and an average completeness of 3.48 across all experiments. The model processed 75,663 input tokens and generated 90,534 total output
tokens in 569.57 seconds, with 39,936 reasoning tokens, resulting in a notable processing speed of 158.95 tokens per second. Importantly, the total experiment cost was only $0.48, highlighting the model's cost-effectiveness.

## Detailed Analysis

| Experiment         | Average Accuracy | Average Completeness | Average Time   | Average Tokens | Average Tokens/second |
|--------------------|------------------|----------------------|----------------|----------------|-----------------------|
| Code Translation   | 3.689            | 3.859                | 31.948 seconds | 5796.143       | 181.422               |
| Code Generation    | 3.330            | 2.790                | 31.094 seconds | 4398.286       | 141.452               |
| Code Documentation | 3.678            | 3.726                | 14.252 seconds | 2130.333       | 149.472               |

_Table 3. Detailed analysis of OpenAI o3-mini performance._

- Code Translation Performance. The model demonstrates exceptional capabilities in code translation tasks:
    - Achieves a high average accuracy of 3.689 and completeness of 3.859
    - Processes translations efficiently with an average time of 31.948 seconds
    - Shows impressive token processing speed of 181.422 tokens per second
    - Particularly excels in framework translations (React, Angular, jQuery)
    - Notable perfect scores (4.0) in multiple translation tasks, including complex jQuery to React and Angular to React conversions

- Code Generation Capabilities. In code generation tasks, the model shows strong performance with some areas for optimization:
    - Maintains a solid average accuracy of 3.330 and completeness of 2.790
    - Processes generation tasks in an average of 31.094 seconds
    - Achieves a token processing rate of 141.452 tokens per second
    - Excels in basic component generation and app modifications
    - Shows some variability in test writing tasks, with scores ranging from 1.98 to 4.0

- Code Documentation Efficiency. The model demonstrates strong documentation capabilities:
    - Maintains high average accuracy of 3.678 and completeness of 3.726
    - Processes documentation tasks quickly at 14.252 seconds on average
    - Achieves efficient token processing at 149.472 tokens per second
    - Shows particular strength in technical implementation documentation
    - Consistently achieves perfect scores in describing complex system architectures

Large Context Instruction Following (LCIF) score: 100%

| Experiment       | Accuracy | Completeness | Time | Input Tokens | Reasoning | Output Tokens | Output Total Tokens |
|------------------|----------|--------------|------|--------------|-----------|---------------|---------------------|
| TranslateToReact | 4        | 4            | 85   | 54052        | 6976      | 3468          | 10444               |
| UpdateReact      | 4        | 4            | 95   | 57017        | 9088      | 3472          | 12560               |

- Perfect score of 100% in LCIF capabilities
- Both test cases achieved maximum scores of 4.0 in accuracy and completeness
- Successfully processes substantial input tokens (54,052 and 57,017) with high accuracy

The OpenAI o3-mini model represents a significant advancement in the field of code-focused language models, offering an impressive balance of performance, efficiency, and cost-effectiveness. Key conclusions from the evaluation include:

1. Overall Excellence:
    - High average accuracy (3.58) and completeness (3.48) across all tasks
    - Superior token processing speed (158.95 tokens/second)
    - Outstanding cost efficiency at $0.48 for comprehensive testing

2. Strengths by Category:
    - Code Translation: Exceptional performance with 3.689 accuracy and 3.859 completeness
    - Documentation: Fast processing with high accuracy (3.678) and completeness (3.726)
    - LCIF: Perfect 100% score demonstrating excellent handling of large contexts

3. Production Readiness:
    - Implementation of professional-grade features like tool calling and structured outputs
    - Robust performance across varied task complexities
    - Efficient resource utilization and processing speeds

4. Areas for Optimization:
    - Some variability in code generation tasks
    - Potential for improvement in test writing capabilities
    - Opportunity for enhanced performance in specific edge cases

The o3-mini model stands out as a highly capable, cost-effective solution for professional development teams, particularly those requiring a balance of performance and efficiency. Its new features and improved cost structure, combined with
strong technical capabilities, make it an excellent choice for production environments where reliability, speed, and cost-effectiveness are crucial factors.

<p style="text-align: center;">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>