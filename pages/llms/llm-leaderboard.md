# LLMs Leaderboard (Benchmark v3.1, last update 2026-01-12)

> 📊 **Interactive Leaderboard**: View live results with charts at our [LLM Leaderboard](https://epam.github.io/AIRUN-Engineering-Benchmark/llm)

## Coding Leaderboard Rating

![llm-rating.png](/images/llms/coding/llm-score.png)

### Multimodal Leaderboard Rating

![llm-rating.png](/images/llms/multimodal/llm-score.png)

## Introduction to EPAM AI/RUN LLMs Engineering Benchmark

This page presents the results of LLMs engineering benchmark v3 including a leaderboard that compares the effectiveness of Anthropic, Google DeepMind, xAI, OpenAI, and other companies' LLMs (Large
Language Models) and SMLs (Small Language Models) in executing both coding and multimodal tasks, including code translation, code generation, documentation generation, large context instruction
following (LCIF), and multimodal reasoning.

This leaderboard will be updated regularly to reflect the latest developments in the field of large language models.


> Previous results for benchmark v1 were moved to [llm-leaderboard-v1.md](/pages/llms/benchmark_v1/llm-leaderboard_v1.md) for reference.<br />
> Benchmark v2 results moved to [llm-leaderboard-v2.md](/pages/llms/benchmark_v2/llm-leaderboard_v2.md)
> Benchmark v3 results moved to [llm-leaderboard-v3.md](/pages/llms/benchmark_v3/llm-leaderboard_v3.md)

## Benchmark Key Findings

General insights:

**Coding Benchmark Leaders:**

- GPT-5.2 (12-11) (high) achieves 85.53% with strong performance across categories (code translation: 85.33%, code generation: 81.42%, documentation: 82.86%, LCIF: 92.50%), execution time 154.25 min
  at $9.39 cost
- Claude Opus 4.5 Think achieves 85.31% with reasoning mode, delivering excellent code translation (83.25%) and documentation (82.89%), LCIF excellence (98.50%), execution time 240.63 min at $27.69
  cost
- Claude Opus 4.5 achieves 85.18% without reasoning mode, maintaining strong code translation (82.92%), code generation (78.27%), and LCIF (98.50%), execution time 228.37 min at $26.84 cost
- GPT-5.2 (12-11) achieves 84.61% with fast execution (85.90 min, 91.66 T/S) and balanced cost ($7.18), strong code generation (80.27%) and translation (82.96%)
- Claude Sonnet 4.5 Think achieves 83.91% with reasoning mode, leading in code documentation (85.31%), execution time 205.75 min at $15.54 cost
- Claude Sonnet 4.5 achieves 83.10% without reasoning, excelling in code documentation (84.06%), execution time 203.17 min at $15.91 cost
- GPT-5.1 Codex achieves 82.26% with balanced performance (code translation: 78.17%, code generation: 78.00%, documentation: 76.64%, LCIF: 96.25%), execution time 198.42 min at $10.76 cost, performs
  better in multimodal benchmark (79.94%) but may show "no access to write tools" messages in high-output scenarios
- Claude Haiku 4.5 achieves 79.58% with exceptional speed (181.81 T/S) and highest token generation (1.1M tokens), strong code documentation (80.42%), execution time 101.02 min at $5.92 cost
- Kimi K2 Thinking achieves 78.46% as top open-source model, delivering strong performance (code translation: 78.38%, code generation: 76.27%, documentation: 79.19%, LCIF: 80.00%), excellent speed (
  161.66 T/S), fast execution (62.83 min) at low cost ($1.72)
- Grok 4 (07-09) achieves 74.23% with balanced performance across categories, execution time 94.85 min at $5.39 cost
- GPT-5 Mini achieves 73.17% (high reasoning) with strong code translation (79.71%) and excellent documentation (83.86%) despite weak LCIF (55.00%), execution time 186.19 min at $1.59 cost
- DeepSeek V3.2 achieves 72.52% as reasoning model with improved performance, delivering balanced results (code translation: 73.96%, code generation: 72.15%, documentation: 68.97%, LCIF: 75.00%),
  execution time 96.28 min at ultra-low cost ($0.99)
- Grok Code Fast achieves 71.75% with LCIF excellence (93.50%), execution time 57.29 min at low cost ($0.45)
- Gemini 3 Pro Preview achieves 70.00% with strong LCIF (92.50%), but limited by token generation constraints (~7-10k output per scenario vs 64k theoretical limit), execution time 54.07 min at $4.78
  cost
- GPT-5.1 Codex mini achieves 69.45% with strong code translation (77.71%), performs better in multimodal benchmark (77.75%), similar tool handling characteristics as full Codex, execution time 120.30
  min at $1.87 cost
- Gemini 3 Flash Preview achieves 68.34% with exceptional speed (23.00 min, 159.08 T/S) and low cost ($0.85), strong LCIF (96.25%), but affected by token generation constraints similar to Pro variant
- MiniMax M2.1 achieves 67.73% with strong code documentation (79.67%) and code translation (70.13%), execution time 61.59 min at $0.67 cost
- Grok 4.1 Fast Reasoning achieves 63.23% affected by truncation bug in code translation tasks (20.33%), while maintaining acceptable code generation (66.00%), documentation (75.33%), and LCIF (
  91.25%), execution time 37.95 min at ultra-low cost ($0.15)
- Grok 4.1 Fast achieves 62.17% without the truncation issue but moderate overall performance, execution time 19.00 min at ultra-low cost ($0.18)
- GPT-5 Nano achieves 57.06% with ultra-low cost ($0.36), execution time 114.74 min

**Multimodal Benchmark Leaders:**

- Gemini 3 Flash Preview leads with 83.35% (13.32 min, 116.32 T/S, $0.65), achieving best result with exceptional speed and cost-efficiency, significantly outperforming its coding results (68.34%)
- Gemini 3 Pro Preview achieves 82.54% (25.70 min, 81.67 T/S, $3.00), token-efficient design excels in multimodal vs moderate coding performance (70.00%)
- GPT-5.2 (12-11) (high) achieves 82.52% (33.85 min, $2.20) with consistent cross-domain excellence (coding: 85.53%)
- GPT-5.1 Codex achieves 79.94% (31.97 min, $1.50), outperforming coding benchmark (82.26%) in multimodal tasks
- GPT-5 Mini scores 79.21% with excellent cost-efficiency ($0.48), outperforming coding (73.17%)
- GPT-5.2 (12-11) achieves 77.89% (16.71 min, $1.67), fast execution with perfect completeness (100%)
- GPT-5.1 Codex mini scores 77.75% (9.83 min, $0.31, 125.00 T/S), significantly exceeding coding performance (69.45%)
- Claude Opus 4.5 Think achieves 70.94% (22.78 min, $5.75) with reasoning mode, below coding performance (85.31%)
- Claude Sonnet 4.5 Think achieves 67.82% (20.16 min, $3.34) with reasoning mode, below coding performance (83.91%)
- GPT-5 Nano achieves 66.34% ($0.13), best cost-effectiveness
- Claude Opus 4.5 scores 65.80% (10.43 min, $4.61), significantly below coding performance (85.18%)
- Claude Haiku 4.5 scores 61.13% with the fastest execution (4.64 min, $0.91), below coding performance (79.58%)
- Claude Sonnet 4.5 scores 54.76% (8.46 min, $2.69), significantly below coding performance (83.10%)
- Grok 4 (07-09) achieves 43.75%, below coding performance (74.23%), confirming xAI specialization in text-based programming
- Grok 4.1 Fast Reasoning/Nonreasoning score 43.46% and 42.52% accordingly

Performance metrics highlights:

**Coding Benchmark:**

- **Fastest token generation**: Grok 4.1 Fast (192.58 T/S), Claude Haiku 4.5 (181.81 T/S), Kimi K2 Thinking (161.66 T/S), Gemini 3 Flash Preview (159.08 T/S), MiniMax M2.1 (129.56 T/S)
- **Shortest execution time**: Grok 4.1 Fast (19.00 min), Gemini 3 Flash Preview (23.00 min), Grok 4.1 Fast Reasoning (37.95 min), Gemini 3 Pro Preview (54.07 min), Grok Code Fast (57.29 min)
- **Most tokens generated**: Claude Haiku 4.5 (1,102,016 tokens), GPT-5.1 Codex (1,035,665 tokens), Claude Opus 4.5 Think (1,024,709 tokens)
- **Best cost-effectiveness**: Grok 4.1 Fast Reasoning ($0.15), Grok 4.1 Fast ($0.18), GPT-5 Nano ($0.36), Grok Code Fast ($0.45), MiniMax M2.1 ($0.67)

**Multimodal Benchmark:**

- **Fastest token generation**: GPT-5.1 Codex mini (125.00 T/S), Gemini 3 Flash Preview (116.32 T/S), Grok 4 Fast (91.42 T/S), GPT-5 Nano (86.49 T/S), Gemini 3 Pro Preview (81.67 T/S)
- **Shortest execution time**: Claude Haiku 4.5 (4.64 min), Grok 4.1 Fast (5.15 min), Claude Sonnet 4.5 (8.46 min), GPT-5.1 Codex mini (9.83 min), Claude Opus 4.5 (10.43 min)
- **Best cost-effectiveness**: GPT-5 Nano ($0.13), Grok 4.1 Fast ($0.13), Grok 4.1 Fast Reasoning ($0.13), Grok 4 Fast ($0.16), GPT-5.1 Codex mini ($0.31), GPT-5 Mini ($0.48)

Best results by category:

**Coding Benchmark:**

- **Code Translation**: GPT-5.2 (12-11) (high) (85.33%), Claude Opus 4.5 Think (83.25%), GPT-5.2 (12-11) (82.96%), Claude Opus 4.5 (82.92%), GPT-5 Mini (79.71%)
- **Code Generation**: GPT-5.2 (12-11) (high) (81.42%), GPT-5.2 (12-11) (80.27%), Claude Opus 4.5 (78.27%), GPT-5.1 Codex (78.00%), Claude Opus 4.5 Think (76.62%)
- **Code Documentation**: Claude Sonnet 4.5 Think (85.31%), Claude Sonnet 4.5 (84.06%), GPT-5 Mini (83.86%), Claude Opus 4.5 Think (82.89%), GPT-5.2 (12-11) (high) (82.86%)
- **LCIF**: Claude Opus 4.5 (98.50%), Claude Opus 4.5 Think (98.50%), Gemini 3 Flash Preview (96.25%), Claude Sonnet 4.5 (96.25%), GPT-5.1 Codex (96.25%), Claude Sonnet 4.5 Think (96.25%)

**Multimodal Benchmark:**

- **Overall Multimodal Performance**: Gemini 3 Flash Preview (83.35%), Gemini 3 Pro Preview (82.54%), GPT-5.2 (12-11) (high) (82.52%), GPT-5.1 Codex (79.94%), GPT-5 Mini (79.21%)

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

**Leadership and Reasoning Mode Impact**

GPT-5.2 (12-11) and Anthropic Claude models share leadership in coding benchmark. GPT-5.2 (high) leads with 85.53%, excelling in code translation (85.33%) and code generation (81.42%). Claude models
demonstrate strong performance both with and without reasoning mode: Claude Opus 4.5 Think (85.31%) and non-reasoning variant (85.18%) show minimal difference, while Claude Sonnet 4.5 Think (83.91%)
leads in code documentation (85.31%). The Claude family generates highest token output, with Claude Haiku 4.5 producing 1.1M tokens and maintaining exceptional speed (181.81 T/S).

**Open-Source Excellence**

Kimi K2 Thinking achieves 78.46% as top open-source model, delivering strong balanced performance across all categories (code translation: 78.38%, code generation: 76.27%, documentation: 79.19%, LCIF:
80.00%) with excellent speed (161.66 T/S) and low cost ($1.72). DeepSeek V3.2 demonstrates improved performance as reasoning model, achieving 72.52% with ultra-low cost ($0.99) and balanced results
across categories. MiniMax M2.1 shows strong code documentation capabilities (79.67%) at competitive pricing ($0.67).

**xAI Grok Models Performance**

Grok 4 (07-09) delivers 74.23% with moderate performance across categories. Newer Grok 4.1 variants show regression: Grok 4.1 Fast Reasoning (63.23%) continues to suffer from truncation bug in code
translation tasks (20.33%), where model generates reasoning tokens but abruptly truncates output, while maintaining acceptable performance in code generation (66.00%), documentation (75.33%), and
LCIF (91.25%). Grok 4.1 Fast (62.17%) avoids the truncation issue but shows moderate overall results. Grok Code Fast maintains LCIF excellence (93.50%) with fast execution and low cost.

**Google Gemini Token Generation Constraints**

Gemini 3 models demonstrate significant token generation limitations despite 64k theoretical output capacity. Models generate only ~7-10k tokens per scenario, resulting in ~300k total output tokens
across benchmark, compared to 1M+ tokens from leading models. Gemini 3 Pro Preview (70.00%) and Flash Preview (68.34%) show strong LCIF performance (92.50% and 96.25%) but limited code generation and
documentation scores due to output constraints. Previous Gemini 2.5 Flash achieved 800k+ tokens in earlier benchmarks, but Google's recent adjustments reduced token generation, impacting coding
performance while improving cost-efficiency.

**OpenAI Codex Tool Handling Behavior**

GPT-5.1 Codex (82.26%) and Codex mini (69.45%) demonstrate unique tool handling characteristics in coding tasks. When tests require extensive output generation, models may respond with "no access to
write tools, please provide tools and I will generate results" messages instead of producing code directly. This behavior particularly affects high-output scenarios but doesn't impact models' strong
performance in multimodal benchmark (79.94% and 77.75% respectively), where tool usage requirements are minimal and visual reasoning capabilities excel.

**Domain Specialization Patterns**

Cross-domain performance reveals clear specialization patterns. Gemini 3 models excel in multimodal tasks (Flash: 83.35%, Pro: 82.54%) significantly outperforming coding results (68.34%, 70.00%),
demonstrating Google's optimization for visual reasoning with concise outputs. Claude models show inverse pattern, with strong coding performance (Opus: 85.18%, Sonnet: 83.10%, Haiku: 79.58%) but
lower multimodal scores (65.80%, 54.76%, 61.13%), indicating Anthropic's focus on text-based programming tasks. OpenAI GPT-5.2 maintains consistent excellence across both domains (coding: 85.53%,
multimodal: 82.52%). xAI Grok models specialize in text-based programming, with Grok 4 achieving 74.23% in coding but only 43.75% in multimodal tasks.

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
| GPT-5.2 (12-11) (high)  | Yes (high) | 0.810    | 0.852        | 154.25           | 68.06       | 325207      | 129372         | 629918       | 9.39   | 85.53%      |
| Claude Opus 4.5 Think   | Yes        | 0.795    | 0.827        | 240.63           | 70.97       | 413767      | N/A            | 1024709      | 27.69  | 85.31%      |
| Claude Opus 4.5         | No         | 0.797    | 0.818        | 228.37           | 72.32       | 412477      | -              | 990965       | 26.84  | 85.18%      |
| GPT-5.2 (12-11)         | No         | 0.804    | 0.837        | 85.90            | 91.66       | 325207      | -              | 472424       | 7.18   | 84.61%      |
| Claude Sonnet 4.5 Think | Yes        | 0.796    | 0.814        | 205.75           | 77.22       | 413767      | N/A            | 953288       | 15.54  | 83.91%      |
| Claude Sonnet 4.5       | No         | 0.785    | 0.803        | 203.17           | 80.23       | 412477      | -              | 978018       | 15.91  | 83.10%      |
| GPT-5.1 Codex           | Yes (high) | 0.758    | 0.791        | 198.42           | 86.99       | 325207      | 717120         | 1035665      | 10.76  | 82.26%      |
| Claude Haiku 4.5        | No         | 0.746    | 0.787        | 101.02           | 181.81      | 412477      | -              | 1102016      | 5.92   | 79.58%      |
| Kimi K2 Thinking        | Yes        | 0.758    | 0.804        | 62.83            | 161.66      | 327773      | N/A            | 609390       | 1.72   | 78.46%      |
| Grok 4 (07-09)          | Yes        | 0.651    | 0.703        | 94.85            | 50.84       | 350971      | 75804          | 289367       | 5.39   | 74.23%      |
| GPT-5 Mini              | Yes (high) | 0.775    | 0.820        | 186.19           | 67.69       | 325207      | 337920         | 756191       | 1.59   | 73.17%      |
| DeepSeek V3.2           | Yes        | 0.690    | 0.736        | 96.28            | 82.21       | 338854      | N/A            | 474934       | 0.99   | 72.52%      |
| Grok Code Fast          | Yes        | 0.627    | 0.654        | 57.29            | 74.94       | 330288      | 19285          | 257592       | 0.45   | 71.75%      |
| Gemini 3 Pro Preview    | Yes (high) | 0.590    | 0.637        | 54.07            | 102.93      | 386529      | 95722          | 333950       | 4.78   | 70.00%      |
| GPT-5.1 Codex mini      | Yes (high) | 0.697    | 0.723        | 120.30           | 124.08      | 325207      | 630272         | 895575       | 1.87   | 69.45%      |
| Gemini 3 Flash Preview  | Yes        | 0.568    | 0.586        | 23.00            | 159.08      | 386529      | 34352          | 219502       | 0.85   | 68.34%      |
| MiniMax M2.1            | Yes        | 0.722    | 0.699        | 61.59            | 129.56      | 331296      | N/A            | 478803       | 0.67   | 67.73%      |
| Grok 4.1 Fast Reasoning | Yes        | 0.572    | 0.571        | 37.95            | 76.48       | 328224      | 202817         | 376972       | 0.25   | 63.23%      |
| Grok 4.1 Fast           | No         | 0.653    | 0.636        | 19.00            | 192.58      | 328740      | -              | 219545       | 0.18   | 62.17%      |
| GPT-5 Nano              | Yes (high) | 0.634    | 0.669        | 114.74           | 125.96      | 325207      | 577408         | 867145       | 0.36   | 57.06%      |

_Table 1. Overview of the coding benchmark results._

### Multimodal Benchmark Results

| Name                    | Reasoning  | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total Thinking | Total output | Cost $ | Total Score |
|-------------------------|------------|----------|--------------|------------------|-------------|-------------|----------------|--------------|--------|-------------|
| Gemini 3 Flash Preview  | Yes        | 0.815    | 1.000        | 13.32            | 116.32      | 743882      | 77035          | 92991        | 0.65   | 83.35%      |
| Gemini 3 Pro Preview    | Yes (high) | 0.809    | 0.973        | 25.70            | 81.67       | 743882      | 107774         | 125944       | 3.00   | 82.54%      |
| GPT-5.2 (12-11) (high)  | Yes (high) | 0.807    | 0.992        | 33.85            | 38.35       | 636192      | 39035          | 77897        | 2.20   | 82.52%      |
| GPT-5.1 Codex           | Yes (high) | 0.778    | 0.992        | 31.97            | 38.29       | 610241      | 60480          | 73432        | 1.50   | 79.94%      |
| GPT-5 Mini              | Yes (high) | 0.769    | 0.997        | 51.23            | 52.28       | 636192      | 124352         | 160700       | 0.48   | 79.21%      |
| GPT-5.2 (12-11)         | No         | 0.754    | 1.000        | 16.71            | 39.44       | 636192      | -              | 39537        | 1.67   | 77.89%      |
| GPT-5.1 Codex mini      | Yes (high) | 0.756    | 0.974        | 9.83             | 125.00      | 636192      | 60800          | 73687        | 0.31   | 77.75%      |
| Claude Opus 4.5 Think   | Yes        | 0.681    | 0.962        | 22.78            | 50.87       | 802140      | N/A            | 69535        | 5.75   | 70.94%      |
| Claude Sonnet 4.5 Think | Yes        | 0.644    | 0.989        | 20.16            | 51.66       | 802140      | N/A            | 62474        | 3.34   | 67.82%      |
| GPT-5 Nano              | Yes (high) | 0.627    | 0.994        | 46.74            | 86.49       | 649510      | 208768         | 242562       | 0.13   | 66.34%      |
| Claude Opus 4.5         | No         | 0.622    | 0.982        | 10.43            | 38.32       | 801240      | -              | 23977        | 4.61   | 65.80%      |
| Claude Haiku 4.5        | No         | 0.571    | 0.971        | 4.64             | 74.89       | 801240      | -              | 20831        | 0.91   | 61.13%      |
| Claude Sonnet 4.5       | No         | 0.503    | 0.949        | 8.46             | 37.12       | 801210      | -              | 18843        | 2.69   | 54.76%      |
| Grok 4 (07-09)          | Yes        | 0.380    | 0.958        | 66.46            | 42.72       | 606242      | 138102         | 170368       | 4.37   | 43.75%      |
| Grok 4.1 Fast Reasoning | Yes        | 0.375    | 0.974        | 18.69            | 25.58       | 587687      | 65856          | 28675        | 0.13   | 43.46%      |
| Grok 4.1 Fast           | No         | 0.366    | 0.955        | 5.15             | 70.27       | 588047      | -              | 21694        | 0.13   | 42.52%      |

_Table 2. Overview of the multimodal benchmark results._

> Additional info:  
> Evaluation of benchmark results were performed automatically with the help of evaluation tools based on the LLMs.
> Please refer to the page [LLMs Benchmark Approach](llm-approach.md) for more details on the evaluation methodology.

</details>

## Models specification

| LLM Name                                                                                      | API Provider used in benchmark                                         | Context Window | Cost (Input / Output per MTok)                   | Max Output | Knowledge Cutoff |
|-----------------------------------------------------------------------------------------------|------------------------------------------------------------------------|----------------|--------------------------------------------------|------------|------------------|
| [GPT-5.2 (12-11)](https://platform.openai.com/docs/models/gpt-5.2)                            | OpenAI                                                                 | 400K           | $1.75 / $14.00                                   | 128K       | Aug 31, 2025     |
| [Claude 4.5 Opus](https://www.anthropic.com/news/claude-opus-4-5)                             | Google Vertex AI                                                       | 200K           | $5.00 / $25.00                                   | 64K        | July, 2025       |
| [Claude 4.5 Sonnet](https://www.anthropic.com/news/claude-sonnet-4-5)                         | Google Vertex AI                                                       | 200K           | $3.00 / $15.00                                   | 64K        | July, 2025       |
| [GPT-5.1-Codex](https://platform.openai.com/docs/models/gpt-5.1-codex)                        | OpenAI                                                                 | 400K           | $1.25 / $10.00                                   | 128K       | Sep 30, 2024     |
| [Claude 4.5 Haiku](https://www.anthropic.com/news/claude-haiku-4-5)                           | Google Vertex AI                                                       | 200K           | $1.00 / $5.00                                    | 64K        | July, 2025       |
| [Kimi K2](https://github.com/MoonshotAI/Kimi-K2)                                              | [Fireworks.ai](https://fireworks.ai/models/fireworks/kimi-k2-thinking) | 200K           | $0.60 / $2.50                                    | N/A        | N/A              |
| [Grok 4 (07-09)](https://docs.x.ai/docs/models/grok-4-0709)                                   | xAI Console                                                            | 256K           | $3.00 / $15.00 <= 128K and $6.00 / $30.00 > 128K | N/A        | N/A              |
| [GPT-5 Mini (08-07)](https://platform.openai.com/docs/models/gpt-5-mini)                      | OpenAI                                                                 | 400K           | $0.25 / $2.00                                    | 128K       | May 31, 2024     |
| [Grok Code Fast](https://x.ai/news/grok-code-fast-1)                                          | xAI                                                                    | 256K           | $0.20 / $1.50                                    | N/A        | N/A              |
| [DeepSeek V3.2](https://huggingface.co/deepseek-ai/DeepSeek-V3.2)                             | [Fireworks.ai](https://fireworks.ai/models/fireworks/deepseek-v3p2)    | 128K           | $0.56 / $1.68                                    | N/A        | N/A              |
| [Gemini 3 Pro Preview](https://ai.google.dev/gemini-api/docs/models#gemini-3-pro)             | Google AI Studio                                                       | 1M             | $2.00 / $12.00 <= 200K<br>$4 / $18.00 > 200K     | 65K        | Jan, 2025        |
| [Gemini 3 Flash Preview](https://ai.google.dev/gemini-api/docs/models#gemini-3-flash)         | Google AI Studio                                                       | 1M             | $0.50 / $3.00                                    | 65K        | Jan, 2025        |
| [MiniMax M2.1](https://github.com/MiniMax-AI/MiniMax-M2.1)                                    | [Fireworks.ai](https://fireworks.ai/models/fireworks/minimax-m2)       | 200K           | $0.30 / $1.20                                    | 131K       | N/A              |
| [Grok 4.1 Fast Reasoning/Nonreasoning](https://docs.x.ai/docs/models/grok-4-1-fast-reasoning) | xAI                                                                    | 2M             | $0.20 / $0.50 <= 128K / $0.40 / $1.00 > 128K     | N/A        | N/A              |
| [GPT-5 Nano (08-07)](https://platform.openai.com/docs/models/gpt-5-nano)                      | OpenAI                                                                 | 400K           | $0.05 / $0.40                                    | 128K       | May 31, 2024     |

_Table 3. Description of LLMs, their versions, amount of information to process, and the length of the response._

## Notes

- To learn more about our methodology for evaluating LLMs, please read [LLMs Benchmark Approach](llm-approach.md).
- To submit your model for evaluation, please refer to the [Large Language Model Benchmark Submission](submissions/llm-benchmark-submission.md) page.
- Previous charts with ratings and other scores can be found in the [LLMs Charts archive](/images/llms/llm-charts-archive).

<p align="center">
    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>
