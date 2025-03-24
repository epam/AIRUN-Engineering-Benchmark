# Gemini 1.5 Pro vs Claude 3 Opus vs GPT-4 Turbo - May 2024

## Table of Contents

- [Introduction](#introduction)
- [Conducting an experiment](#conducting-an-experiment)
    - [Calculated Scores for Code Generation Experiment](#calculated-scores-for-code-generation-experiment)
    - [Calculated Scores for Code Translation Experiment](#calculated-scores-for-code-translation-experiment)
    - [Calculated Scores for Code Documentation Experiment](#calculated-scores-for-code-documentation-experiment)
    - [Calculated Scores for Large Context Instructions Following](#calculated-scores-for-large-context-instructions-following)
- [Results Analysis](#results-analysis)
- [Conclusion](#conclusion)
- [Comparison with Earlier versions](#comparison-with-earlier-versions)
- [Detailed Report](#detailed-report)

## Introduction

This benchmark study evaluates three advanced Large Language Models (LLMs) - Claude Opus, GPT-4 Turbo, and Gemini Pro -
focusing on their application in software engineering tasks such as code translation, generation, and documentation
generation. The study aims to provide a comprehensive comparison of each model's performance using Accuracy,
Completeness, and Response Generation Rate, Attempt Number, as primary evaluation metrics. The experiments are
categorized into four main areas:

1. **Code Generation:** Tasks include generating unit tests, creating and modifying React components, and configuring
   front-end projects.
2. **Code Translation:** Involves upgrading applications and translating code across different frameworks and languages.
3. **Code Documentation Generation:** Focuses on generating various forms of documentation, from inline comments to
   comprehensive user manuals.
4. **Large Context Instructions Following:** Assesses the models' ability to engage in a continuous dialogue to perform complex
   tasks sequentially.

The study employs an empirical research methodology, analyzing the performance of the LLMs through quantitative metrics
and model output evaluations against predefined complexity benchmarks.

Initial observations suggest that the models have varying strengths in generating maintainable code and comprehensive
documentation. The dialogue-based instructions following tests are crucial in assessing each model's ability to handle
real-world software development scenarios.

The findings from this benchmark study are expected to provide significant insights into each LLM's capabilities and
potential limitations, helping to optimize software engineering practices by integrating the most effective AI-driven
tools.

## Conducting an experiment

### Calculated Scores for Code Generation Experiment

| Model       | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time    | Avg Tokens/second | Score     |
|-------------|-------------|--------------|------------------|-------------|-------------------|-----------|
| Claude Opus | 1           | **3.692308** | **3.307692**     | 61.5160     | 30.8959           | *0.88756* |
| Gemini Pro  | 1.077       | 3.153846     | 2.615385         | **24.9482** | **32.8219**       | *0.76610* |
| GPT-4 Turbo | 1.462       | 3.307692     | 2.538462         | 51.5108     | 15.4476           | *0.70532* |

### Calculated Scores for Code Translation Experiment

| Model       | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time    | Avg Tokens/second | Score     |
|-------------|-------------|--------------|------------------|-------------|-------------------|-----------|
| Claude Opus | 1.083       | **3.692308** | **3.153846**     | 77.4763     | 33.7019           | *0.87596* |
| Gemini Pro  | 1.667       | 3.461538     | 2.846154         | **51.1408** | **35.2847**       | *0.79744* |
| GPT-4 Turbo | 2.083       | 3.538462     | 2.846154         | 86.2105     | 17.2750           | *0.73325* |

### Calculated Scores for Code Documentation Experiment

| Model           | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time    | Avg Tokens/sec | Score   |
|-----------------|-------------|--------------|------------------|-------------|----------------|---------|
| **Claude Opus** | 1.103       | 3.862069     | **3.758621**     | 54.6756     | 26.4307        | 0.93180 |
| **Gemini Pro**  | 1.966       | 3.206897     | 3.172414         | 67.9185     | **36.9911**    | 0.79449 |
| **GPT-4 Turbo** | 1.655       | **3.965517** | 3.620690         | **47.4571** | 16.8738        | 0.87368 |

### Calculated Scores for Large Context Instructions Following

| Model           | Avg Accuracy | Avg Completeness | Score  |
|-----------------|--------------|------------------|--------|
| **Claude Opus** | 3            | **4**            | 0,8750 |
| **Gemini Pro**  | 3            | 3.5              | 0,8125 |
| **GPT-4 Turbo** | 3            | 3.5              | 0,8125 |

## Results Analysis

According to our results analyses, each model has its strengths and weaknesses.

- Gemini excels **in speed** but lags in accuracy and stability.
- Claude 3 Opus stands out for its **accuracy, completeness, and stability**, making it a robust choice for various
  tasks.
- GPT-4-Turbo offers strong performance in specific areas like code documentation but is slower and less stable than
  Claude 3 Opus.

The impact of codebase size on performance is a common challenge across all models, suggesting a need for further
optimization in handling larger datasets.

## Conclusion

*Speed:*

Among the evaluated models, Gemini emerged as the fastest, followed by Claude 3 Opus. In comparison, GPT-4-Turbo was
notably slower, taking approximately twice the time of its competitors.

*Accuracy:*

In terms of accuracy, Claude 3 Opus demonstrated the highest average performance across various tasks. GPT-4 also
performed well, particularly excelling in specific categories such as code documentation, where it outperformed Claude 3
Opus. Gemini ranked last in accuracy but still delivered commendable results.

*Completeness:*

When evaluating the completeness of responses, Claude 3 Opus consistently provided the most comprehensive results across
all categories. GPT-4 was slightly better than Gemini, which trailed behind but still maintained a reasonable level of
completeness.

*Handling Size and Complexity:*

The complexity of the codebase did not significantly impact the performance of the models. All of them were
capable of effectively solving both low- and high-complexity code problems. However, as the size of the codebase
increased, there was a noticeable decline in accuracy and completeness. This trend was observed across all models,
indicating that larger codebases pose a greater challenge.

*Stability:*

In terms of stability, Claude 3 Opus was the most reliable, consistently returning the same results across multiple
attempts. In contrast, Gemini and GPT-4-Turbo produced different responses with each attempt. Additionally, Gemini
occasionally failed to complete the task entirely, highlighting a potential area for improvement in its stability.

*Large Context Instructions Following:*

All models achieved the same accuracy in this experiment. Claude 3 Opus outperformed the others in terms of completion.

The final score was calculated as an average across scores for individual experiment categories.

| Model          | Code Translation | Code Generation | Code Documentation | Large Context Instructions Following | Final Score |
|----------------|------------------|-----------------|--------------------|--------------------------------------|-------------|
| Claude 3 Opus  | 0,88             | 0,89            | 0,93               | 0,88                                 | 0,90        |
| Gemini Pro 1.5 | 0,83             | 0,77            | 0,79               | 0,81                                 | 0,80        |
| GPT-4-Turbo    | 0,74             | 0,71            | 0,87               | 0,81                                 | 0,78        |

*Note! GPT-4 usually shows better Accuracy and Completeness results than Gemini, but due to its low token/second rate,
its overall score is lower compared to Gemini.*

In summary, each model has its strengths and weaknesses. Gemini excels in speed but lags in accuracy and stability.
Claude 3 Opus stands out for its accuracy, completeness, and stability, making it a robust choice for various tasks.
GPT-4-Turbo offers strong performance in specific areas like code documentation but is slower and less stable than
Claude 3 Opus. The impact of codebase size on performance is a common challenge across all models, suggesting a need for
further optimization in handling larger datasets.

## Comparison with Earlier versions

Meanwhile, we are noticing significant performance improvements in GPT-4-Turbo and Gemini Pro 1.5 models compared to the
benchmark results of the earlier models' versions.

| Model               | Code Translation | Code Generation | Code Documentation | Large Context Instructions Following | Final Score |
|---------------------|------------------|-----------------|--------------------|--------------------------------------|-------------|
| Gemini Pro 1.0      | 0.67             | 0.60            | 0.68               | 0.20                                 | 0.54        |
| GPT-4 Turbo Preview | 0.75             | 0.41            | 0.62               | 0.9                                  | 0.67        |

Refer to the benchmark results provided in Appendix 1 for more information.

## Detailed Report

[Gemini 1.5 Pro vs GPT-4 Turbo vs Claude 3 Opus.pdf](../../../docs/Gemini-1.5-Pro-GPT-4-Turbo-Claude-3-Opus-report.pdf)

<p style="text-align: center;">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>