# OpenAI o1 family (end of September 2024)

## Table of Contents

- [Introduction](#introduction)
- [Conducting an experiment](#conducting-an-experiment)
    - [Calculated Scores for Code Translation Experiment](#calculated-scores-for-code-translation-experiment)
    - [Calculated Scores for Code Generation Experiment](#calculated-scores-for-code-generation-experiment)
    - [Calculated Scores for Code Documentation Experiment](#calculated-scores-for-code-documentation-experiment)
    - [Calculated Scores for Large Context Instructions Following](#calculated-scores-for-large-context-instructions-following)
- [Final scores](#final-scores)
    - [Conclusion](#conclusion)
- [Useful links](#useful-links)

## Introduction

In September 2024, OpenAI unveiled a groundbreaking series of language models known as the "o1" family, introducing
o1-preview and o1-mini. These models represent a significant advancement in AI capability, particularly in complex
reasoning tasks. This research aims to conduct a comparative analysis of these new models against our previous leaders -
Claude 3.5 Sonnet and ChatGPT-4o (for comparison, we will take the results of these models from a previously conducted
experiment).

The o1 series introduces a novel approach to AI reasoning, with models trained to spend more time thinking through
problems before responding. This methodology aims to emulate human-like thought processes, enabling the models to refine
their thinking, explore different strategies, and recognize mistakes. Early tests have shown promising results, with the
o1 models demonstrating performance comparable to PhD-level students in challenging benchmark tasks across multiple
scientific disciplines.

Of particular note is the o1 models' exceptional performance in specialized domains. In a qualifying exam for the
International Mathematics Olympiad (IMO), the o1 model achieved an 83% success rate, significantly outperforming its
predecessor, GPT-4o, which solved only 13% of the problems correctly. Additionally, in coding proficiency tests, the
model reached the 89th percentile in Codeforces competitions, underscoring its potential in software development
tasks. - Introducing OpenAI o1-preview

There are two OpenAI "o1" family models available today (this is an early preview of these reasoning models):

1. o1-preview: reasoning model designed to solve hard problems across domains.
2. o1-mini: faster and cheaper reasoning model particularly good at coding, math, and science.

The table below presents the key characteristics of the models under evaluation:

| Model                      | Window Context | Max output | Price (Input/Output) | Data Cut-off | API Provider used in Benchmark | Other available API Providers |
|----------------------------|----------------|------------|----------------------|--------------|--------------------------------|-------------------------------|
| OpenAI o1-preview (0912)   | 128K           | 32K        | $15.00 / $60.00      | October 2023 | OpenAI                         | Azure                         |
| OpenAI o1-mini (0912)      | 128K           | 64K        | $3.00 / $12.00       | October 2023 | OpenAI                         | Azure                         |
| Claude 3.5 Sonnet          | 200K           | 4K         | $3.00 / $15.00       | April 2024   | Google Cloud Vertex AI         | AWS Bedrock, Anthropic        |
| ChatGPT-4o latest (august) | 128K           | 16K        | $5.00 / $15.00       | October 2023 | OpenAI                         | Azure                         |

Observations:

1. **o1-mini** has double the output tokens compared to o1-preview.
2. **o1-preview** has a significantly higher price than other models. Considering that o1 models generate 2-2.5 times more
   tokens (as we will demonstrate later), this could substantially impact the final cost of using the model.

It's important to note how o1 models handle tokens. Under the hood, the model uses reasoning tokens as part of the
output. Users should be cautious, as the context window limit may be reached unexpectedly due to this internal token
usage.

![reasoning_tokens.png](../../../images/llms/reasoning_tokens.png)
_*Picture from OpenAI website, reasoning guide_

## Conducting an experiment

Before proceeding with detailed analysis, we will conduct a comparative analysis of the model metrics after launching
our benchmark. This analysis covers execution time, I/O tokens, and cost (price for input + output) collected from the
entire experimental dataset. This comparison will provide a complete overview of the performance characteristics and
performance indicators of the models.

| Model                    | Total Time(min) | Total Input | Reasoning/Output | Total Output | Experiment Cost($) |
|--------------------------|-----------------|-------------|------------------|--------------|--------------------|
| OpenAi o1-preview (0912) | 26.120          | 77409       | 92096/54921      | 147017       | 9.98               |
| OpenAi o1-mini (0912)    | 13.503          | 77409       | 34432/75812      | 110244       | 1.56               |
| Claude 3.5 Sonnet        | 7.517           | 94783       | -/40769          | 40769        | 0.90               |
| ChatGPT-4o (august)      | 8.563           | 75818       | -/43856          | 43856        | 1.04               |

Observations:

1. As evident from the table, the o1-preview model underperformed in several parameters. It took the longest to complete
   the experiment, with reasoning tokens nearly double the useful output. Consequently, the final cost of the experiment
   was 10 times higher than other models.
2. The o1-mini model, due to its lower price, was not significantly more expensive than other models. Notably, its
   useful output (75812) sets new records in terms of volume.

## Calculated Scores for Code Translation Experiment

| Model                    | AVG Accuracy | AVG Completeness | AVG Time | AVG Token output | AVG Tokens/Second | Score  |
|--------------------------|--------------|------------------|----------|------------------|-------------------|--------|
| OpenAi o1-preview (0912) | 3.757        | 3.861            | 96.778   | 2842.429         | 29.371            | 0.8903 |
| OpenAi o1-mini (0912)    | 3.866        | 3.859            | 45.001   | 4175.857         | 92.794            | 0.9624 |
| Claude 3.5 Sonnet        | 3.694        | 3.871            | 28.546   | 2945.143         | 103.173           | 0.9565 |
| ChatGPT-4o (august)      | 3.894        | 3.857            | 28.451   | 2459.286         | 86.438            | 0.9589 |

Observation

OpenAI o1-mini (0912):

- Achieved the highest accuracy among all models.
- Demonstrated excellent completeness, nearly matching Claude 3.5 Sonnet.
- Produced the highest average token output, significantly surpassing other models.
- Showed good token processing speed, though not the fastest.
- Attained the highest overall score in this experiment.

OpenAI o1-preview (0912):

- Displayed good accuracy, slightly lower than o1-mini but competitive with other models.
- Matched o1-mini in completeness, performing well in this aspect.
- Had the longest average processing time, significantly higher than other models.
- Produced a competitive number of output tokens.
- Showed the lowest token processing speed.
- Achieved the lowest overall score among the models, despite good accuracy and completeness.

## Calculated Scores for Code Generation Experiment

| Model                    | AVG Accuracy | AVG Completeness | AVG Time | AVG Token output | AVG Tokens/Second | Score  |
|--------------------------|--------------|------------------|----------|------------------|-------------------|--------|
| OpenAi o1-preview (0912) | 3.511        | 3.470            | 40.481   | 1711.286         | 42.274            | 0.8450 |
| OpenAi o1-mini (0912)    | 3.870        | 3.314            | 44.117   | 2630.286         | 59.621            | 0.8846 |
| Claude 3.5 Sonnet        | 3.327        | 2.972            | 17.091   | 1541.000         | 90.166            | 0.8299 |
| ChatGPT-4o (august)      | 3.570        | 3.084            | 16.031   | 1443.286         | 90.031            | 0.8653 |

Observations:

OpenAI o1-mini (0912):

- Demonstrated the highest accuracy among all models.
- Showed good completeness, though not the highest.
- Had the longest average processing time.
- Generated the highest number of output tokens.
- Displayed moderate token processing speed.
- Achieved the highest overall score in this experiment.

OpenAI o1-preview (0912):

- Showed good accuracy, though lower than o1-mini.
- Demonstrated the highest completeness among all models.
- Had a longer processing time compared to Claude 3.5 Sonnet and ChatGPT-4o.
- Produced a competitive number of output tokens.
- Displayed the lowest token processing speed.
- Achieved a good overall score, ranking third among the models.

## Calculated Scores for Code Documentation Experiment

| Model                    | AVG Accuracy | AVG Completeness | AVG Time | AVG Token output | AVG Tokens/Second | Score  |
|--------------------------|--------------|------------------|----------|------------------|-------------------|--------|
| OpenAi o1-preview (0912) | 4.000        | 3.771            | 63.675   | 2391.889         | 37.564            | 0.9017 |
| OpenAi o1-mini (0912)    | 3.938        | 3.836            | 19.356   | 2952.000         | 152.514           | 0.9773 |
| Claude 3.5 Sonnet        | 3.508        | 3.430            | 13.566   | 952.222          | 70.191            | 0.8398 |
| ChatGPT-4o (august)      | 3.276        | 3.872            | 21.877   | 1785.444         | 81.614            | 0.8683 |

Observations

OpenAI o1-mini (0912):

- Demonstrated very high accuracy, second only to o1-preview.
- Showed excellent completeness, nearly matching ChatGPT-4o.
- Had a moderate processing time, faster than o1-preview but slower than other models.
- Generated the highest number of output tokens.
- Displayed the highest token processing speed by a significant margin.
- Achieved the highest overall score in this experiment.

OpenAI o1-preview (0912):

- Achieved perfect accuracy, outperforming all other models.
- Demonstrated very good completeness, though slightly lower than o1-mini.
- Had the longest average processing time by a significant margin.
- Produced a high number of output tokens, second only to o1-mini.
- Showed the lowest token processing speed.
- Attained the second-highest overall score, despite its slower processing.

## Calculated Scores for Large Context Instructions Following

| Model                    | AVG Accuracy | AVG Completeness | Total Input | Reasoning/Output | Total output | Total Time (min) | Score  |
|--------------------------|--------------|------------------|-------------|------------------|--------------|------------------|--------|
| OpenAi o1-preview (0912) | 3.5          | 3.5              | 164 571     | 128 704/10 520   | 139 224      | 27 min           | 0.875  |
| OpenAi o1-mini (0912)    | 3.5          | 3.5              | 155 757     | 42 048/8 397     | 50 445       | 5.6 min          | 0.875  |
| Claude 3.5 Sonnet        | 4            | 4                | ≈140 000    | -/≈8 000         | ≈8 000       | ≈3 min           | 1      |
| GPT-4o (2024-08-06)      | 3.5          | 4                | ≈160 000    | -/≈9 000         | ≈9 000       | ≈5 min           | 0.9375 |

Observations

OpenAI o1-preview (0912):

- Demonstrated equal performance in accuracy and completeness as o1-mini.
- Had the highest total input and output tokens among all models.
- Showed a significant amount of reasoning tokens (128,704), which greatly exceeded its actual output (10,520).
- Took the longest time to complete the task at 27 minutes, substantially more than other models.
- Despite the high token count and long processing time, achieved the same score as o1-mini.

OpenAI o1-mini (0912):

- Matched o1-preview in accuracy and completeness scores.
- Used fewer total input tokens compared to o1-preview.
- Exhibited a more balanced ratio between reasoning tokens (42,048) and actual output (8,397).
- Completed the task in 5.6 minutes, significantly faster than o1-preview but still slower than Claude 3.5 Sonnet and
  GPT-4o.
- Achieved the same score as o1-preview, despite using fewer tokens and less time.

In the Large Context Instructions Following, both OpenAI o1-preview and o1-mini models demonstrated consistent performance but fell
short of the best results. Despite their advanced reasoning capabilities and high token usage, particularly in the case
of o1-preview, they achieved lower scores compared to Claude 3.5 Sonnet and GPT-4o. The o1 models' performance suggests
that while they employ complex internal processing, this does not necessarily translate to superior outcomes in
instructions following tasks. Their identical scores, despite significant differences in token usage and processing time, indicate
that the additional computational effort of o1-preview may not yield proportional improvements in this specific type of
task.

## Final scores

| Model                    | Code Translation | Generation | Document | Context | Total Score |
|--------------------------|------------------|------------|----------|---------|-------------|
| OpenAi o1-preview (0912) | 0.890            | 0.845      | 0.902    | 0.875   | 0.878       |
| OpenAi o1-mini (0912)    | 0.962            | 0.885      | 0.977    | 0.875   | 0.925       |
| Claude 3.5 Sonnet        | 0.957            | 0.830      | 0.840    | 1       | 0.907       |
| GPT-4o (2024-08-06)      | 0.959            | 0.865      | 0.868    | 0.9375  | 0.907       |

![o1-total-score.png](../../../images/llms/o1-total-score.png)

## Conclusion

Based on the comprehensive evaluation of OpenAI's o1-preview and o1-mini models across various experiments, including
code translation, generation, documentation, and instructions following, we can draw several key insights:

1. Performance Variability:
    - The o1-mini model consistently demonstrated strong performance across all experiments, often achieving top scores
      in accuracy, completeness, and overall performance.
    - The o1-preview model showed mixed results, excelling in some areas like code documentation accuracy but
      underperforming in others, particularly in processing speed and efficiency.

2. Efficiency and Speed:
    - o1-mini proved to be significantly more efficient than o1-preview, consistently processing tasks faster and with a
      better balance between reasoning and output tokens.
    - o1-preview consistently had the longest processing times and the lowest tokens per second rate, indicating
      potential inefficiencies in its processing approach.

3. Token Usage:
    - Both models, especially o1-preview, demonstrated high token usage, often surpassing other models in total output.
      This suggests a more verbose or detailed approach to task completion.
    - The high ratio of reasoning tokens to output tokens, particularly in o1-preview, indicates a complex internal
      processing mechanism that doesn't always translate to superior results.

4. Cost-Effectiveness:
    - Despite its advanced features, o1-preview's significantly higher cost is not justified by its performance in our
      benchmarks. Its lengthy processing times and high token usage contribute to increased operational costs without
      proportional improvements in output quality.
    - o1-mini offers a more balanced profile, delivering competitive results at a lower cost, making it a more
      attractive option for many applications.

5. Large Context Instructions Following:
    - In the Large Context Instructions Following, both o1 models performed identically but fell short of the top-performing models
      like Claude 3.5 Sonnet and GPT-4o. This suggests that their complex reasoning processes may not always

6. Strengths and Weaknesses:
    - Strengths: Both models showed high accuracy and completeness scores across various tasks. o1-mini, in particular, demonstrated a good balance of performance and efficiency.
    - Weaknesses: o1-preview's long processing times and high token usage present significant drawbacks, especially considering its higher cost. Both models lagged in the instructions following task.

In conclusion, while the o1 series introduces innovative approaches to AI reasoning, our benchmarks reveal that these advancements do not consistently translate to superior performance across all tasks. The o1-mini model emerges as the more practical choice, offering competitive performance at a more reasonable cost. The o1-preview, despite its advanced features and higher price point, does not demonstrate the exceptional results one might expect in our comprehensive evaluation. This underscores the importance of task-specific model selection and the need for continued refinement in balancing sophisticated reasoning capabilities with practical efficiency and cost-effectiveness in AI language models.

### Useful links

Our benchmark approach and evaluation - [LLMs Benchmark Approach](../llm-approach.md)  

<p style="text-align: center;">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>