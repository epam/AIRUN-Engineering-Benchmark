# LLMs Leaderboard (Benchmark v3, last update 2025-11-26)

> 📊 **Interactive Leaderboard**: View live results with charts at Our [LLM Leaderboard](https://epam.github.io/AIRUN-Engineering-Benchmark/llm)

## Coding Leaderboard Rating

![llm-rating.png](/images/llms/coding/llm-score.png)

### Multimodal Leaderboard Rating

![llm-rating.png](/images/llms/multimodal/llm-score.png)

## Introduction to EPAM AI/RUN LLMs Engineering Benchmark

This page presents the results of LLMs engineering benchmark v3 including a leaderboard that compares the effectiveness of Anthropic, Amazon, Google DeepMind, Meta, xAI, OpenAI, and other companies'
LLMs (Large Language Models) and SMLs (Small Language Models) in executing both coding and multimodal tasks, including code translation, code generation, documentation generation, large context
instruction following (LCIF), and multimodal reasoning.

This leaderboard will be updated regularly to reflect the latest developments in the field of large language models.


> Previous results for benchmark v1 were moved to [llm-leaderboard-v1.md](benchmark_v1/llm-leaderboard_v1.md) for reference.<br />
> Benchmark v2 results moved to [llm-leaderboard-v2.md](benchmark_v2/llm-leaderboard_v2.md)

## Benchmark Key Findings

General insights:

**Coding Benchmark Leaders:**

- GPT-5.1 (11-13) leads with 83.36%, with high reasoning variant at 83.96% (171.48 min, $7.87) - minimal improvement (+0.6%) at 2.5x cost
- Claude Opus 4.5 scores 83.18%, first model by Anthropic available on all major cloud providers (Vertex AI, Azure, AWS, Anthropic API), also price reduced from $15/$75 to $5/$25 per MTok
- Claude Sonnet 4.5 achieves 82.19%, strong balanced performance without reasoning mode
- Claude Haiku 4.5 scores 81.83% with exceptional speed (180.66 T/S) and mid-tier pricing ($3.61), first place in code documentation (80.64%)
- Grok 4 Fast delivers 79.45% with best cost-efficiency ($0.22)
- GPT-5.1 Codex achieves 78.72%, specialized coding model with extremely slow LCIF execution (~90 min vs typical 10 min), frequent tool call errors with repeated file reads/writes
- GPT-5 Codex achieves 77.25%, specialized for complex software engineering with code generation leadership (81.42%)
- Grok 4.1 Fast Reasoning scores 67.90%, affected by truncation bug: generates reasoning tokens, then truncates output after 50 tokens, causing low results on large contexts in code generation
- MiniMax M2 leads open-source models at 71.14%, strong code translation (81.63%) but struggles with LCIF (61.25%)
- Gemini 3 Pro Preview scores 70.25% with excellent LCIF (96.25%, tied 2nd) but limited by severe token generation constraints (~12K max vs 60K allowed), weak code documentation (52.08%)
- GPT-5.1 Codex mini achieves 61.58% (58.99 min, $1.04, 135.56 T/S), experiences similar tool handling issues as full Codex
- gpt-oss-120b achieves 62.19% with the fastest execution (6.71 min, 555.99 T/S) and ultra-low cost ($0.23)
- Grok 4.1 Fast scores 60.09%, performs below Grok 4 Fast (79.45%) despite version upgrade, required multiple LCIF attempts to achieve passing results

**Multimodal Benchmark Leaders:**

- Gemini 3 Pro Preview leads with 82.54% (25.70 min, 81.67 T/S, $3.00), unlike constrained coding performance, excels where output requirements are moderate
- GPT-5.1 Codex achieves 79.94% (31.97 min, $1.50), second place overall - significantly outperforms coding benchmark (78.72%, 7th place)
- GPT-5 Mini scores 79.21%, significantly outperforming coding (71.28%) with excellent cost-efficiency ($0.48)
- GPT-5.1 Codex mini scores 77.75% (9.83 min, $0.31, 125.00 T/S), fourth place - dramatically exceeds coding performance (61.58%, 16th place)
- GPT-5.1 (11-13) achieves 74.17%, regular variant outperforms high reasoning (70.43%) - opposite of coding pattern
- Claude Opus 4.5 scores 65.80% (10.43 min, $4.61), significantly below coding performance (83.18%)
- Claude Haiku 4.5 scores 61.13% with the fastest execution (4.64 min, $0.91), significantly behind coding performance (81.83%)
- Grok 4 Fast achieves 50.74% vs strong coding (79.45%), confirming xAI specialization in text-based programming
- Grok 4.1 Fast Reasoning/Nonreasoning scores 43.46% and 42.52% accordingly, lowest among Grok models

Performance metrics highlights:

**Coding Benchmark:**

- **Fastest token generation**: gpt-oss-120b (555.99 T/S), Claude Haiku 4.5 (180.66 T/S), Grok Code Fast (165.54 T/S), GPT-5.1 Codex mini (135.56 T/S), Grok 4 Fast (125.84 T/S)
- **Shortest execution time**: gpt-oss-120b (6.71 min), Grok Code Fast (17.66 min), Grok 4.1 Fast (26.07 min), Grok 4 Fast (41.22 min), Gemini 3 Pro Preview (44.32 min)
- **Most tokens generated**: GPT-5.1 (11-13) (high) (747,615 tokens), GPT-5 Mini (649,773 tokens), Claude Haiku 4.5 (642,436 tokens), Claude Opus 4.5 (603,412 tokens)
- **Best cost-effectiveness**: Grok 4.1 Fast Reasoning ($0.13), Grok 4.1 Fast ($0.14), Grok 4 Fast ($0.22), gpt-oss-120b ($0.23), GPT-5 Nano ($0.33), Grok Code Fast ($0.33)

**Multimodal Benchmark:**

- **Fastest token generation**: GPT-5.1 Codex mini (125.00 T/S), Grok 4 Fast (91.42 T/S), GPT-5 Nano (86.49 T/S), Gemini 3 Pro Preview (81.67 T/S), Claude Haiku 4.5 (74.89 T/S)
- **Shortest execution time**: Claude Haiku 4.5 (4.64 min), Grok 4.1 Fast (5.15 min), Claude Sonnet 4.5 (8.46 min), GPT-5.1 Codex mini (9.83 min), Claude Opus 4.5 (10.43 min)
- **Best cost-effectiveness**: GPT-5 Nano ($0.13), Grok 4.1 Fast ($0.13), Grok 4.1 Fast Reasoning ($0.13), Grok 4 Fast ($0.16), GPT-5.1 Codex mini ($0.31), GPT-5 Mini ($0.48)

Best results by category:

**Coding Benchmark:**

- **Code Translation**: GPT-5.1 (11-13) (high) (84.71%), GPT-5.1 (11-13) (84.17%), Claude Opus 4.5 (82.83%), Claude Haiku 4.5 (82.63%), GPT-5 Codex (81.67%), MiniMax M2 (81.63%)
- **Code Generation**: GPT-5 Codex (81.42%), Grok 4 Fast (80.38%), GPT-5.1 Codex (79.15%), GPT-5.1 (11-13) (high) (78.96%), GPT-5.1 (11-13) (77.65%), Claude Sonnet 4.5 (75.92%)
- **Code Documentation**: GPT-5.1 (11-13) (high) (80.92%), Claude Haiku 4.5 (80.64%), GPT-5.1 (11-13) (80.39%), Claude Sonnet 4.5 (79.53%), GPT-5 Mini (78.64%), Grok 4 Fast (78.39%)
- **LCIF**: Claude Opus 4.5 (98.50%), Grok Code Fast (98.50%), Claude Sonnet 4.5 (96.25%), Gemini 3 Pro Preview (96.25%), GPT-5.1 Codex (96.25%), Grok 4 (92.50%)

**Multimodal Benchmark:**

- **Overall Multimodal Performance**: Gemini 3 Pro Preview (82.54%), GPT-5.1 Codex (79.94%), GPT-5 Mini (79.21%), GPT-5.1 Codex mini (77.75%), GPT-5.1 (11-13) (74.17%), GPT-5 Codex (73.06%)

## Additional Views

<details>
<summary>Other metrics from coding leaderboard</summary>

![llm-type.png](/images/llms/coding/llm-reasoning.png)
![llm-type.png](/images/llms/coding/llm-license.png)
![llm-price.png](/images/llms/coding/llm-price.png)
![llm-tokens.png](/images/llms/coding/llm-tokens.png)
![llm-cost.png](/images/llms/coding/llm-cost.png)
![llm-time.png](/images/llms/coding/llm-time.png)
![llm-speed.png](/images/llms/coding/llm-speed.png)

</details>

<details>
<summary>Other metrics from multimodal leaderboard</summary>

![llm-type.png](/images/llms/multimodal/llm-reasoning.png)
![llm-type.png](/images/llms/multimodal/llm-license.png)
![llm-price.png](/images/llms/multimodal/llm-price.png)
![llm-tokens.png](/images/llms/multimodal/llm-tokens.png)
![llm-cost.png](/images/llms/multimodal/llm-cost.png)
![llm-time.png](/images/llms/multimodal/llm-time.png)
![llm-speed.png](/images/llms/multimodal/llm-speed.png)

</details>

### Observations

**Reasoning Mode Impact**

- GPT-5.1 high reasoning: +0.6% coding improvement at 2.5x cost, but -3.74% in multimodal
- Claude 4: reasoning mode reduces coding (-2%) but improves multimodal (+4%)
- Claude Sonnet 4.5: achieves top coding results without reasoning mode, suggesting integrated reasoning architecture

**Domain Specialization**

- Google Gemini: strong multimodal (82.54%), weak coding (70.25%) due to token generation limits (~12K max vs 60K allowed)
- OpenAI Codex variants show inverted performance: GPT-5.1 Codex/mini weaker in coding (78.72%, 61.58%) but excel in multimodal (79.94% 2nd, 77.75% 4th)
- xAI Grok: coding-focused (79.45%), multimodal struggles (50.74%), Grok 4.1 regression in both domains
- Claude: coding-optimized (83.18% Opus, 82.19% Sonnet), multimodal regression (65.80%, 54.76%)

**Key Limitations**

- Gemini 3 Pro Preview: severe output constraints impact code documentation (52.08%) and generation (58.23%), LCIF succeeds (96.25%)
- GPT-5.1 Codex/mini: tool handling issues with repeated file reads/writes, extremely slow LCIF execution (~90 min vs typical 10 min)
- Grok 4.1 Fast Reasoning: truncation bug on large contexts - generates reasoning tokens then truncates output after 50 tokens
- GPT-5 Nano: reasoning inefficiency - 95% tokens spent on thinking vs actual output
- Grok 4.1 Fast: regression vs Grok 4 Fast (60.09% vs 79.45%)

**Top Performers by Use Case**

- Coding: GPT-5.1 (11-13) for performance/cost balance, Claude Opus 4.5 for coding tasks (83.18%, price reduced to $5/$25), Claude Haiku 4.5 for speed
- Multimodal: Gemini 3 Pro Preview for accuracy, GPT-5.1 Codex for performance (79.94%, 2nd, $1.50), GPT-5.1 Codex mini for speed/cost (125 T/S, $0.31)
- Budget: Grok 4.1 models for lowest cost ($0.13 both benchmarks), Grok 4 Fast for coding quality ($0.22)
- Specialized: GPT-5 Codex for complex software engineering (81.42% code generation)
- Open-source: MiniMax M2 (71.14%), gpt-oss-120b for speed (555.99 T/S, $0.23)

### Detailed Results

All categories, except Large Context Instructions Following (LCIF), are evaluated automatically using the Large Language Model<sup>1</sup>.
You can read [llm-comparison-report.md](llm-comparison-report.md) for detailed coding benchmark analysis and [llm-comparison-report-multimodal.md](llm-comparison-report-multimodal.md) for multimodal
benchmark results. These reports include all experiment scores, performance breakdowns by category, and comprehensive analysis.

The tables below provide an overview of both coding and multimodal benchmark experiments. For coding tasks, you can review the average accuracy and completeness across all categories, total execution
time, generation token speed (token per second), the total number of input and output tokens, the cost of the experiment, and the final score. The multimodal benchmark focuses on visual reasoning and
multimodal instruction following capabilities.

<details>
<summary>Detailed Results and Observations</summary>

### Coding Benchmark Results

| Name                    | Reasoning  | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total Thinking | Total output | Cost $ | Total Score |
|-------------------------|------------|----------|--------------|------------------|-------------|-------------|----------------|--------------|--------|-------------|
| GPT-5.1 (11-13) (high)  | Yes (high) | 0.796    | 0.832        | 171.48           | 72.66       | 314149      | 369491         | 747615       | 7.87   | 83.96%      |
| GPT-5.1 (11-13)         | No         | 0.795    | 0.817        | 68.46            | 78.94       | 314149      | -              | 324268       | 3.64   | 83.36%      |
| Claude Opus 4.5         | No         | 0.761    | 0.796        | 142.09           | 70.78       | 399778      | -              | 603412       | 17.08  | 83.18%      |
| Claude Sonnet 4.5       | No         | 0.773    | 0.782        | 101.75           | 81.41       | 399735      | -              | 496983       | 8.65   | 82.19%      |
| Claude Haiku 4.5        | No         | 0.777    | 0.807        | 59.27            | 180.66      | 399778      | -              | 642436       | 3.61   | 81.83%      |
| Grok 4 Fast             | Yes        | 0.767    | 0.810        | 41.22            | 125.84      | 315508      | 65852          | 311224       | 0.22   | 79.45%      |
| GPT-5.1 Codex           | Yes (high) | 0.711    | 0.723        | 197.44           | 50.29       | 314149      | 413568         | 595740       | 6.35   | 78.72%      |
| GPT-5 Codex             | Yes (low)  | 0.696    | 0.751        | 69.49            | 63.39       | 314149      | 61760          | 264293       | 3.04   | 77.25%      |
| Grok 4 (07-09)          | Yes        | 0.680    | 0.652        | 80.75            | 46.27       | 339997      | 57357          | 224156       | 4.38   | 73.33%      |
| Grok Code Fast          | Yes        | 0.645    | 0.603        | 17.66            | 165.54      | 319314      | 16584          | 175420       | 0.33   | 71.74%      |
| GPT-5 Mini              | Yes (high) | 0.751    | 0.785        | 191.62           | 56.51       | 314149      | 339968         | 649773       | 1.38   | 71.28%      |
| MiniMax M2              | Yes        | 0.714    | 0.756        | 172.20           | 31.67       | 320258      | N/A            | 327231       | 0.49   | 71.14%      |
| Gemini 3 Pro Preview    | Yes (high) | 0.583    | 0.621        | 44.32            | 93.72       | 374616      | 75652          | 249189       | 3.74   | 70.25%      |
| Grok 4.1 Fast Reasoning | Yes        | 0.610    | 0.628        | 56.20            | 42.28       | 317185      | 171344         | 142556       | 0.13   | 67.90%      |
| gpt-oss-120b            | Yes (low)  | 0.709    | 0.720        | 6.71             | 555.99      | 316966      | N/A            | 223941       | 0.23   | 62.19%      |
| GPT-5.1 Codex mini      | Yes (high) | 0.591    | 0.606        | 58.99            | 135.56      | 314149      | 341632         | 479773       | 1.04   | 61.58%      |
| Grok 4.1 Fast           | No         | 0.609    | 0.608        | 26.07            | 101.67      | 317701      | -              | 159054       | 0.14   | 60.09%      |
| GPT-5 Nano              | Yes (high) | 0.652    | 0.630        | 150.27           | 86.83       | 314149      | 541824         | 782832       | 0.33   | 58.61%      |
| Amazon Nova Premier     | No         | 0.282    | 0.205        | 15.88            | 46.56       | 224223      | -              | 44360        | 1.12   | 26.89%      |

_Table 1. Overview of the coding benchmark results._

### Multimodal Benchmark Results

| Name                    | Reasoning  | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total Thinking | Total output | Cost $ | Total Score |
|-------------------------|------------|----------|--------------|------------------|-------------|-------------|----------------|--------------|--------|-------------|
| Gemini 3 Pro Preview    | Yes (high) | 0.809    | 0.973        | 25.70            | 81.67       | 743882      | 107774         | 125944       | 3.00   | 82.54%      |
| GPT-5.1 Codex           | Yes (high) | 0.778    | 0.992        | 31.97            | 38.29       | 610241      | 60480          | 73432        | 1.50   | 79.94%      |
| GPT-5 Mini              | Yes (high) | 0.769    | 0.997        | 51.23            | 52.28       | 636192      | 124352         | 160700       | 0.48   | 79.21%      |
| GPT-5.1 Codex mini      | Yes (high) | 0.756    | 0.974        | 9.83             | 125.00      | 636192      | 60800          | 73687        | 0.31   | 77.75%      |
| GPT-5.1 (11-13)         | No         | 0.713    | 1.000        | 20.05            | 39.70       | 610241      | -              | 47761        | 1.24   | 74.17%      |
| GPT-5 Codex             | Yes (low)  | 0.704    | 0.970        | 11.67            | 49.14       | 610301      | 23232          | 34411        | 1.11   | 73.06%      |
| GPT-5.1 (11-13) (high)  | Yes (high) | 0.672    | 0.992        | 64.07            | 39.27       | 610241      | 97171          | 150970       | 2.27   | 70.43%      |
| GPT-5 Nano              | Yes (high) | 0.627    | 0.994        | 46.74            | 86.49       | 649510      | 208768         | 242562       | 0.13   | 66.34%      |
| Claude Opus 4.5         | No         | 0.622    | 0.982        | 10.43            | 38.32       | 801240      | -              | 23977        | 4.61   | 65.80%      |
| Claude Haiku 4.5        | No         | 0.571    | 0.971        | 4.64             | 74.89       | 801240      | -              | 20831        | 0.91   | 61.13%      |
| Claude Sonnet 4.5       | No         | 0.503    | 0.949        | 8.46             | 37.12       | 801210      | -              | 18843        | 2.69   | 54.76%      |
| Amazon Nova Premier     | No         | 0.489    | 0.928        | 14.85            | 16.78       | 767489      | -              | 14954        | 2.11   | 53.26%      |
| Grok 4 Fast             | Yes        | 0.455    | 0.982        | 14.22            | 91.42       | 586517      | 32902          | 77976        | 0.16   | 50.74%      |
| Grok 4 (07-09)          | Yes        | 0.380    | 0.958        | 66.46            | 42.72       | 606242      | 138102         | 170368       | 4.37   | 43.75%      |
| Grok 4.1 Fast Reasoning | Yes        | 0.375    | 0.974        | 18.69            | 25.58       | 587687      | 65856          | 28675        | 0.13   | 43.46%      |
| Grok 4.1 Fast           | No         | 0.366    | 0.955        | 5.15             | 70.27       | 588047      | -              | 21694        | 0.13   | 42.52%      |

_Table 2. Overview of the multimodal benchmark results._

> Additional info:  
> Evaluation of benchmark results were performed automatically with the help of evaluation tools based on the LLMs.
> Please refer to the page [LLMs Benchmark Approach](llm-approach.md) for more details on the evaluation methodology.

</details>

## Models specification

| LLM Name                                                                                                                                                 | API Provider used in benchmark                                                        | Context Window | Cost (Input / Output per MTok)                   | Max Output | Knowledge Cutoff |
|----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|----------------|--------------------------------------------------|------------|------------------|
| [GPT-5.1 (11-13)](https://platform.openai.com/docs/models/gpt-5.1)                                                                                       | OpenAI                                                                                | 400K           | $1.25 / $10.00                                   | 128K       | Sep 30, 2024     |
| [Claude 4.5 Opus](https://www.anthropic.com/news/claude-opus-4-5)                                                                                        | Google Vertex AI                                                                      | 200K           | $5.00 / $25.00                                   | 64K        | July, 2025       |
| [Claude 4.5 Sonnet](https://www.anthropic.com/news/claude-sonnet-4-5)                                                                                    | Google Vertex AI                                                                      | 200K           | $3.00 / $15.00                                   | 64K        | July, 2025       |
| [Claude Haiku 4.5](https://www.anthropic.com/news/claude-haiku-4-5)                                                                                      | Google Vertex AI                                                                      | 200K           | $1.00 / $5.00                                    | 64K        | July, 2025       |
| [Grok 4 Fast Reasoning](https://docs.x.ai/docs/models/grok-4-fast-reasoning)                                                                             | xAI                                                                                   | 2M             | $0.20 / $0.50                                    | N/A        | N/A              |
| [GPT-5.1-codex](https://platform.openai.com/docs/models/gpt-5.1-codex)                                                                                   | OpenAI                                                                                | 400K           | $1.25 / $10.00                                   | 128K       | Sep 30, 2024     |
| [GPT-5-codex](https://platform.openai.com/docs/models/gpt-5-codex)                                                                                       | OpenAI                                                                                | 400K           | $1.25 / $10.00                                   | 128K       | Sep 30, 2024     |
| [Grok 4 (07-09)](https://docs.x.ai/docs/models/grok-4-0709)                                                                                              | xAI Console                                                                           | 256K           | $3.00 / $15.00 <= 128K and $6.00 / $30.00 > 128K | N/A        | N/A              |
| [Grok Code Fast](https://x.ai/news/grok-code-fast-1)                                                                                                     | xAI                                                                                   | 256K           | $0.20 / $1.50                                    | N/A        | N/A              |
| [GPT-5 Mini (08-07)](https://platform.openai.com/docs/models/gpt-5-mini)                                                                                 | OpenAI                                                                                | 400K           | $0.25 / $2.00                                    | 128K       | May 31, 2024     |
| [MiniMax M2](https://github.com/MiniMax-AI/MiniMax-M2)                                                                                                   | [Fireworks.ai](https://fireworks.ai/models/fireworks/minimax-m2)                      | 200K           | $0.30 / $1.20                                    | 131K       | N/A              |
| [Gemini 3 Pro Preview](https://ai.google.dev/gemini-api/docs/models#gemini-3-pro)                                                                        | Google AI Studio                                                                      | 1M             | $2.00 / $12.00 <= 200K<br>$4 / $18.00 > 200K     | 65K        | Jan, 2025        |
| [Grok 4.1 Fast Reasoning/Nonreasoning](https://docs.x.ai/docs/models/grok-4-1-fast-reasoning)                                                            | xAI                                                                                   | 2M             | $0.20 / $0.50 <= 128K / $0.40 / $1.00 > 128K     | N/A        | N/A              |
| [gpt-oss-120b](https://platform.openai.com/docs/models/gpt-oss-120b)                                                                                     | [Cerebras](https://www.cerebras.ai/blog/openai-gpt-oss-120b-runs-fastest-on-cerebras) | 131K           | $0.25 / $0.69                                    | 33K        | Jun 01, 2024     |
| [GPT-5 Nano (08-07)](https://platform.openai.com/docs/models/gpt-5-nano)                                                                                 | OpenAI                                                                                | 400K           | $0.05 / $0.40                                    | 128K       | May 31, 2024     |
| [Amazon Nova Premier](https://aws.amazon.com/blogs/aws/amazon-nova-premier-our-most-capable-model-for-complex-tasks-and-teacher-for-model-distillation/) | AWS Bedrock                                                                           | 1M             | $2.5 / $12.5                                     | 10K        | N/A              |

_Table 3. Description of LLMs, their versions, amount of information to process, and the length of the response._

## Notes

- To learn more about our methodology for evaluating LLMs, please read [LLMs Benchmark Approach](llm-approach.md).
- To submit your model for evaluation, please refer to the [Large Language Model Benchmark Submission](submissions/llm-benchmark-submission.md) page.
- Previous charts with ratings and other scores can be found in the [LLMs Charts archive](/images/llms/llm-charts-archive).

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>