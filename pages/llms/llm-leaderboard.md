# LLMs Leaderboard (Benchmark v2, last update 2025-08-12)

![llm-rating.png](/images/llms/llm-rating.png)

## Introduction to EPAM AI/RUN LLMs Engineering Benchmark

This page presents the results of LLMs engineering benchmark including a leaderboard that compares the effectiveness of Anthropic, Amazon, Google DeepMind, Meta, xAI, OpenAI, and other companies'
LLMs (Large Language Models)and SMLs (Small Language Models) in executing software engineering tasks, including code translation, code generation, documentation generation, and large context
instruction following (LCIF).

This leaderboard will be updated regularly to reflect the latest developments in the field of large language models.

> Starting from 2025-08-12 we changed the scoring formula to better reflect the performance of LLMs in engineering tasks. The new formula is based only on the average of accuracy and completeness
> scores across all categories, including LCIF experiment score. Previous benchmark results were calculated as the 45% weight of accuracy, 45% weight of completeness, and 5% of the fastest execution
> time and 5% of the fastest token generation speed.
<details>
<summary>Scores calculated with previous formula that takes into account speed</summary>

![llm-previous-rating.png](/images/llms/llm-previous-rating.png)

</details>

> Earlier benchmark v1 results were moved to [llm-leaderboard-v1.md](benchmark_v1/llm-leaderboard_v1.md) for reference.

## Benchmark Key Findings

General insights:

- GPT-5 (08-07) leads the benchmark with 99.46% total score, achieving perfect 100% in code translation and excellent performance across all categories ($1.36 total cost)
- Gemini 2.5 Flash Preview (05-20) follows closely at 99.13% with very fast token generation (208.25 tokens/sec) and cost-effective performance ($1.09 total cost)
- Gemini 2.5 Pro Preview models show interesting performance variation: 05-06 version reaches 98.10% but at higher cost ($3.46), while newer 06-05 version scores lower (96.12%) with reduced token
  generation, suggesting Google's optimization for cost over raw performance
- Grok 4 (07-09) achieves strong performance at 97.39% with balanced capabilities across all categories, but suffers from slow generation speed (42.03 tokens/sec) that makes it less
  suitable for interactive development workflows despite reasonable cost efficiency ($2.07)
- Codex Mini Latest (specialized OpenAI coding model) achieves 97.34% with the highest accuracy (3.993) but shows refusal behaviors in some scenarios, often declining to execute tasks with responses
  like "I'm sorry I can't answer that" or claiming lack of necessary tools despite having repository access
- Claude 4 Sonnet leads Anthropic models at 97.02%, notably outperforming its Thinking mode variant (96.43%)
- Anthropic Claude 4 models has the most recent [knowledge cutoff date](#models-specification) - March 2025
- gpt-oss-120b open-weight model demonstrates exceptional speed with 1,144.30 tokens/sec generation with [Cerebras](https://www.cerebras.ai/) provider and completes all tasks in just **1.53 min**,
  achieving 95.81% score at ultra-low cost ($0.09)
- Grok 3 mini beta demonstrates excellent value at 95.35% score for just $0.13 total cost
- GPT-4.1 nano shows remarkable speed with the fastest execution time (3.84 min) and 204.22 tokens/sec generation, though scoring 71.37%
- Small open-source alternatives show promise: Gemma 3 family (27B leads at 58.99%) and Phi-4 (49.08%) provide self-hosted options

Performance metrics highlights:

- **Fastest token generation**: gpt-oss-120b (1,144.30 tokens/sec), Gemini 2.5 Flash Preview (05-20) (208.25 tokens/sec), GPT-4.1 nano (204.22 tokens/sec)
- **Shortest execution time**: gpt-oss-120b (1.53 min), GPT-4.1 nano (3.84 min), Llama 4 Maverick (6.48 min)
- **Most tokens generated**: Gemini 2.5 Pro Preview (05-06) (334,178 tokens), Gemini 2.5 Flash Preview (05-20) (306,543 tokens), Grok 3 mini beta (220,054 tokens)
- **Best cost-effectiveness**: gpt-oss-120b (95.81% score, $0.09 total), Llama 4 Maverick (74.21% score, $0.05 total), GPT-4.1 nano (71.37% score, $0.02 total)

Best results by category:

- **Code Translation**: GPT-5 (08-07) (100.00%), Codex Mini Latest (99.75%), Gemini 2.5 Flash Preview (05-20) (99.45%)
- **Code Generation**: Claude 4 Sonnet (99.98%), Claude 4 Opus (Thinking) (99.97%), Gemini 2.5 Flash Preview (05-20) (99.39%)
- **Code Documentation**: GPT-5 (08-07) (98.61%), Gemini 2.5 Flash Preview (05-20) (97.69%), gpt-oss-120b (96.90%)
- **LCIF**: models from all major providers achieved 100% in this category

## Additional Views

![llm-type.png](/images/llms/llm-type.png)
![llm-type.png](/images/llms/llm-is_commercial.png)
![llm-price.png](/images/llms/llm-price.png)
![llm-tokens.png](/images/llms/llm-tokens.png)
![llm-cost.png](/images/llms/llm-cost.png)
![llm-time.png](/images/llms/llm-time.png)
![llm-speed.png](/images/llms/llm-speed.png)

<details>
<summary>Detailed Results and Observations</summary>

### Observations

The benchmark results presented here are based on the latest LLMs engineering benchmark conducted by EPAM AI/RUN. The benchmark evaluates the performance of various LLMs in executing software
When examining the benchmark results, it's recommended to focus not only on the scores but also on metrics such as token generation speed, experiment execution time, the number of generated tokens,
and the final cost of the experiment.

The current benchmark leader, GPT-5 (08-07) by OpenAI, achieves exceptional results with 99.46% total score, being the first model to reach perfect 100% in code translation. The model generated
125,778 tokens with moderate speed (41.28 tokens/second) over 50.78 minutes, costing $1.36. GPT-5 demonstrates the highest accuracy (4.000) and excellent completeness (3.938), making it an outstanding
choice for engineering tasks requiring maximum precision and quality. Based on our observations, GPT-5 performs better when using low reasoning mode rather than high reasoning, and we configured
verbosity to high for generating more comprehensive code.

Second place is held by Gemini 2.5 Flash Preview (05-20), a thinking model by Google, scoring 99.13% with excellent speed and cost efficiency. The model generated 306,543 tokens at a generation speed
of 208.25 tokens/second. The experiment cost $1.09, which is relatively inexpensive considering the 300,000 generated tokens. This combination of high performance, speed, and cost-effectiveness makes
it an excellent choice for high-volume engineering tasks.

Third place is occupied by Gemini 2.5 Pro Preview (05-06), the earlier version of Google's Pro model, achieving 98.10%. While more expensive ($3.46) and slower (95.95 tokens/second), this version
generated the most tokens overall (334,178) and maintains high quality. Interestingly, the newer 06-05 version scored lower (96.12%) despite generating fewer tokens (176,493) at similar speed,
suggesting Google optimized for cost efficiency over raw performance in the update.

Fifth place is held by Codex Mini Latest, an OpenAI model that is a fine-tuned version of o4-mini specifically designed for use in Codex CLI. It achieved the highest accuracy score (3.993) among all
models. However, some benchmark scenarios had to be rerun, as the model would respond to tasks with answers like: "I'm sorry I can't answer that" or "I'm sorry, but I can't proceed without access to
the repository's files."

Further in the ranking are Anthropic's models, Claude 4 Sonnet and Claude 4 Opus. Interestingly, Claude 4 Sonnet with thinking mode disabled showed higher results compared to Claude 4 Opus and Sonnet
in thinking mode. This suggests that thinking mode doesn't always provide improvement in code generation quality and can sometimes even worsen results by reducing the number of valuable generated
tokens. Claude 4.1 Opus was also run without reasoning mode, as our tests show that Anthropic models generate better code without reasoning when the task is clearly defined and only requires code
rewriting.

Grok 3 mini beta from xAI, which is a reasoning model, showed results higher than Grok 3 beta, which is not a reasoning model. Here we see that a mini model with reasoning capabilities
outperforms a full model without reasoning capabilities.

DeepSeek models have not yet shown high results in the benchmark, with the latest model almost reaching 85%. It's worth noting that the model follows instructions very poorly. In the LCIF experiment,
the model failed to sequentially read each repository file and update it. Instead, it would read 3-4 files out of 8 and try to convert the application prematurely.

A remarkable breakthrough came with gpt-oss-120b, the new open-source OpenAI model. We chose to use Cerebras as the provider since they offered speeds of 3-5k tokens per second, which is more than 10
times faster than typical model speeds. This model completed ALL benchmark tasks in just 1.5 minutes, while other models typically take 20-30 minutes. Moreover, this is the first open-source model to
achieve a score above 95% (95.81%).

Recently, new open-source models have been added to our leaderboard, which are self-hosted and can be used in production. These models include Gemma 3 27B, Gemma 3 12B Q4, Phi 4, Gemma 3 4B, and Gemma
3 1B. These models are particularly noteworthy as they can be self-hosted within organizations seeking privacy, control, and cost optimization. This represents a significant advancement in the
open-source LLM space.

### Detailed Results

All categories, except Large Context Instructions Following (LCIF), are evaluated automatically using the Large Language Model<sup>1</sup>.
You can read [llm-comparison-report.md](llm-comparison-report.md) for a detailed comparison of the models. The report includes all experiment scores, the performance of each model in different
categories, and the final scores. Maximum score of accuracy and completeness is 4.0 and total score is calculated as the average of accuracy and completeness scores across all categories

The table below provides an overview of the experiment, encompassing three categories. Here, you can review the average accuracy and completeness across all categories, total execution time,
generation token speed (token per second), the total number of input and output tokens, the cost of the experiment, and finally, the total score. The total score comprises the average score across all
categories **including** LCIF experiment score.

| Name                             | Reasoning    | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total output | Cost $ | Total Score |
|----------------------------------|--------------|----------|--------------|------------------|-------------|-------------|--------------|--------|-------------|
| GPT-5 (08-07)                    | Yes (low)    | 4.000    | 3.938        | 50.78            | 41.28       | 80575       | 125778       | 1.36   | 99.46%      |
| Gemini 2.5 Flash Preview (05-20) | Yes          | 3.957    | 3.945        | 24.53            | 208.25      | 92766       | 306543       | 1.09   | 99.13%      |
| Gemini 2.5 Pro Preview (05-06)   | Yes          | 3.941    | 3.851        | 58.05            | 95.95       | 92745       | 334178       | 3.46   | 98.10%      |
| Grok 4 (07-09)                   | Yes          | 3.918    | 3.801        | 48.32            | 42.03       | 80121       | 121850       | 2.07   | 97.39%      |
| Codex Mini Latest                | Yes (high)   | 3.993    | 3.708        | 20.28            | 138.98      | 80551       | 169109       | 1.14   | 97.34%      |
| Claude 4 Sonnet                  | No           | 3.888    | 3.773        | 22.11            | 96.52       | 100015      | 128012       | 2.22   | 97.02%      |
| Claude 4.1 Opus                  | No           | 3.894    | 3.765        | 42.82            | 55.51       | 100051      | 142620       | 12.20  | 96.85%      |
| Claude 4 Sonnet (Thinking)       | Yes          | 3.913    | 3.704        | 28.48            | 86.51       | 100711      | 147800       | 2.52   | 96.43%      |
| Gemini 2.5 Pro (06-05)           | Yes          | 3.898    | 3.675        | 30.61            | 96.09       | 92745       | 176493       | 1.88   | 96.12%      |
| Claude 3.7 Sonnet                | No           | 3.819    | 3.756        | 24.60            | 76.31       | 100002      | 112605       | 1.99   | 96.07%      |
| Claude 4 Opus (Thinking)         | Yes          | 3.766    | 3.775        | 25.03            | 89.44       | 100711      | 134301       | 11.58  | 95.95%      |
| gpt-oss-120b                     | Yes (low)    | 3.914    | 3.812        | 1.53             | 1144.30     | 82111       | 105138       | 0.09   | 95.81%      |
| OpenAI o3-pro (high) (06-10)     | Yes (high)   | 3.934    | 3.612        | 110.34           | 13.90       | 80551       | 92049        | 8.97   | 95.77%      |
| OpenAI o3 (high) (04-16)         | Yes (high)   | 3.955    | 3.598        | 13.06            | 128.14      | 80551       | 100372       | 4.82   | 95.69%      |
| Grok 3 mini beta (high)          | Yes (high)   | 3.891    | 3.690        | 24.05            | 152.47      | 80100       | 220054       | 0.13   | 95.35%      |
| Claude 3.7 Sonnet (Thinking)     | Yes          | 3.778    | 3.683        | 42.16            | 79.27       | 100711      | 200502       | 3.31   | 95.13%      |
| OpenAI o4-mini (high) (04-16)    | Yes (high)   | 3.889    | 3.579        | 25.84            | 104.17      | 80551       | 161478       | 0.80   | 94.96%      |
| GPT-4.1 mini (04-14)             | No           | 3.929    | 3.572        | 20.86            | 61.08       | 80575       | 76452        | 0.15   | 94.08%      |
| OpenAI o3-mini (medium) (01-31)  | Yes (medium) | 3.818    | 3.488        | 13.13            | 117.30      | 80551       | 92403        | 0.50   | 93.56%      |
| GPT-4.1 (04-14)                  | No           | 3.766    | 3.514        | 24.40            | 48.17       | 80575       | 70541        | 0.73   | 93.51%      |
| Grok 3 Beta                      | No           | 3.763    | 3.456        | 13.85            | 81.24       | 80076       | 67531        | 1.25   | 92.93%      |
| OpenAI o1 (medium) (12-17)       | Yes (medium) | 3.706    | 3.187        | 27.09            | 54.32       | 80551       | 88289        | 6.51   | 89.13%      |
| DeepSeek V3 (03-24)              | No           | 3.619    | 3.440        | 28.65            | 35.38       | 82977       | 60811        | 0.17   | 88.94%      |
| ChatGPT-4o                       | No           | 3.647    | 3.290        | 6.53             | 123.85      | 80575       | 48506        | 1.13   | 88.45%      |
| DeepSeek R1 (05-28)              | Yes          | 3.633    | 3.349        | 19.91            | 110.39      | 82977       | 131840       | 0.64   | 87.92%      |
| GPT-4.5 preview                  | No           | 3.613    | 2.873        | 73.49            | 8.59        | 80575       | 37894        | 11.73  | 83.16%      |
| DeepSeek R1                      | Yes          | 3.473    | 3.041        | 21.32            | 68.63       | 82977       | 87785        | 0.95   | 80.55%      |
| Llama 4 Maverick                 | No           | 3.165    | 2.494        | 6.48             | 103.21      | 80493       | 40144        | 0.05   | 74.21%      |
| GPT-4.1 nano (04-14)             | No           | 3.483    | 2.853        | 3.84             | 204.22      | 80575       | 47043        | 0.02   | 71.37%      |
| Amazon Nova Premier              | No           | 3.145    | 1.999        | 9.88             | 48.73       | 99511       | 28896        | 0.61   | 63.92%      |
| Amazon Nova Pro                  | No           | 2.998    | 2.165        | 7.77             | 81.32       | 88588       | 37918        | 0.19   | 62.04%      |
| Gemma 3 27B                      | No           | 2.911    | 2.218        | 16.84            | 45.44       | 73619       | 45925        | 0.00   | 58.99%      |
| Gemma 3 12B Q4                   | No           | 3.181    | 2.578        | 40.60            | 20.60       | 93835       | 50194        | 0.00   | 53.14%      |
| Phi 4 14.7B                      | No           | 3.101    | 2.196        | 6.69             | 80.29       | 79109       | 32213        | 0.00   | 49.08%      |
| Gemma 3 4B                       | No           | 2.135    | 1.659        | 23.89            | 27.63       | 86748       | 39596        | 0.00   | 34.99%      |
| Gemma 3 1B                       | No           | 1.068    | 1.128        | 8.52             | 84.82       | 93233       | 43344        | 0.00   | 19.98%      |

_Table 1. Overview of the experiment results._

> Additional info:  
> Evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the OpenAI o3-mini and Claude Sonnet 3.7 models.
> Please refer to the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.

</details>

## Models specification

| LLM Name                                                                                                                                                 | API Provider used in benchmark                                                           | Context Window                       | Cost (Input / Output per MTok)                   | Max Output         | Knowledge Cutoff |
|----------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|--------------------------------------|--------------------------------------------------|--------------------|------------------|
| [GPT-5 (08-07)](https://platform.openai.com/docs/models/gpt-5)                                                                                           | OpenAI                                                                                   | 400K                                 | $1.25 / $10.00                                   | 128K               | Sep 30, 2024     |
| [Gemini 2.5 Flash Preview (05-20)](https://ai.google.dev/gemini-api/docs/models#gemini-2.5-flash-preview)                                                | Google AI Studio                                                                         | 1M                                   | $0.15 / $3.50                                    | 65K                | Jan, 2025        |
| [Codex Mini Latest (o4-mini)](https://platform.openai.com/docs/models/codex-mini-latest)                                                                 | OpenAI                                                                                   | 200K                                 | $1.50 / $6.00                                    | 100K               | Jun 01, 2024     |
| [Gemini 2.5 Pro Preview (05-06)](https://blog.google/products/gemini/gemini-2-5-pro-updates/)                                                            | Google AI Studio                                                                         | 1M                                   | $1.25 / $10.00 <= 200K<br>$2.50 / $15.00 > 200K  | 65K                | Jan, 2025        |
| [Gemini 2.5 Pro Preview (06-05)](https://blog.google/products/gemini/gemini-2-5-pro-latest-preview/)                                                     | Google AI Studio                                                                         | 1M                                   | $1.25 / $10.00 <= 200K<br>$2.50 / $15.00 > 200K  | 65K                | Jan, 2025        |
| [Claude 4 Sonnet](https://www.anthropic.com/news/claude-4)                                                                                               | Google Vertex AI                                                                         | 200K                                 | $3.00 / $15.00                                   | 64K                | Mar, 2025        |
| [Claude 4.1 Opus](https://www.anthropic.com/news/claude-opus-4-1)                                                                                        | Google Vertex AI                                                                         | 200K                                 | $15.00 / $75.00                                  | 32K                | Mar, 2025        |
| [OpenAI o3 (04-16)](https://platform.openai.com/docs/models/o3)                                                                                          | OpenAI                                                                                   | 200K                                 | $10.00 / $40.00                                  | 100K               | Jun 01, 2024     |
| [Grok 4 (07-09)](https://docs.x.ai/docs/models/grok-4-0709)                                                                                              | xAI Console                                                                              | 256K                                 | $3.00 / $15.00 <= 128K and $6.00 / $30.00 > 128K | N/A                | N/A              |
| [Grok 3 mini beta](https://docs.x.ai/docs/models/grok-3-mini)                                                                                            | xAI Console                                                                              | 131K                                 | $0.30 / $0.50                                    | 131K               | 17th Nov, 2024   |
| [Claude 4 Opus](https://www.anthropic.com/news/claude-4)                                                                                                 | Google Vertex AI                                                                         | 200K                                 | $15.00 / $75.00                                  | 32K                | Mar, 2025        |
| [Claude 3.7 Sonnet](https://www.anthropic.com/news/claude-3-7-sonnet)                                                                                    | Google Vertex AI                                                                         | 200K                                 | $3.00 / $15.00                                   | 8K                 | Nov, 2024        |
| [gpt-oss-120b](https://platform.openai.com/docs/models/gpt-oss-120b)                                                                                     | [Cerebras](https://www.cerebras.ai/blog/openai-gpt-oss-120b-runs-fastest-on-cerebras)    | 131K                                 | $0.25 / $0.69                                    | 33K                | Jun 01, 2024     |
| [OpenAI o3-pro (06-20)](https://platform.openai.com/docs/models/o3-pro)                                                                                  | OpenAI                                                                                   | 200K                                 | $20.00 / $80.00                                  | 100K               | Jun 01, 2024     |
| [OpenAI o4-mini (04-16)](https://platform.openai.com/docs/models/o4-mini)                                                                                | OpenAI                                                                                   | 200K                                 | $1.10 / $4.40                                    | 100K               | Jun 01, 2024     |
| [OpenAI o3-mini (01-31)](https://platform.openai.com/docs/models/o3-mini)                                                                                | OpenAI                                                                                   | 200K                                 | $1.10 / $4.40                                    | 100K               | Up to Oct 2023   |
| [Claude 3.7 Sonnet (Thinking mode)](https://www.anthropic.com/news/claude-3-7-sonnet)                                                                    | Google Vertex AI                                                                         | 200K                                 | $3.00 / $15.00                                   | 64K (128K in beta) | Nov, 2024        |
| [GPT-4.1 mini (04-14)](https://platform.openai.com/docs/models/gpt-4.1-mini)                                                                             | OpenAI                                                                                   | 1M                                   | $0.40 / $1.60                                    | 32K                | Jun 01, 2024     |
| [Grok 3 beta](https://docs.x.ai/docs/models/grok-3)                                                                                                      | xAI Console                                                                              | 131K                                 | $3.00 / $15.00                                   | 131K               | 17th Nov, 2024   |
| [GPT-4.1 (04-14)](https://platform.openai.com/docs/models/gpt-4.1)                                                                                       | OpenAI                                                                                   | 1M                                   | $2.00 / $8.00                                    | 32K                | Jun 01, 2024     |
| [ChatGPT-4o Latest (2025-03-26)](https://platform.openai.com/docs/models/chatgpt-4o-latest)                                                              | OpenAI                                                                                   | 128K                                 | $5.00 / $15.00                                   | 16K                | Up to Oct 2023   |
| [DeepSeek R1 (05-28)](https://api-docs.deepseek.com/news/news250528)                                                                                     | [Fireworks AI](https://fireworks.ai/models/fireworks/deepseek-r1-0528)                   | 160K                                 | $3.00 / $8.00                                    | 16K                | April, 2024      |
| [OpenAI o1 (12-17)](https://platform.openai.com/docs/models/o1)                                                                                          | OpenAI                                                                                   | 200K                                 | $15.00 / $60.00                                  | 100K               | Up to Oct 2023   |
| [DeepSeek V3 (03-24)](https://api-docs.deepseek.com/news/news250325)                                                                                     | [Fireworks AI](https://fireworks.ai/models/fireworks/deepseek-v3-0324)                   | 64K                                  | $1.20 / $1.20                                    | 8K                 | Up to Oct 2023   |
| [DeepSeek R1](https://fireworks.ai/models/fireworks/deepseek-r1)                                                                                         | [Fireworks AI](https://fireworks.ai/models/fireworks/deepseek-r1)                        | 64K                                  | $3.00 / $8.00                                    | 8K                 | Up to Oct 2023   |
| [GPT-4.5 Preview](https://openai.com/index/introducing-gpt-4-5/)                                                                                         | OpenAI                                                                                   | 128K                                 | $75.00 / $150.00                                 | 16K                | Up to Oct 2023   |
| [OpenAI o1-Pro](https://platform.openai.com/docs/models/o1-pro)                                                                                          | OpenAI                                                                                   | 200K                                 | $150.00 / $600.00                                | 100K               | Up to Oct 2023   |
| [Llama 4 Maverick](https://ai.meta.com/blog/llama-4-multimodal-intelligence)                                                                             | [Fireworks AI](https://app.fireworks.ai/models/fireworks/llama4-maverick-instruct-basic) | 1M                                   | $0.05 / $0.22                                    | 131K               | Aug, 2024        |
| [GPT-4.1 nano](https://openai.com/index/gpt-4-1/)                                                                                                        | OpenAI                                                                                   | 1M                                   | $0.025 / $0.4                                    | 32K                | June, 2024       |
| [Amazon Nova Premier](https://aws.amazon.com/blogs/aws/amazon-nova-premier-our-most-capable-model-for-complex-tasks-and-teacher-for-model-distillation/) | AWS Bedrock                                                                              | 1M                                   | $2.5 / $12.5                                     | 10K                | N/A              |
| [Amazon Nova Pro](https://aws.amazon.com/ai/generative-ai/nova/)                                                                                         | AWS Bedrock                                                                              | 300K                                 | $0.80 / $3.20                                    | 10K                | October, 2023    |
| [Gemma 3 (1B, 4B, 12B, 27B)](https://ai.google.dev/gemma)                                                                                                | Locally hosted                                                                           | 128K max, 32K used during evaluation | $0.00 / $0.00                                    | N/A                | August, 2024     |
| [Phi 4 14.7B](https://huggingface.co/microsoft/phi-4)                                                                                                    | Locally hosted                                                                           | 16K                                  | $0.00 / $0.00                                    | N/A                | June, 2024       |

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