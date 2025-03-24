# Claude 3.5 Sonnet, GPT-4o, Gemini 1.5 Pro, ChatGPT-4o (September 2024)

# Table of Contents

- [Introduction](#introduction)
- [Conducting an experiment](#conducting-an-experiment)
    - [Calculated Scores for Code Translation Experiment](#calculated-scores-for-code-translation-experiment)
    - [Calculated Scores for Code Generation Experiment](#calculated-scores-for-code-generation-experiment)
    - [Calculated Scores for Code Documentation Experiment](#calculated-scores-for-code-documentation-experiment)
    - [Calculated Scores for Large Context Instructions Following](#calculated-scores-for-large-context-instructions-following)
- [Final scores](#final-scores)
- [Conclusion](#conclusion)

## Introduction

In early August, OpenAI and DeepMind introduced new versions of their models: **GPT-4o** (2024-08-06) and **Gemini 1.5
Pro** (2024-08-01, experimental preview), respectively. Previously, on June 24, Anthropic had released their advanced
model, **Claude 3.5 Sonnet**, which the company claimed to possess higher intelligence than Claude 3 Opus while being
more cost-effective. We conducted a comparative analysis of these three top-tier models.

The evaluation aimed to assess the relative performance and capabilities of these state-of-the-art language models
across four key aspects: Code Translation, Code Generation, Code Documentation, and Large Context Instructions Following. Our
comprehensive benchmark suite was designed to rigorously test these specific areas, providing a multifaceted view of
each model's strengths and capabilities. This comparison offers valuable insights into the current landscape of advanced
AI models and their respective proficiencies in these critical domains.

**UPD 08-09-2024:** During the course of our experiment, OpenAI introduced a new model to their lineup: **ChatGPT-4o
latest**. Initially, we (along with many others in the field) assumed this was simply an alias for their most recent
model, given the inclusion of "latest" in its name. However, this assumption was challenged when the model appeared on
the [https://lmarena.ai/](https://lmarena.ai/) website's ranking, securing the top position. This unexpected development
prompted us to include ChatGPT-4o latest in our evaluation process. This addition allows us to assess whether ChatGPT-4o
latest indeed represents a significant advancement in performance compared to other models in our study.

The table below presents the key characteristics of the models:

| Model                                                                                                       | Window Context | Max Output | Price (Input/Output)                             | Data Cut-off  | API Provider used in Benchmark                                                                                           | Other available API Providers |
|-------------------------------------------------------------------------------------------------------------|----------------|------------|--------------------------------------------------|---------------|--------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| [Claude 3.5 Sonnet](https://www.anthropic.com/news/claude-3-5-sonnet)                                       | 200K           | 4K         | $3.00 / $15.00                                   | April 2024    | [Google Cloud Vertex AI](https://console.cloud.google.com/vertex-ai/publishers/anthropic/model-garden/claude-3-5-sonnet) | AWS Bedrock, Anthropic        |
| [GPT-4o 2024-08-06](https://platform.openai.com/docs/models/gpt-4o)                                         | 128K           | 16K        | $2.50 / $10.00                                   | October 2023  | OpenAI                                                                                                                   | Azure                         |
| [Gemini 1.5 Pro 2024-08-01](https://aistudio.google.com/app/prompts/new_chat?model=gemini-1.5-pro-exp-0801) | 1M             | 8K         | $3.50 <= 128K < $7.00 /  $10.50 <= 128K < $21.00 | November 2023 | [Google AI Studio](https://aistudio.google.com/app/prompts/new_chat?model=gemini-1.5-pro-exp-0801)                       | -                             |
| [ChatGPT-4o latest](https://platform.openai.com/docs/models/gpt-4o)                                         | 128K           | 16K        | $5.00 / $15.00                                   | October 2023  | OpenAI                                                                                                                   | Azure                         |

### Observations:

- **Claude 3.5 Sonnet** – maintains the same characteristics as Claude 3 Opus but at a reduced cost (Claude 3 Opus
  pricing: $15.00 / $75.00). According to Anthropic, this model offers higher intelligence at a lower price point.
  ![sonnet-3.5-intelligence.png](../../../images/llms/sonnet-3.5-intelligence.png)
- **GPT-4o (2024-08-06)** – key differences from the previous version include an increased number of max output tokens,
  now 16K, and a reduced price: $2.50 / $10.00 compared to the previous $5.00 / $15.00.
- **Gemini 1.5 Pro (2024-08-01)** – is an experimental preview version. No specific differences from previous versions
  were announced, but upon its release, this model claimed the top position on [lmarena.ai](https://lmarena.ai/).
- **ChatGPT-4o latest** – The model version continuously points to the version of GPT-4o used in ChatGPT, and is updated
  frequently. OpenAI states that this version is used in ChatGPT.

## Conducting an experiment

Before proceeding into the detailed evaluations, we will conduct a comparative analysis of key parameters across
different test runs for various models. This analysis encompasses input/output tokens and tokens per second, utilizing
data collected from the entire experimental dataset. This comparison will provide a comprehensive overview of the
models' performance characteristics and efficiency metrics.

| Model                     | Total Input | Total Output | Token/Second |
|---------------------------|-------------|--------------|--------------|
| Claude 3 Opus             | 94480       | 45543        | 30.869       |
| **Claude 3.5 Sonnet**     | 94783       | 40769        | 90.398       |
| GPT-4o (2024-05-13)       | 75581       | 40935        | 53.233       |
| **GPT-4o (2024-08-06)**   | 75818       | 31244        | 88.457       |
| Gemini 1.5 Pro (0409)     | 87596       | 40652        | 35.258       |
| **Gemini 1.5 Pro (0801)** | 87887       | 44630        | 47.491       |
| **ChatGPT-4o latest**     | 75581       | 43856        | 85.358       |

- All new models have increased processing speed, particularly Claude 3.5 Sonnet and GPT-4o.
- Although the new version of GPT-4o has a four-fold increase in max output parameter (16K), **it produced fewer output
  tokens compared to the previous version**.
- Input token values remained consistent across model versions.

### Calculated Scores for Code Translation Experiment

| Model                       | AVG Accuracy | AVG Completeness | AVG Time   | AVG Token output | AVG Tokens/Second | Score      |
|-----------------------------|--------------|------------------|------------|------------------|-------------------|------------|
| Claude 3.5 Sonnet           | 3.694        | **3.871**        | 28.546     | **2945.143**     | **103.173**       | 0.9565     |
| GPT-4o (2024-08-06)         | 3.734        | 3.220            | **22.685** | 2254.571         | 99.388            | 0.8918     |
| Gemini 1.5 Pro (2024-08-01) | 3.721        | 3.166            | 64.229     | **2946.071**     | 45.868            | 0.8332     |
| **ChatGPT-4o latest**       | **3.894**    | 3.857            | 28.451     | 2459.286         | 86.438            | **0.9589** |

- **Accuracy**: All models demonstrate approximately equivalent results, with ChatGPT-4o latest showing a slight edge.
- **Completeness**: ChatGPT-4o latest and Claude 3.5 Sonnet exhibited the best performance, significantly outperforming
  GPT-4o and Gemini 1.5 Pro.
- **Time**: GPT-4o and ChatGPT-4o latest proved to be the fastest, with nearly identical processing times. Both were
  almost 2-3 times faster than Gemini 1.5 Pro.
- **Tokens**: Claude 3.5 Sonnet and Gemini showed the highest output, while GPT-4o produced about 30% fewer tokens.
  ChatGPT-4o latest fell between these extremes.
- **Token/Second**: Claude 3.5 Sonnet demonstrated the highest processing speed, closely followed by GPT-4o and
  ChatGPT-4o latest. Gemini was notably slower, processing at about half the speed of the others.
- **Score**: ChatGPT-4o latest achieved the highest overall score, narrowly surpassing Claude 3.5 Sonnet. GPT-4o ranked
  third, with Gemini 1.5 Pro trailing behind.

### Calculated Scores for Code Generation Experiment

| Model                       | AVG Accuracy | AVG Completeness | AVG Time   | AVG Token output | AVG Tokens/Second | Score      |
|-----------------------------|--------------|------------------|------------|------------------|-------------------|------------|
| Claude 3.5 Sonnet           | 3.327        | 2.972            | 17.091     | 1541.000         | **90.166**        | 0.8299     |
| GPT-4o (2024-08-06)         | 3.413        | 2.496            | **10.999** | 950.000          | 86.370            | 0.7866     |
| Gemini 1.5 Pro (2024-08-01) | 3.255        | **3.139**        | 43.329     | **2190.714**     | 50.559            | 0.7955     |
| **ChatGPT-4o latest**       | **3.570**    | 3.084            | 16.031     | 1443.286         | **90.031**        | **0.8653** |

- **Accuracy**: All models again showed equivalent results, with ChatGPT-4o latest slightly outperforming the others.
- **Completeness**: ChatGPT-4o latest and Gemini 1.5 Pro showed the best results, while GPT-4o's results were the
  lowest, likely due to its lower token output.
- **Time**: GPT-4o remained the fastest in execution time, with ChatGPT-4o latest and Claude 3.5 Sonnet following
  closely. Gemini 1.5 Pro was significantly slower.
- **Tokens**: Gemini 1.5 Pro produced the highest token output, often reaching its 8K limit. ChatGPT-4o latest and
  Claude 3.5 Sonnet produced similar amounts, while GPT-4o generated the least.
- **Token/Second**: Claude 3.5 Sonnet, ChatGPT-4o latest, and GPT-4o demonstrated similar, high processing speeds.
  Gemini 1.5 Pro lagged behind significantly.
- **Score**: ChatGPT-4o latest achieved the highest score, followed by Claude 3.5 Sonnet. Gemini 1.5 Pro and GPT-4o were
  close behind, with GPT-4o ranking last in this test.

### Calculated Scores for Code Documentation Experiment

| Model                       | AVG Accuracy | AVG Completeness | AVG Time   | AVG Token output | AVG Tokens/Second | Score      |
|-----------------------------|--------------|------------------|------------|------------------|-------------------|------------|
| Claude 3.5 Sonnet           | **3.508**    | 3.430            | 13.566     | 952.222          | 70.191            | 0.8798     |
| GPT-4o (2024-08-06)         | 3.218        | 3.480            | **12.005** | 869.000          | 72.387            | 0.8585     |
| Gemini 1.5 Pro (2024-08-01) | 3.433        | 2.935            | 19.488     | 908.278          | 46.608            | 0.7939     |
| **ChatGPT-4o latest**       | 3.276        | **3.872**        | 21.877     | **1785.444**     | **81.614**        | **0.9148** |

- **Accuracy**: Claude 3.5 Sonnet showed the highest accuracy, followed closely by Gemini 1.5 Pro. ChatGPT-4o latest and
  GPT-4o had slightly lower but similar accuracy scores.
- **Completeness**: ChatGPT-4o latest significantly outperformed the other models in completeness, with GPT-4o and
  Claude 3.5 Sonnet showing similar, good results. Gemini 1.5 Pro lagged behind in this aspect.
- **Time**: GPT-4o maintained its position as the fastest model, followed closely by Claude 3.5 Sonnet. ChatGPT-4o
  latest and Gemini 1.5 Pro took significantly longer to process.
- **Tokens**: ChatGPT-4o latest produced nearly twice as many tokens as the other models, which all had similar output
  levels.
- **Token/Second**: ChatGPT-4o latest showed the highest token processing speed, followed closely by GPT-4o and Claude
  3.5 Sonnet. Gemini 1.5 Pro processed tokens at a notably slower rate.
- **Score**: ChatGPT-4o latest achieved the highest overall score, with Claude 3.5 Sonnet in second place. GPT-4o ranked
  third, and Gemini 1.5 Pro, while still performing well, ranked last in this comparison.

### Calculated Scores for Large Context Instructions Following

| Model                       | AVG Accuracy | AVG Completeness | Score  |
|-----------------------------|--------------|------------------|--------|
| **Claude 3.5 Sonnet**       | 4            | 4                | 1      |
| GPT-4o (2024-08-06)         | 3.5          | 4                | 0.9375 |
| Gemini 1.5 Pro (2024-08-01) | 3            | 3.5              | 0.8125 |
| ChatGPT-4o latest           | 4            | 3.5              | 0.9375 |

- Claude 3.5 Sonnet demonstrated the best performance, reaching the limit of our test. The model fully translated the
  application, utilized imports between files, and excluded unused code segments.

- GPT-4o also showed very good results, translating all functionality. However, in one task, a feature was not fully
  operational, and one function remained unused.

- Gemini 1.5 Pro omitted some functionality, did not utilize utilities or constants, and insufficiently separated the
  codebase. Nevertheless, all implemented features worked without errors, and the core functionality operated correctly.

- ChatGPT-4o latest completed the task perfectly, but missed one of the details in one of the tasks, for which the
  completeness score was reduced

## Final scores

| Model                       | Code Translation | Generation | Document  | Context | Total Score |
|-----------------------------|------------------|------------|-----------|---------|-------------|
| **Claude 3.5 Sonnet**       | **0.957**        | 0.830      | 0.880     | **1**   | **0.917**   |
| GPT-4o (2024-08-06)         | 0.892            | 0.787      | 0.858     | 0.875   | 0.853       |
| Gemini 1.5 Pro (2024-08-01) | 0.833            | 0.796      | 0.794     | 0.8125  | 0.809       |
| **ChatGPT-4o latest**       | **0.959**        | **0.865**  | **0.915** | 0.9375  | **0.919**   |

## Conclusion

Our comprehensive evaluation of four leading AI models - Claude 3.5 Sonnet, GPT-4o (2024-08-06), Gemini 1.5 Pro (
2024-08-01), and ChatGPT-4o latest - has revealed fascinating insights into their respective capabilities and
performance across various software engineering tasks.

**ChatGPT-4o latest** emerged as the overall leader, demonstrating exceptional performance across all evaluated aspects.
It consistently outperformed its competitors in code translation, generation, documentation, and instructions following tasks. This model's ability to balance high accuracy with impressive completeness scores, coupled with
efficient processing speeds, positions it as a top choice for advanced language processing and software engineering
applications.

**Claude 3.5 Sonnet** closely followed ChatGPT-4o latest, showcasing high performance and consistency across all tasks.
It particularly excelled in instructions following, achieving perfect scores

<p style="text-align: center;">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0<br/>
</p>