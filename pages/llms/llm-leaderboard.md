# LLMs Leaderboard (Benchmark v2, last update 2025-06-12)

![llm-rating.png](/images/llms/llm-rating.png)

## Introduction to EPAM AI/RUN LLMs Engineering Benchmark

This page presents the results of LLMs engineering benchmark including a leaderboard that compares the effectiveness of Anthropic, Amazon, Google DeepMind, Meta, xAI, OpenAI, and other companies'
LLMs (Large Language Models)and SMLs (Small Language Models) in executing software engineering tasks, including code translation, code generation, documentation generation, and large context
instruction following (LCIF).

This leaderboard will be updated regularly to reflect the latest developments in the field of large language models.

> Previous benchmark v1 results were moved to [llm-leaderboard-v1.md](benchmark_v1/llm-leaderboard_v1.md) for reference.

## Benchmark Key Findings

General insights:

- Gemini 2.5 Flash Preview (05-20) dominates with 95.99% total score, fastest token generation (208.25 tokens/sec), and cost-effective performance ($1.09 total cost)
- Codex Mini Latest (specialized OpenAI coding model) achieves 93.48% with the highest accuracy (3.993) but shows refusal behaviors in some scenarios, often declining to execute tasks with responses
  like "I'm sorry I can't answer that" or claiming lack of necessary tools despite having repository access
- Gemini 2.5 Pro Preview models show interesting performance variation: 05-06 version reaches 92.75% but at higher cost ($3.46), while newer 06-05 version scores lower (91.17%) with reduced token
  generation, suggesting Google's optimization for cost over raw performance
- Claude 4 Sonnet leads Anthropic models at 92.19%, notably outperforming its Thinking mode variant (91.32%)
- Anthropic Claude 4 models has the most recent [knowledge cutoff date](#models-specification) - March 2025
- OpenAI o3 (high) achieves 92.02% with exceptional speed (128.14 tokens/sec) and short execution time (13.06 min)
- Grok 3 mini beta demonstrates excellent value at 91.68% score for just $0.13 total cost
- GPT-4.1 nano shows remarkable speed with the fastest execution time (3.84 min) and 204.22 tokens/sec generation
- Open-source alternatives show promise: Gemma 3 family (27B leads at 55.87%) and Phi-4 (47.83%) provide self-hosted options

Performance metrics highlights:

- **Fastest token generation**: Gemini 2.5 Flash Preview (05-20) (208.25 tokens/sec), GPT-4.1 nano (204.22 tokens/sec), Grok 3 mini beta (152.47 tokens/sec)
- **Shortest execution time**: GPT-4.1 nano (3.84 min), Llama 4 Maverick (6.48 min), ChatGPT-4o (6.53 min)
- **Most tokens generated**: Gemini 2.5 Flash Preview (05-20) (306,543 tokens), Gemini 2.5 Pro Preview (05-06) (334,178 tokens), Grok 3 mini beta (220,054 tokens)
- **Best cost-effectiveness**: Grok 3 mini beta (91.68% score, $0.13 total), GPT-4.1 nano (72.79% score, $0.02 total), Llama 4 Maverick (72.97% score, $0.05 total)

Best results by category:

- **Code Translation**: Gemini 2.5 Flash Preview (05-20) (95.09%), Claude 4 Sonnet (90.88%), Claude 4 Opus Thinking (89.62%)
- **Code Generation**: Gemini 2.5 Flash Preview (05-20) (95.05%), Claude 4 Sonnet (92.75%), Claude 4 Opus Thinking (92.56%)
- **Code Documentation**: Gemini 2.5 Flash Preview (05-20) (93.80%), OpenAI o3 high (91.53%), Codex Mini Latest (91.05%)
- **LCIF**: 14 models achieved perfect 100% scores including all major providers

## Additional Views

![llm-type.png](/images/llms/llm-type.png)
![llm-price.png](/images/llms/llm-price.png)
![llm-tokens.png](/images/llms/llm-tokens.png)
![llm-cost.png](/images/llms/llm-cost.png)
![llm-time.png](/images/llms/llm-time.png)
![llm-speed.png](/images/llms/llm-speed.png)

<details>
<summary>Details</summary>

### Observations

The benchmark results presented here are based on the latest LLMs engineering benchmark conducted by EPAM AI/RUN. The benchmark evaluates the performance of various LLMs in executing software
When examining the benchmark results, it's recommended to focus not only on the scores but also on metrics such as token generation speed, experiment execution time, the number of generated tokens,
and the final cost of the experiment.

The current benchmark leader, Gemini 2.5 Flash Preview (05-20), a thinking model from Google, demonstrates excellent results in both speed and code generation quality. The model generated 306,543
tokens at a generation speed of 208.25 tokens/second. The experiment cost $1.09, which is relatively inexpensive considering the 300,000 generated tokens. This makes it an excellent choice for
engineering tasks requiring high performance and quality.

Second place is held by Codex Mini Latest, an OpenAI model that is a fine-tuned version of o4-mini specifically designed for use in Codex CLI. It achieved the highest accuracy score (3.993).
It's worth noting that some benchmark scenarios had to be rerun, as the model would respond to tasks with answers like: "I'm sorry I can't answer that" or "I'm sorry, but I can't proceed without
access
to the repository's files."

Third place is occupied by Gemini 2.5 Pro Preview (05-06), the previous version of the current Gemini 2.5 Pro Preview (06-05). Both are thinking models from Google. Interestingly, the 06-05 version
showed lower results compared to 05-06, and we can observe that this newer model generated half the number of tokens at the same speed. It can be assumed that before release, the model was limited in
token generation, which affected code generation quality but reduced the total experiment cost (from $3.46 to $1.88).

Further in the ranking are Anthropic's models, Claude 4 Sonnet and Claude 4 Opus. Interestingly, Claude 4 Sonnet with thinking mode disabled showed higher results compared to Claude 4 Opus and Sonnet
in thinking mode. This suggests that thinking mode doesn't always provide improvement in code generation quality and can sometimes even worsen results by reducing the number of valuable generated
tokens.

Grok 3 mini beta from xAI, which is a reasoning model, showed results higher than Grok 3 beta, which is not a reasoning model. Here we see that a mini model with reasoning capabilities
outperforms a full model without reasoning capabilities.

DeepSeek models have not yet shown high results in the benchmark, with the latest model almost reaching 85%. It's worth noting that the model follows instructions very poorly. In the LCIF experiment,
the model failed to sequentially read each repository file and update it. Instead, it would read 3-4 files out of 8 and try to convert the application prematurely.

Recently, new open-source models have been added to our leaderboard, which are self-hosted and can be used in production. These models include Gemma 3 27B, Gemma 3 12B Q4, Phi 4, Gemma 3 4B, and Gemma
3 1B. These models are particularly noteworthy as they can be self-hosted within organizations seeking privacy, control, and cost optimization. This represents a significant advancement in the
open-source LLM space.

### Detailed Results

All categories, except Large Context Instructions Following (LCIF), are evaluated automatically using the Large Language Model<sup>1</sup>.
You can read [llm-comparison-report.md](llm-comparison-report.md) for a detailed comparison of the models. The report includes all experiment scores, the performance of each model in different
categories, and the final scores.

The table below provides an overview of the experiment, encompassing three categories. Here, you can review the average accuracy and completeness across all categories, total execution time,
generation token speed (token per second), the total number of input and output tokens, the cost of the experiment, and finally, the total score. The total score comprises the average score across all
categories **including** LCIF experiment score.

| Name                             | Reasoning    | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total output | Cost $ | Total Score |
|----------------------------------|--------------|----------|--------------|------------------|-------------|-------------|--------------|--------|-------------|
| Gemini 2.5 Flash Preview (05-20) | Yes          | 3.957    | 3.945        | 24.53            | 208.25      | 92766       | 306543       | 1.09   | 95.99%      |
| Codex Mini Latest                | Yes (high)   | 3.993    | 3.708        | 20.28            | 138.98      | 80551       | 169109       | 1.14   | 93.48%      |
| Gemini 2.5 Pro Preview (05-06)   | Yes          | 3.941    | 3.851        | 58.05            | 95.95       | 92745       | 334178       | 3.46   | 92.75%      |
| Claude 4 Sonnet                  | No           | 3.888    | 3.773        | 22.11            | 96.52       | 100015      | 128012       | 2.22   | 92.19%      |
| OpenAI o3 (high) (04-16)         | Yes (high)   | 3.955    | 3.598        | 13.06            | 128.14      | 80551       | 100372       | 4.82   | 92.02%      |
| Grok 3 mini beta (high)          | Yes (high)   | 3.891    | 3.690        | 24.05            | 152.47      | 80100       | 220054       | 0.13   | 91.68%      |
| Claude 4 Sonnet (Thinking)       | Yes          | 3.913    | 3.704        | 28.48            | 86.51       | 100711      | 147800       | 2.52   | 91.32%      |
| Gemini 2.5 Pro Preview (06-05)   | Yes          | 3.898    | 3.675        | 30.61            | 96.09       | 92745       | 176493       | 1.88   | 91.17%      |
| Claude 4 Opus (Thinking)         | Yes          | 3.766    | 3.775        | 25.03            | 89.44       | 100711      | 134301       | 11.58  | 91.01%      |
| Claude 3.7 Sonnet                | No           | 3.819    | 3.756        | 24.60            | 76.31       | 100002      | 112605       | 1.99   | 90.89%      |
| OpenAI o4-mini (high) (04-16)    | Yes (high)   | 3.889    | 3.579        | 25.84            | 104.17      | 80551       | 161478       | 0.80   | 90.49%      |
| OpenAI o3-mini (medium) (01-31)  | Yes (medium) | 3.818    | 3.488        | 13.13            | 117.30      | 80551       | 92403        | 0.50   | 89.90%      |
| Claude 3.7 Sonnet (Thinking)     | Yes          | 3.778    | 3.683        | 42.16            | 79.27       | 100711      | 200502       | 3.31   | 89.85%      |
| GPT-4.1 mini (04-14)             | No           | 3.929    | 3.572        | 20.86            | 61.08       | 80575       | 76452        | 0.15   | 88.83%      |
| Grok 3 Beta                      | No           | 3.763    | 3.456        | 13.85            | 81.24       | 80076       | 67531        | 1.25   | 88.61%      |
| GPT-4.1 (04-14)                  | No           | 3.766    | 3.514        | 24.40            | 48.17       | 80575       | 70541        | 0.73   | 88.10%      |
| ChatGPT-4o                       | No           | 3.647    | 3.290        | 6.53             | 123.85      | 80575       | 48506        | 1.13   | 86.33%      |
| DeepSeek R1 (05-28)              | Yes          | 3.633    | 3.349        | 19.91            | 110.39      | 82977       | 131840       | 0.64   | 84.14%      |
| OpenAI o1 (medium) (12-17)       | Yes (medium) | 3.706    | 3.187        | 27.09            | 54.32       | 80551       | 88289        | 6.51   | 84.13%      |
| DeepSeek V3 (03-24)              | No           | 3.619    | 3.440        | 28.65            | 35.38       | 82977       | 60811        | 0.17   | 83.51%      |
| GPT-4.5 preview                  | No           | 3.613    | 2.873        | 73.49            | 8.59        | 80575       | 37894        | 11.73  | 77.47%      |
| DeepSeek R1                      | Yes          | 3.473    | 3.041        | 21.32            | 68.63       | 82977       | 87785        | 0.95   | 76.51%      |
| Llama 4 Maverick                 | No           | 3.165    | 2.494        | 6.48             | 103.21      | 80493       | 40144        | 0.05   | 72.97%      |
| GPT-4.1 nano (04-14)             | No           | 3.483    | 2.853        | 3.84             | 204.22      | 80575       | 47043        | 0.02   | 72.79%      |
| Amazon Nova Premier              | No           | 3.145    | 1.999        | 9.88             | 48.73       | 99511       | 28896        | 0.61   | 61.49%      |
| Amazon Nova Pro                  | No           | 2.998    | 2.165        | 7.77             | 81.32       | 88588       | 37918        | 0.19   | 60.56%      |
| Gemma 3 27B                      | No           | 2.911    | 2.218        | 16.84            | 45.44       | 73619       | 45925        | 0.00   | 55.87%      |
| Gemma 3 12B Q4                   | No           | 3.181    | 2.578        | 40.60            | 20.60       | 93835       | 50194        | 0.00   | 48.56%      |
| Phi 4 14.7B                      | No           | 3.101    | 2.196        | 6.69             | 80.29       | 79109       | 32213        | 0.00   | 47.83%      |
| Gemma 3 4B                       | No           | 2.135    | 1.659        | 23.89            | 27.63       | 86748       | 39596        | 0.00   | 32.61%      |
| Gemma 3 1B                       | No           | 1.068    | 1.128        | 8.52             | 84.82       | 93233       | 43344        | 0.00   | 21.24%      |

_Table 1. Overview of the experiment results._

> Additional info:  
> Evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the OpenAI o3-mini and Claude Sonnet 3.7 models.
> Please refer to the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.

</details>

## Models specification

| LLM Name                                                                                                                                                 | API Provider used in benchmark                                                           | Context Window                       | Cost (Input / Output per MTok)                  | Max Output         | Knowledge Cutoff |
|----------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|--------------------------------------|-------------------------------------------------|--------------------|------------------|
| [Gemini 2.5 Flash Preview (05-20)](https://ai.google.dev/gemini-api/docs/models#gemini-2.5-flash-preview)                                                | Google AI Studio                                                                         | 1M                                   | $0.15 / $3.50                                   | 65K                | Jan, 2025        |
| [Codex Mini Latest (o4-mini)](https://platform.openai.com/docs/models/codex-mini-latest)                                                                 | OpenAI                                                                                   | 200K                                 | $1.50 / $6.00                                   | 100K               | Jun 01, 2024     |
| [Gemini 2.5 Pro Preview (05-06)](https://blog.google/products/gemini/gemini-2-5-pro-updates/)                                                            | Google AI Studio                                                                         | 1M                                   | $1.25 / $10.00 <= 200k<br>$2.50 / $15.00 > 200k | 65K                | Jan, 2025        |
| [Gemini 2.5 Pro Preview (06-05)](https://blog.google/products/gemini/gemini-2-5-pro-latest-preview/)                                                     | Google AI Studio                                                                         | 1M                                   | $1.25 / $10.00 <= 200k<br>$2.50 / $15.00 > 200k | 65K                | Jan, 2025        |
| [Claude 4 Sonnet](https://www.anthropic.com/news/claude-4)                                                                                               | Google Vertex AI                                                                         | 200K                                 | $3.00 / $15.00                                  | 64K                | Mar, 2025        |
| [OpenAI o3 (04-16)](https://platform.openai.com/docs/models/o3)                                                                                          | OpenAI                                                                                   | 200K                                 | $10.00 / $40.00                                 | 100K               | Jun 01, 2024     |
| [Grok 3 mini beta](https://docs.x.ai/docs/models)                                                                                                        | xAI Console                                                                              | 131K                                 | $0.30 / $0.50                                   | 131K               | 17th Nov, 2024   |
| [Claude 4 Opus](https://www.anthropic.com/news/claude-4)                                                                                                 | Google Vertex AI                                                                         | 200K                                 | $15.00 / $75.00                                 | 32K                | Mar, 2025        |
| [Claude 3.7 Sonnet](https://www.anthropic.com/news/claude-3-7-sonnet)                                                                                    | Google Vertex AI                                                                         | 200K                                 | $3.00 / $15.00                                  | 8K                 | Nov, 2024        |
| [OpenAI o4-mini (04-16)](https://platform.openai.com/docs/models/o4-mini)                                                                                | OpenAI                                                                                   | 200K                                 | $1.10 / $4.40                                   | 100K               | Jun 01, 2024     |
| [OpenAI o3-mini (01-31)](https://platform.openai.com/docs/models/o3-mini)                                                                                | OpenAI                                                                                   | 200K                                 | $1.10 / $4.40                                   | 100K               | Up to Oct 2023   |
| [Claude 3.7 Sonnet (Thinking mode)](https://www.anthropic.com/news/claude-3-7-sonnet)                                                                    | Google Vertex AI                                                                         | 200K                                 | $3.00 / $15.00                                  | 64K (128K in beta) | Nov, 2024        |
| [GPT-4.1 mini (04-14)](https://platform.openai.com/docs/models/gpt-4.1-mini)                                                                             | OpenAI                                                                                   | 1M                                   | $0.40 / $1.60                                   | 32K                | Jun 01, 2024     |
| [Grok 3 beta](https://docs.x.ai/docs/models)                                                                                                             | xAI Console                                                                              | 131K                                 | $3.00 / $15.00                                  | 131K               | 17th Nov, 2024   |
| [GPT-4.1 (04-14)](https://platform.openai.com/docs/models/gpt-4.1)                                                                                       | OpenAI                                                                                   | 1M                                   | $2.00 / $8.00                                   | 32K                | Jun 01, 2024     |
| [ChatGPT-4o Latest (2025-03-26)](https://platform.openai.com/docs/models/chatgpt-4o-latest)                                                              | OpenAI                                                                                   | 128K                                 | $5.00 / $15.00                                  | 16K                | Up to Oct 2023   |
| [DeepSeek R1 (05-28)](https://api-docs.deepseek.com/news/news250528)                                                                                     | [Fireworks AI](https://fireworks.ai/models/fireworks/deepseek-r1-0528)                   | 160K                                 | $3.00 / $8.00                                   | 16K                | April, 2024      |
| [OpenAI o1 (12-17)](https://platform.openai.com/docs/models/o1)                                                                                          | OpenAI                                                                                   | 200K                                 | $15.00 / $60.00                                 | 100K               | Up to Oct 2023   |
| [DeepSeek V3 (03-24)](https://api-docs.deepseek.com/news/news250325)                                                                                     | [Fireworks AI](https://fireworks.ai/models/fireworks/deepseek-v3-0324)                   | 64K                                  | $1.20 / $1.20                                   | 8K                 | Up to Oct 2023   |
| [DeepSeek R1](https://fireworks.ai/models/fireworks/deepseek-r1)                                                                                         | [Fireworks AI](https://fireworks.ai/models/fireworks/deepseek-r1)                        | 64K                                  | $3.00 / $8.00                                   | 8K                 | Up to Oct 2023   |
| [GPT-4.5 Preview](https://openai.com/index/introducing-gpt-4-5/)                                                                                         | OpenAI                                                                                   | 128K                                 | $75.00 / $150.00                                | 16K                | Up to Oct 2023   |
| [OpenAI o1-Pro](https://platform.openai.com/docs/models/o1-pro)                                                                                          | OpenAI                                                                                   | 200K                                 | $150.00 / $600.00                               | 100K               | Up to Oct 2023   |
| [Llama 4 Maverick](https://ai.meta.com/blog/llama-4-multimodal-intelligence)                                                                             | [Fireworks AI](https://app.fireworks.ai/models/fireworks/llama4-maverick-instruct-basic) | 1M                                   | $0.05 / $0.22                                   | 131K               | Aug, 2024        |
| [GPT-4.1 nano](https://openai.com/index/gpt-4-1/)                                                                                                        | OpenAI                                                                                   | 1M                                   | $0.025 / $0.4                                   | 32K                | June, 2024       |
| [Amazon Nova Premier](https://aws.amazon.com/blogs/aws/amazon-nova-premier-our-most-capable-model-for-complex-tasks-and-teacher-for-model-distillation/) | AWS Bedrock                                                                              | 1M                                   | $2.5 / $12.5                                    | 10K                | N/A              |
| [Amazon Nova Pro](https://aws.amazon.com/ai/generative-ai/nova/)                                                                                         | AWS Bedrock                                                                              | 300K                                 | $0.80 / $3.20                                   | 10K                | October, 2023    |
| [Gemma 3 (1B, 4B, 12B, 27B)](https://ai.google.dev/gemma)                                                                                                | Locally hosted                                                                           | 128K max, 32K used during evaluation | $0.00 / $0.00                                   | N/A                | August, 2024     |
| [Phi 4 14.7B](https://huggingface.co/microsoft/phi-4)                                                                                                    | Locally hosted                                                                           | 16K                                  | $0.00 / $0.00                                   | N/A                | June, 2024       |

_Table 2. Description of LLMs, their versions, amount of information to process, and the length of the response._

## Notes

- To learn more about our methodology for evaluating LLMs, please read [LLMs Benchmark Approach](llm-approach.md).
- To submit your model for evaluation, please refer to the [Large Language Model Benchmark Submission](submissions/llm-benchmark-submission.md) page.
- Previous charts with ratings and other scores can be found in the [LLMs Charts archive](/images/llms/llm-charts-archive).

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>