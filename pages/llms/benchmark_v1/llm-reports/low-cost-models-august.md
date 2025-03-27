# GPT-4o mini, Llama3.1 405B, GPT-3.5 Turbo, Llama 3 70B - Compare Low-cost models

## Table of Contents

- [Introduction](#introduction)
- [Evaluation Methodology](#evaluation-methodology)
- [Models](#models)
- [Conducting an experiment](#conducting-an-experiment)
    - [Calculated Scores for Code Translation Experiment](#calculated-scores-for-code-translation-experiment)
    - [Calculated Scores for Code Generation Experiment](#calculated-scores-for-code-generation-experiment)
    - [Calculated Scores for Code Documentation Experiment](#calculated-scores-for-code-documentation-experiment)
    - [Calculated Scores for Large Context Instructions Following](#calculated-scores-for-large-context-instructions-following)
- [Final scores](#final-scores)
- [Conclusion](#conclusion)

## Introduction

On July 18, 2024, OpenAI introduced their new cost-efficient
model [GPT-4o mini](https://openai.com/index/gpt-4o-mini-advancing-cost-efficient-intelligence/), which is set to
replace the **GPT-3.5 Turbo**.

> Today, we're announcing GPT-4o mini, our most cost-efficient small model. We expect GPT-4o mini will significantly
> expand the range of applications built with AI by making intelligence much more affordable. It is priced at **15 cents
per million input tokens** and **60 cents per million output tokens**, an order of magnitude more affordable than
> previous frontier models and more than **60% cheaper than GPT-3.5 Turbo**.

Meanwhile, on July 23, Meta (Facebook) introduced their new language model from the Llama family—Llama 3.1, featuring
405 billion parameters, which is several times larger than their previous model with 70 billion parameters. A key
advantage of this model is that it can be hosted in your own environment or utilized through one of the many available
providers. More details about these providers can be found on the model's
webpage - [Llama Model Pricing](https://llama.meta.com/#:~:text=of%20our%20evals.-,Model%20Pricing,-Hosted%20Llama%203.1).

This report presents a comprehensive analysis of the performance of these four models across various tasks.

## Evaluation Methodology

The benchmark was conducted on a limited dataset as it was for GPT-4o, see [GPT-4o (0806) Benchmark](gpt-4o-0513.md) for more
details.

The evaluation of the results was conducted using our proprietary tool, LLM-Evaluator v1. For more details on the tool,
please refer to the [description](../automated-evaluation-with-llms.md). Based on our review of the automatic evaluation
and grading by LLM-Evaluator v1 on benchmark test results produced by LLMs, we determined that the evaluator's overall
accuracy was approximately **84%**. This means that a 16% error rate could be comparable to the estimation error that
can be produced by human evaluation.

The results are organized into four distinct categories: Code Translation, Code Generation, Code Documentation, and
Large Context Instructions Following.

**Note:** In all experiments, the evaluation of LLM results were performed on the first attempt. However, it is
important to note that Llama3 model consistently return the same result across multiple attempts.

## Models

| Model                                                                                      | Window Context | Max output | Price         | Data Cut-off   | API Provider used in Benchmark        |
|--------------------------------------------------------------------------------------------|----------------|------------|---------------|----------------|---------------------------------------|
| [GPT-4o mini](https://openai.com/index/gpt-4o-mini-advancing-cost-efficient-intelligence/) | 128K           | 16K        | $0.15 / $0.60 | Up to Oct 2023 | OpenAI                                |
| [Llama3.1 405B](https://llama.meta.com/docs/model-cards-and-prompt-formats/llama3_1)       | 128K           | 16K        | $3.00 / $3.00 | December, 2023 | [Fireworks.ai](https://fireworks.ai/) |
| [GPT-3.5 Turbo](https://platform.openai.com/docs/models/gpt-3-5-turbo)                     | 16K            | 4K         | $0.50 / $1.50 | Up to Sep 2021 | OpenAI                                |
| [Llama3 70B](https://ai.meta.com/blog/meta-llama-3/)                                       | 128K           | 8K         | N/A           | N/A            | EPAM AI DIAL<sup>*</sup>              |

> <sup>*</sup>EPAM AI DIAL is a proprietary tool developed by EPAM Systems, serves as a platform for hosting and utilizing models while also functioning as a proxy through Azure.

## Conducting an experiment

### Calculated Scores for Code Translation Experiment

| Model         | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score  |
|---------------|-------------|--------------|------------------|----------|-----------|-------------------|--------|
| GPT-4o mini   | 1.000       | 3.891        | 2.850            | 29.241   | 1596.143  | 54.586            | 0.8537 |
| Llama3.1 405B | 1.000       | 3.694        | 2.479            | 29.339   | 1563.000  | 53.274            | 0.7949 |
| GPT-3.5 Turbo | 1.000       | 3.327        | 2.021            | 18.624   | 1277.571  | 68.598            | 0.7349 |
| Llama3 70B    | 1.000       | 3.286        | 2.429            | 121.70   | 1573.571  | 12.930            | 0.6957 |

**Observations:**

- All models demonstrated high accuracy and moderate completeness.
- GPT-3.5 Turbo stands out with a significantly faster response time of 18 seconds, but it also processes a lower
  average number of tokens.
- The best overall performance was achieved by the GPT-4o Mini model.
- Although the GPT-4o Mini model has a capacity of 16k output tokens, it does not fully utilize this capacity, resulting
  in a loss of completeness.
- Llama3 70B had the lowest score and slowest processing time in this experiment.

### Calculated Scores for Code Generation Experiment

| Model         | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score  |
|---------------|-------------|--------------|------------------|----------|-----------|-------------------|--------|
| GPT-4o mini   | 1.000       | 2.990        | 2.524            | 13.763   | 861.857   | 62.620            | 0.7502 |
| Llama3.1 405B | 1.000       | 3.127        | 2.816            | 30.388   | 1165.429  | 38.352            | 0.7548 |
| GPT-3.5 Turbo | 1.000       | 2.513        | 1.281            | 7.132    | 431.286   | 60.474            | 0.5749 |
| Llama3 70B    | 1.000       | 3.333        | 2.667            | 62.691   | 808.167   | 12.891            | 0.7203 |

**Observations:**

- In the code generation experiment, GPT-4o Mini and Llama 3.1 405B achieved similar scores, while GPT-3.5 Turbo lagged
  significantly behind.
- Llama 3.1 405B received the highest scores for accuracy and completeness in this experiment. However, GPT-4o Mini
  matched its overall score due to being twice as fast, despite slightly lower accuracy and completeness.
- GPT-3.5 Turbo again demonstrated high processing speed, but the quality of its results was considerably lower compared
  to the other models.
- Llama3 70B showed good accuracy and completeness but had the slowest processing speed.

### Calculated Scores for Code Documentation Experiment

| Model         | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score  |
|---------------|-------------|--------------|------------------|----------|-----------|-------------------|--------|
| GPT-4o mini   | 1.000       | 3.570        | 3.178            | 14.152   | 940.000   | 66.424            | 0.8748 |
| Llama3.1 405B | 1.000       | 2.690        | 2.658            | 17.266   | 933.222   | 54.048            | 0.7161 |
| GPT-3.5 Turbo | 1.000       | 3.409        | 2.959            | 9.818    | 589.778   | 60.071            | 0.8272 |
| Llama3 70B    | 1.000       | 3.333        | 2.778            | 69.926   | 880.000   | 12.585            | 0.7335 |

**Observations:**

- In the code documentation experiment, GPT-4o Mini achieved the highest score, demonstrating strong performance across
  all metrics.
- Llama 3.1 405B showed lower accuracy and completeness compared to GPT-4o Mini but maintained a competitive average
  token count.
- GPT-3.5 Turbo performed well with a high speed and decent accuracy, but its completeness was slightly lower than
  GPT-4o Mini.
- Llama3 70B showed good accuracy and completeness but had the slowest processing speed.

### Calculated Scores for Large Context Instructions Following

| Model         | Avg Accuracy | Avg Completeness | Score  |
|---------------|--------------|------------------|--------|
| GPT-4o mini   | 2.5          | 2                | 0.5625 |
| Llama3.1 405B | 2.5          | 3                | 0.6875 |
| GPT-3.5 Turbo | 2            | 1.5              | 0.4375 |
| Llama3 70B    | 1            | 1                | 0.25   |

**Observations:**

- Results of GPT-4o mini, Llama3.1 405B, and GPT-3.5 Turbo were very similar, but GPT-3.5 Turbo's score was the worst
  among them.
- All models generated a lot of comments, unused imports, and tried to join several components into one.
- Llama3.1 405B shows the best result in this experiment.
- Llama3 70B achieved a very low score primarily because it failed to handle one of the tasks in automatic mode, a task
  that other models completed successfully.

## Final scores

| Model         | Code Translation | Generation | Document | Context | Total Score |
|---------------|------------------|------------|----------|---------|-------------|
| GPT-4o mini   | 0.854            | 0.750      | 0.875    | 0.5625  | 0.760       |
| Llama3.1 405B | 0.795            | 0.755      | 0.716    | 0.6875  | 0.738       |
| GPT-3.5 Turbo | 0.735            | 0.575      | 0.827    | 0.4375  | 0.644       |
| Llama3 70B    | 0.696            | 0.720      | 0.734    | 0.25    | 0.600       |

## Conclusion

Based on our comprehensive analysis and experiments, we have evaluated the performance of four prominent language
models: GPT-4o Mini, Llama 3.1 405B, GPT-3.5 Turbo, and Llama 3.1 70B across four distinct tasks: Code Translation, Code
Generation, Code Documentation, and Large Context Instructions Following. The results provide valuable insights into the strengths
and weaknesses of each model.

**1. GPT-4o Mini**

- **Strengths:**
    - Demonstrated the highest overall performance in Code Translation and Code Documentation, combining high accuracy
      and moderate completeness with efficient processing times.
    - Exhibited strong performance in Code Generation, achieving a balance between speed and quality.
    - The most cost-effective token pricing
- **Weaknesses:**
    - Despite having a capacity of 16k output tokens, the model does not fully utilize this capacity, leading to a loss
      in completeness.
- **Best Use Cases:**
    - Ideal for tasks that require a high degree of accuracy and moderate completeness, such as code translation and
      documentation.
    - Suitable for scenarios where cost-efficiency and speed are critical factors.

**2. Llama 3.1 405B**

- **Strengths:**
    - Achieved the highest scores for accuracy and completeness in the Code Generation experiment.
    - Showed competitive performance in Large Context Instructions Following.
- **Weaknesses:**
    - Lower overall scores in Code Documentation compared to GPT-4o Mini.
    - Despite its large parameter size, it did not consistently outperform GPT-4o Mini across all metrics.
- **Best Use Cases:**
    - Suitable for environments where hosting the model locally is preferred.
    - Best suited for tasks where accuracy and completeness are paramount, such as complex code generation tasks.

**3. GPT-3.5 Turbo**

- **Strengths:**
    - Demonstrated the fastest processing times across most experiments, particularly in Code Translation and Code
      Generation.
- **Weaknesses:**
    - Consistently lower completeness scores, indicating that the model may truncate outputs to achieve faster results.
    - The lowest overall performance in the Large Context Instructions Following experiment.
    - Model is outdated and OpenAI recommends switching to GPT-4o mini.
- **Best Use Cases:**
    - Ideal for tasks requiring rapid responses and where speed is a critical factor, such as real-time applications.

**4. Llama 3.1 70B**

- **Strengths:**
    - Showed potential in code generation tasks with good accuracy and completeness.
- **Weaknesses:**
    - Consistently slower processing times across all experiments.
    - Lowest performance in the Large Context Instructions Following experiment.
- **Best Use Cases:**
    - May be suitable for tasks where processing time is not a critical factor and high accuracy is desired.

**Final Recommendation:**

GPT-4o Mini is recommended due to its balanced performance across all metrics and cost-efficiency.

Overall, each model has its unique strengths and can be chosen based on the specific requirements of the task at hand.
The GPT-4o Mini stands out as a versatile and cost-effective solution, while Llama 3.1 405B shows slightly better
accuracy and completeness in some tasks and can be hosted at your workspace. GPT-3.5 Turbo, while deprecated, can still
be used for existing speed-critical applications as it shows slightly better speed. Llama 3.1 70B, despite its larger
size, may be suitable for specific use cases where processing time is not a critical factor.

<p style="text-align: center;">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>