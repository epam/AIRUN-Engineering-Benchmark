# Amazon Nova Pro

## Introduction

This report provides a detailed evaluation of the Amazon Nova Pro language model's performance on various code-related tasks. The model was tested on tasks involving code translation, generation, and documentation across different
programming languages and datasets. The analysis includes an overview of the experiments conducted, the categories evaluated, and the model's accuracy and completeness scores.

## Summary

The following table summarizes the overall performance of the Amazon Nova Pro model across all experiments:

| Experiment         | Category                        | Language | Dataset           | Complexity | Size  | Input | Reasons | Output | Time  | Accuracy<sup>*</sup> | Completeness<sup>*</sup> |
|--------------------|---------------------------------|----------|-------------------|------------|-------|-------|---------|--------|-------|----------------------|--------------------------|
| code_translation   | ReactToAngular                  | React    | ToDoApp_ReactJS   | high       | avg   | 3682  | 0       | 1724   | 26.06 | 3.27                 | 4                        |
| code_translation   | jQueryToReact                   | jQuery   | ToDoApp_jQuery    | high       | low   | 2622  | 0       | 1769   | 31.97 | 4                    | 3                        |
| code_translation   | AngularToReact                  | Angular  | AngularCosmoPage  | avg        | high  | 6135  | 0       | 1701   | 26.05 | 3.94                 | 0                        |
| code_translation   | UpdateReact                     | React    | ToDoApp_ReactJS   | high       | avg   | 3670  | 0       | 1759   | 31.30 | 4                    | 4                        |
| code_translation   | UpdateAngular                   | Angular  | ToDoApp_AngularJS | avg        | avg_2 | 2457  | 0       | 1829   | 26.02 | 2.97                 | 2.97                     |
| code_translation   | ReactToAngular                  | React    | ReactSignUp       | high       | low   | 1335  | 0       | 1326   | 19.05 | 2.18                 | 2.04                     |
| code_translation   | VanillaToReact                  | NativeJS | Piano_NativeJS    | high       | low   | 1544  | 0       | 1817   | 37.85 | 4                    | 2.92                     |
| code_generation    | ModifyReactApp                  | React    | ReactFetchAPI     | avg        | low   | 392   | 0       | 278    | 9.24  | 3.01                 | 2.99                     |
| code_generation    | GenerateBaseComponent           | none     | none              | none       | none  | 188   | 0       | 628    | 9.54  | 3.44                 | 3.03                     |
| code_generation    | GenerateReactApp                | none     | none              | none       | none  | 180   | 0       | 266    | 16.16 | 3.01                 | 3                        |
| code_generation    | WriteTestsForLegacyCode         | React    | ReactSignUp       | high       | low   | 1288  | 0       | 1044   | 14.97 | 2.27                 | 2.99                     |
| code_generation    | WriteTestsForLegacyCode         | React    | ToDoApp_ReactJS   | high       | avg   | 3635  | 0       | 1731   | 24.81 | 2.26                 | 1.68                     |
| code_generation    | WriteTestsForLegacyCode         | Angular  | AngularCosmoPage  | avg        | high  | 6109  | 0       | 1783   | 26.32 | 2.03                 | 1.85                     |
| code_generation    | WriteTestsForActualCode         | React    | ReactSelect       | extra_high | high  | 16751 | 0       | 1165   | 37.40 | 3                    | 2.99                     |
| code_documentation | BusinessFunctionality           | React    | ReactSignUp       | high       | low   | 1281  | 0       | 786    | 10.80 | 4                    | 3.12                     |
| code_documentation | BusinessFunctionality           | React    | ToDoApp_ReactJS   | high       | avg   | 3628  | 0       | 748    | 10.46 | 3.22                 | 4                        |
| code_documentation | BusinessFunctionality           | Angular  | AngularCosmoPage  | avg        | high  | 6102  | 0       | 815    | 11.76 | 2.98                 | 4                        |
| code_documentation | EvaluateCodeQuality             | React    | ReactSignUp       | high       | low   | 1403  | 0       | 1501   | 27.17 | 2.96                 | 4                        |
| code_documentation | EvaluateCodeQuality             | React    | ToDoApp_ReactJS   | high       | avg   | 3750  | 0       | 1749   | 27.36 | 3.5                  | 3.78                     |
| code_documentation | EvaluateCodeQuality             | Angular  | AngularCosmoPage  | avg        | high  | 6224  | 0       | 1335   | 19.50 | 4                    | 4                        |
| code_documentation | DescribeTechnicalImplementation | Angular  | AngularCosmoPage  | avg        | high  | 6182  | 0       | 849    | 12.25 | 4                    | 2.78                     |
| code_documentation | DescribeTechnicalImplementation | React    | ReactSignUp       | high       | low   | 1361  | 0       | 994    | 13.80 | 2.99                 | 4                        |
| code_documentation | DescribeTechnicalImplementation | React    | ToDoApp_ReactJS   | high       | avg   | 3708  | 0       | 1071   | 26.72 | 4                    | 3.99                     |

_Table 1. Detailed evaluation of the Amazon Nova Pro model's performance across various code-related tasks._

> <sup>*</sup> - Maximum score is 4. To learn more about our methodology for evaluating LLMs and scoring, please read [LLMs Benchmark Approach](../llm-approach.md).

Below is a summary of the overall performance across all experiments:

| Total Input | Total Reasons | Total Output | Total Time (sec) | Token per Second | Experiment cost ($) | Average Accuracy | Average Completeness |
|-------------|---------------|--------------|------------------|------------------|---------------------|------------------|----------------------|
| 83627       | 0             | 28668        | 496.56           | 57.73            | 0.29                | 3.26             | 3.09                 |

_Table 2. Summary of the Amazon Nova Pro model's overall performance across all experiments._

The summary shows that the Amazon Nova Pro model achieved an average accuracy of 3.26 and an average completeness of 3.09 across all experiments. The model processed a total of 83,627 tokens with an average speed of 57.73 tokens per second.
The total cost of the experiments was $0.29.

## Detailed Analysis

| Experiment         | Average Accuracy | Average Completeness | Average Time   | Average Tokens | Average Tokens/second |
|--------------------|------------------|----------------------|----------------|----------------|-----------------------|
| Code Translation   | 3.480            | 2.704                | 28.329 seconds | 1703.571       | 60.136                |
| Code Generation    | 2.717            | 2.647                | 19.778 seconds | 985.000        | 49.803                |
| Code Documentation | 3.517            | 3.741                | 17.757 seconds | 1094.222       | 61.622                |

_Table 3. Average performance metrics for different categories of code-related tasks._

- Code Translation: The Amazon Nova Pro model achieved an average accuracy of 3.48 and an average completeness of 2.70 in code translation tasks. The average processing time was 28.33 seconds per task, with an average speed of 60.14 tokens
  per second.
- Code Generation: The model had an average accuracy of 2.72 and an average completeness of 2.65 in code generation tasks. The average processing time was 19.78 seconds per task, with an average speed of 49.80 tokens per second.
- Code Documentation: For code documentation tasks, the model achieved an average accuracy of 3.52 and an average completeness of 3.74. The average processing time was 17.76 seconds per task, with an average speed of 61.62 tokens per
  second.

Large Context Instruction Following (LCIF) score: 56.25%

| Experiment       | Accuracy | Completeness | Time        | Input Tokens | Output Tokens |
|------------------|----------|--------------|-------------|--------------|---------------|
| TranslateToReact | 2        | 2            | 136 seconds | 143253       | 8196          |
| UpdateReact      | 2.5      | 2.5          | 70 seconds  | 75962        | 3731          |

_Table 4. Amazon Nova Pro model's performance on Large Context Instruction Following (LCIF) tasks._

LCIF experiment notes in english: The model understood the instructions well, but the code output required further refinement and corrections. In addition, much of the functionality was lost in the code translation.

1. TranslateToReact: The model translated a large React project to Angular in 136 seconds. Reached 143,253 in output and 8,196 in input tokens. The output code was not functional and required significant modifications to work correctly.
2. UpdateReact: The model updated a React project in 70 seconds. Reached 75,962 in input tokens and 3,731 in output tokens. The output code was partially functional but required additional modifications to match the original functionality.

## Conclusion

Amazon Nova Pro demonstrates competitive performance in certain areas while showing room for improvement in others when compared to leading language models in the field. Here are the key takeaways from the evaluation:

1. Overall Performance: Amazon Nova Pro achieved a total score of 71.9% across all categories, placing it in the mid-range of evaluated models. This indicates that while the model is capable, there is still a significant gap between Nova
   Pro and top-performing models like OpenAI's o1-mini (91.7%) and Claude 3.5 Sonnet v2 (89.6%).

2. Strengths:
    - Code Documentation: Nova Pro performed particularly well in this category, with an average accuracy of 3.517 and completeness of 3.741. This was its strongest area, showcasing the model's ability to understand and explain code
      effectively.
    - Efficiency: With an average processing speed of 57.73 tokens per second and a total experiment cost of only $0.29, Nova Pro demonstrates good efficiency and cost-effectiveness.

3. Areas for Improvement:
    - Code Generation: This was Nova Pro's weakest area, with average accuracy of 2.717 and completeness of 2.647. Improving the model's ability to generate accurate and complete code could significantly boost its overall performance.
    - Large Context Instruction Following (LCIF): With a score of 56.25%, Nova Pro lags behind top-performing models in this crucial area. Enhancing its ability to handle and process large contexts would be beneficial.

4. Consistency: Nova Pro showed varying performance across different tasks, with code documentation being a strong point and code generation needing improvement. This suggests that the model might benefit from more balanced training across
   different types of coding tasks.

5. Cost-Effectiveness: Given its relatively low cost and decent performance, Nova Pro could be an attractive option for organizations looking for a balance between capability and affordability in their AI solutions.

6. Comparative Standing: While Nova Pro doesn't match the performance of top-tier models like GPT-4o or Claude 3.5 Sonnet v2, it outperforms some widely used models like GPT-3.5 Turbo in overall score, suggesting it's a competitive option
   in the mid-range LLM market.

In conclusion, Amazon Nova Pro shows promise as a capable and cost-effective language model, particularly excelling in code documentation tasks. However, to compete with top-tier models, according to our benchmark, improvements in code
generation and large context handling are necessary. Its current performance makes it a viable option for organizations seeking a balance between cost and capability, especially for tasks that align with its strengths. As the field of LLMs
continues to evolve rapidly, it will be interesting to see how Amazon enhances Nova Pro's capabilities in future iterations to close the gap with leading models of our benchmark.
