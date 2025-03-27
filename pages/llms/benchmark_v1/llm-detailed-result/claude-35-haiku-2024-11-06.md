# Claude 3.5 Haiku (2024-11-06)

## Introduction

This article presents an analysis of various code-related tasks performed by the Claude 3.5 Haiku language model. We'll examine the model's performance across different categories, like translation, generation and documentation.

## Evaluation Summary

The following table provides detailed information on each experiment conducted. It includes the type of experiment, category, programming language, dataset used, complexity, input and output sizes, time taken, and accuracy and completeness
scores.

| Experiment         | Category                        | Language | Dataset           | Complexity | Size  | Input | Reasons | Output | Time  | Accuracy | Completeness |
|--------------------|---------------------------------|----------|-------------------|------------|-------|-------|---------|--------|-------|----------|--------------|
| code_translation   | ReactToAngular                  | React    | ToDoApp_ReactJS   | high       | avg   | 4057  | 0       | 2859   | 40.85 | 3.62     | 4            |
| code_translation   | jQueryToReact                   | jQuery   | ToDoApp_jQuery    | high       | low   | 2929  | 0       | 3247   | 46.90 | 4        | 4            |
| code_translation   | AngularToReact                  | Angular  | AngularCosmoPage  | avg        | high  | 6767  | 0       | 1405   | 19.89 | 4        | 3            |
| code_translation   | UpdateReact                     | React    | ToDoApp_ReactJS   | high       | avg   | 4047  | 0       | 2753   | 37.70 | 4        | 4            |
| code_translation   | UpdateAngular                   | Angular  | ToDoApp_AngularJS | avg        | avg_2 | 2794  | 0       | 2742   | 40.81 | 3.18     | 2.85         |
| code_translation   | ReactToAngular                  | React    | ReactSignUp       | high       | low   | 1575  | 0       | 1644   | 24.40 | 2.08     | 3            |
| code_translation   | VanillaToReact                  | NativeJS | Piano_NativeJS    | high       | low   | 1674  | 0       | 1989   | 29.63 | 4        | 4            |
| code_generation    | ModifyReactApp                  | React    | ReactFetchAPI     | avg        | low   | 449   | 0       | 815    | 13.32 | 4        | 4            |
| code_generation    | GenerateBaseComponent           | none     | none              | none       | none  | 215   | 0       | 1492   | 21.97 | 4        | 4            |
| code_generation    | GenerateReactApp                | none     | none              | none       | none  | 204   | 0       | 1175   | 18.84 | 4        | 4            |
| code_generation    | WriteTestsForLegacyCode         | React    | ReactSignUp       | high       | low   | 1527  | 0       | 1798   | 28.28 | 4        | 3.04         |
| code_generation    | WriteTestsForLegacyCode         | React    | ToDoApp_ReactJS   | high       | avg   | 4009  | 0       | 2337   | 36.50 | 4        | 3.44         |
| code_generation    | WriteTestsForLegacyCode         | Angular  | AngularCosmoPage  | avg        | high  | 6739  | 0       | 1643   | 25.83 | 1.93     | 1.94         |
| code_generation    | WriteTestsForActualCode         | React    | ReactSelect       | extra_high | high  | 20232 | 0       | 1571   | 23.90 | 4        | 3            |
| code_documentation | BusinessFunctionality           | React    | ReactSignUp       | high       | low   | 1521  | 0       | 414    | 7.17  | 3        | 3.98         |
| code_documentation | BusinessFunctionality           | React    | ToDoApp_ReactJS   | high       | avg   | 4003  | 0       | 366    | 6.76  | 3        | 3.15         |
| code_documentation | BusinessFunctionality           | Angular  | AngularCosmoPage  | avg        | high  | 6733  | 0       | 467    | 8.67  | 4        | 4            |
| code_documentation | EvaluateCodeQuality             | React    | ReactSignUp       | high       | low   | 1666  | 0       | 1196   | 17.82 | 3.02     | 4            |
| code_documentation | EvaluateCodeQuality             | React    | ToDoApp_ReactJS   | high       | avg   | 4148  | 0       | 1284   | 21.80 | 4        | 4            |
| code_documentation | EvaluateCodeQuality             | Angular  | AngularCosmoPage  | avg        | high  | 6878  | 0       | 1352   | 20.95 | 4        | 4            |
| code_documentation | DescribeTechnicalImplementation | Angular  | AngularCosmoPage  | avg        | high  | 6806  | 0       | 906    | 15.77 | 4        | 2.44         |
| code_documentation | DescribeTechnicalImplementation | React    | ReactSignUp       | high       | low   | 1594  | 0       | 768    | 13.20 | 4        | 1.94         |
| code_documentation | DescribeTechnicalImplementation | React    | ToDoApp_ReactJS   | high       | avg   | 4076  | 0       | 994    | 14.62 | 4        | 4            |

_Table 1. Detailed evaluation of Claude 3.5 Haiku in EPAM's LLMs Benchmark._

Below is a summary of the overall performance across all experiments:

| Total Input | Total Reasons | Total Output | Total Time (sec) | Token per Second | Experiment cost ($) | Average Accuracy | Average Completeness | 
|-------------|---------------|--------------|------------------|------------------|---------------------|------------------|----------------------|
| 94643       | 0             | 35217        | 535.58           | 65.75            | 0.27                | 3.64             | 3.47                 |

_Table 2. Summary of Claude 3.5 Haiku performance in EPAM's LLMs Benchmark._

This summary shows that Claude 3.5 Haiku has an average accuracy of 3.64 and an average completeness of 3.47 across all experiments. The model processed a total of 94,643 input tokens, generating 35,217 output tokens in 535.58 seconds,
resulting in an average speed of 65.75 tokens per second.

## Detailed Analysis

| Experiment         | Average Accuracy | Average Completeness | Average Time   | Average Tokens | Average Tokens/second |
|--------------------|------------------|----------------------|----------------|----------------|-----------------------|
| Code Translation   | 3.554            | 3.550                | 34.312 seconds | 2377.000       | 69.275                |
| Code Generation    | 3.704            | 3.346                | 24.092 seconds | 1547.286       | 64.225                |
| Code Documentation | 3.669            | 3.501                | 14.084 seconds | 860.778        | 61.117                |

_Table 3. Detailed analysis of Claude 3.5 Haiku performance in EPAM's LLMs Benchmark._

- Code Translation: The model performed well in translating code between different languages, with an average accuracy of 3.554 and an average completeness of 3.550. The average time taken for translation was 34.312 seconds, with an average
  of 2377 tokens processed per translation and an average speed of 69.275 tokens per second.
- Code Generation: The model showed good performance in generating code, with an average accuracy of 3.704 and an average completeness of 3.346. The average time taken for code generation was 24.092 seconds, with an average of 1547.286
  tokens processed per generation and an average speed of 64.225 tokens per second.
- Code Documentation: The model demonstrated strong performance in generating code documentation, with an average accuracy of 3.669 and an average completeness of 3.501. The average time taken for documentation was 14.084 seconds, with an
  average of 860.778 tokens processed per documentation and an average speed of 61.117 tokens per second.

Large Context Instruction Following (LCIF) score: 87.5%

| Experiment       | Accuracy | Completeness | Time        | Input Tokens | Output Tokens |
|------------------|----------|--------------|-------------|--------------|---------------|
| TranslateToReact | 3        | 4            | 155 seconds | 96357        | 7655          |
| UpdateReact      | 4        | 3            | 76 seconds  | 30569        | 3760          |

_Table 4. Large Context Instruction Following (LCIF) evaluation of Claude 3.5 Haiku in EPAM's LLMs Benchmark._

1. TranslateToReact: The model translated a large React project to Angular in 155 seconds, processing 96357 input tokens and generating 7655 output tokens.
2. UpdateReact: The model updated a React project in 76 seconds, processing 30569 input tokens and generating 3760 output tokens.

## Conclusion

The comprehensive evaluation of Claude 3.5 Haiku demonstrates strong performance across all tested domains, with particularly notable efficiency in processing speed and cost-effectiveness. Here are the key findings:

1. Performance Across Categories:
    - Strongest in Code Generation (accuracy: 3.704, completeness: 3.346)
    - Excellent Code Documentation capabilities (accuracy: 3.669, completeness: 3.501)
    - Solid Code Translation performance (accuracy: 3.554, completeness: 3.550)
    - Strong LCIF score of 87.5%, indicating reliable handling of large-scale tasks

2. Efficiency Metrics:
    - Impressive token processing speeds:
        * Code Translation: 69.275 tokens/second
        * Code Generation: 64.225 tokens/second
        * Code Documentation: 61.117 tokens/second
    - Notable cost efficiency at $0.28 for the entire test suite
    - Excellent average response times:
        * Documentation: 14.084 seconds
        * Code Generation: 24.092 seconds
        * Code Translation: 34.312 seconds

3. Key Strengths:
    - Exceptional consistency between accuracy and completeness scores
    - High performance across all complexity levels
    - Particularly strong with React-based tasks
    - Efficient handling of large datasets (processing 96,357 tokens in LCIF tasks)
    - Very balanced performance across all three main categories
    - Cost-effective operation compared to other models in its class

4. Areas for Potential Enhancement:
    - Slight performance variation in Angular-related tasks
    - Minor degradation in completeness scores for some complex code generation tasks
    - Some variation in performance with framework-specific translations

Overall, Claude 3.5 Haiku establishes itself as a highly capable model, particularly notable for its balanced performance and operational efficiency. The model's consistent scores across both accuracy and completeness metrics suggest a
well-rounded architecture capable of handling diverse programming tasks. Its strong LCIF performance and impressive token processing speeds make it particularly suitable for large-scale development projects.

The model's combination of high accuracy (3.64 average) and completeness (3.47 average), coupled with its cost-effectiveness, positions it as an excellent choice for organizations requiring reliable, efficient code-related tasks. The
minimal variance between accuracy and completeness scores across categories indicates a well-calibrated model that delivers consistent, dependable results.

<p style="text-align: center;">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>