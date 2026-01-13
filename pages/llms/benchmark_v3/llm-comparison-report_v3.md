# LLM's Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                  | Benchmark model ID      | Reasoning  | Execution Date | Code Translation | Code Generation | Code Document | LCIF   | Total Score |
|------------------------|-------------------------|------------|----------------|------------------|-----------------|---------------|--------|-------------|
| GPT52_1211_high        | GPT-5.2 (12-11) (high)  | Yes (high) | 2025-12-12     | 87.33%           | 78.46%          | 81.89%        | 92.50% | 85.05%      |
| Claude_Opus_45         | Claude Opus 4.5         | No         | 2025-11-25     | 82.83%           | 73.96%          | 77.42%        | 98.50% | 83.18%      |
| GPT52_1211             | GPT-5.2 (12-11)         | No         | 2025-12-12     | 84.88%           | 72.85%          | 78.94%        | 92.50% | 82.29%      |
| Claude_Sonnet_45       | Claude Sonnet 4.5       | No         | 2025-09-30     | 77.04%           | 75.92%          | 79.53%        | 96.25% | 82.19%      |
| Claude_Haiku_45        | Claude Haiku 4.5        | No         | 2025-10-16     | 82.63%           | 74.04%          | 80.64%        | 90.00% | 81.83%      |
| Grok4FastReasoning     | Grok 4 Fast             | Yes        | 2025-09-26     | 77.79%           | 80.38%          | 78.39%        | 81.25% | 79.45%      |
| GPT51_Codex            | GPT-5.1 Codex           | Yes (high) | 2025-11-21     | 76.00%           | 79.15%          | 63.47%        | 96.25% | 78.72%      |
| Kimi_K2                | Kimi K2 Thinking        | Yes        | 2025-12-09     | 80.58%           | 69.35%          | 69.25%        | 80.00% | 74.79%      |
| Gemini_3_Pro_Preview   | Gemini 3 Pro Preview    | Yes (high) | 2025-12-18     | 76.04%           | 61.58%          | 60.19%        | 96.25% | 73.52%      |
| Grok4_0709             | Grok 4 (07-09)          | Yes        | 2025-09-11     | 70.63%           | 65.23%          | 64.94%        | 92.50% | 73.33%      |
| Gemini_3_Flash_Preview | Gemini 3 Flash Preview  | Yes        | 2025-12-18     | 77.29%           | 60.85%          | 53.25%        | 98.50% | 72.47%      |
| Grok_Code_0825         | Grok Code Fast          | Yes        | 2025-09-11     | 71.13%           | 56.50%          | 60.83%        | 98.50% | 71.74%      |
| GPT5_Mini_high         | GPT-5 Mini              | Yes (high) | 2025-10-24     | 80.92%           | 70.58%          | 78.64%        | 55.00% | 71.28%      |
| MiniMaxM2              | MiniMax M2              | Yes        | 2025-11-05     | 81.63%           | 73.92%          | 67.78%        | 61.25% | 71.14%      |
| Grok41_FastReasoning   | Grok 4.1 Fast Reasoning | Yes        | 2025-11-21     | 38.08%           | 71.42%          | 70.83%        | 91.25% | 67.90%      |
| DeepSeek_v32           | DeepSeek V3.2           | Yes        | 2025-12-09     | 70.25%           | 64.92%          | 53.53%        | 75.00% | 65.93%      |
| GPT_OSS_120B           | gpt-oss-120b            | Yes (low)  | 2025-09-11     | 76.88%           | 71.54%          | 67.86%        | 32.50% | 62.19%      |
| GPT51_Codex_mini       | GPT-5.1 Codex mini      | Yes (high) | 2025-11-21     | 70.50%           | 53.38%          | 57.42%        | 65.00% | 61.58%      |
| Grok41_Fast            | Grok 4.1 Fast           | No         | 2025-11-21     | 67.17%           | 59.29%          | 57.64%        | 56.25% | 60.09%      |
| GPT5_Nano_high         | GPT-5 Nano              | Yes (high) | 2025-10-24     | 72.08%           | 52.92%          | 66.92%        | 42.50% | 58.61%      |
| AmazonNovaPremier      | Amazon Nova Premier     | No         | 2025-09-11     | 24.54%           | 26.88%          | 22.39%        | 33.75% | 26.89%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT52_1211_high        | 0.845        | 0.902            | 271.16   | 15728.58  | 58.01             | 0.8733  |
| GPT52_1211             | 0.818        | 0.880            | 125.27   | 9685.58   | 77.32             | 0.8488  |
| Claude_Opus_45         | 0.822        | 0.835            | 194.05   | 14298.00  | 73.68             | 0.8283  |
| Claude_Haiku_45        | 0.811        | 0.842            | 70.16    | 14007.83  | 199.65            | 0.8263  |
| MiniMaxM2              | 0.803        | 0.829            | 183.60   | 10530.50  | 57.36             | 0.8163  |
| GPT5_Mini_high         | 0.772        | 0.847            | 262.90   | 16592.33  | 63.11             | 0.8092  |
| Kimi_K2                | 0.770        | 0.842            | 97.60    | 17700.50  | 181.36            | 0.8058  |
| Grok4FastReasoning     | 0.755        | 0.801            | 76.51    | 9506.33   | 124.25            | 0.7779  |
| Gemini_3_Flash_Preview | 0.716        | 0.830            | 69.23    | 10836.50  | 156.53            | 0.7729  |
| Claude_Sonnet_45       | 0.763        | 0.778            | 104.68   | 9619.83   | 91.89             | 0.7704  |
| GPT_OSS_120B           | 0.753        | 0.785            | 9.64     | 6600.25   | 684.50            | 0.7688  |
| Gemini_3_Pro_Preview   | 0.711        | 0.810            | 124.11   | 13725.33  | 110.59            | 0.7604  |
| GPT51_Codex            | 0.742        | 0.778            | 357.05   | 25115.33  | 70.34             | 0.7600  |
| GPT5_Nano_high         | 0.725        | 0.717            | 253.90   | 22961.83  | 90.44             | 0.7208  |
| Grok_Code_0825         | 0.738        | 0.684            | 27.02    | 5852.08   | 216.62            | 0.7113  |
| Grok4_0709             | 0.667        | 0.746            | 188.24   | 9413.75   | 50.01             | 0.7063  |
| GPT51_Codex_mini       | 0.704        | 0.706            | 156.10   | 21590.92  | 138.31            | 0.7050  |
| DeepSeek_v32           | 0.685        | 0.720            | 267.59   | 6318.58   | 23.61             | 0.7025  |
| Grok41_Fast            | 0.680        | 0.663            | 51.49    | 5469.50   | 106.22            | 0.6717  |
| Grok41_FastReasoning   | 0.330        | 0.432            | 119.26   | 2397.58   | 20.10             | 0.3808  |
| AmazonNovaPremier      | 0.303        | 0.188            | 18.65    | 1065.92   | 57.17             | 0.2454  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Grok4FastReasoning     | 0.812        | 0.796            | 53.90    | 7660.62   | 142.13            | 0.8038  |
| GPT51_Codex            | 0.821        | 0.762            | 480.27   | 17801.92  | 37.07             | 0.7915  |
| GPT52_1211_high        | 0.797        | 0.772            | 138.98   | 13785.00  | 99.19             | 0.7846  |
| Claude_Sonnet_45       | 0.758        | 0.760            | 173.16   | 16989.00  | 98.11             | 0.7592  |
| Claude_Haiku_45        | 0.718        | 0.762            | 88.17    | 18798.62  | 213.22            | 0.7404  |
| Claude_Opus_45         | 0.737        | 0.742            | 252.35   | 19200.15  | 76.08             | 0.7396  |
| MiniMaxM2              | 0.732        | 0.747            | 432.02   | 9330.92   | 21.60             | 0.7392  |
| GPT52_1211             | 0.758        | 0.699            | 66.32    | 7025.23   | 105.93            | 0.7285  |
| GPT_OSS_120B           | 0.723        | 0.708            | 8.89     | 4849.08   | 545.55            | 0.7154  |
| Grok41_FastReasoning   | 0.737        | 0.692            | 97.55    | 5163.54   | 52.93             | 0.7142  |
| GPT5_Mini_high         | 0.732        | 0.680            | 288.81   | 15851.31  | 54.88             | 0.7058  |
| Kimi_K2                | 0.678        | 0.708            | 129.74   | 15785.69  | 121.67            | 0.6935  |
| Grok4_0709             | 0.705        | 0.600            | 83.24    | 3994.92   | 47.99             | 0.6523  |
| DeepSeek_v32           | 0.655        | 0.644            | 124.14   | 6298.92   | 50.74             | 0.6492  |
| Gemini_3_Pro_Preview   | 0.625        | 0.607            | 77.91    | 8456.23   | 108.54            | 0.6158  |
| Gemini_3_Flash_Preview | 0.632        | 0.585            | 40.97    | 6145.69   | 150.00            | 0.6085  |
| Grok41_Fast            | 0.623        | 0.563            | 41.83    | 4341.85   | 103.81            | 0.5929  |
| Grok_Code_0825         | 0.640        | 0.490            | 21.92    | 3548.92   | 161.89            | 0.5650  |
| GPT51_Codex_mini       | 0.563        | 0.505            | 96.64    | 13013.62  | 134.67            | 0.5338  |
| GPT5_Nano_high         | 0.595        | 0.464            | 210.25   | 19960.23  | 94.94             | 0.5292  |
| AmazonNovaPremier      | 0.324        | 0.214            | 20.18    | 1229.85   | 60.94             | 0.2688  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT52_1211_high        | 0.782        | 0.856            | 101.32   | 6495.50   | 64.11             | 0.8189  |
| Claude_Haiku_45        | 0.797        | 0.816            | 87.10    | 12775.56  | 146.67            | 0.8064  |
| Claude_Sonnet_45       | 0.789        | 0.801            | 144.31   | 8927.11   | 61.86             | 0.7953  |
| GPT52_1211             | 0.763        | 0.816            | 85.13    | 5617.28   | 65.98             | 0.7894  |
| GPT5_Mini_high         | 0.752        | 0.821            | 254.90   | 13588.78  | 53.31             | 0.7864  |
| Grok4FastReasoning     | 0.742        | 0.826            | 47.47    | 5420.00   | 114.18            | 0.7839  |
| Claude_Opus_45         | 0.739        | 0.809            | 162.00   | 10124.11  | 62.49             | 0.7742  |
| Grok41_FastReasoning   | 0.704        | 0.713            | 37.37    | 2592.17   | 69.37             | 0.7083  |
| Kimi_K2                | 0.687        | 0.698            | 49.54    | 5363.06   | 108.26            | 0.6925  |
| GPT_OSS_120B           | 0.671        | 0.687            | 9.53     | 4538.89   | 476.33            | 0.6786  |
| MiniMaxM2              | 0.642        | 0.714            | 139.60   | 4420.17   | 31.66             | 0.6778  |
| GPT5_Nano_high         | 0.646        | 0.693            | 179.79   | 13767.06  | 76.57             | 0.6692  |
| Grok4_0709             | 0.671        | 0.628            | 83.55    | 3292.06   | 39.40             | 0.6494  |
| GPT51_Codex            | 0.612        | 0.658            | 73.23    | 3496.17   | 47.74             | 0.6347  |
| Grok_Code_0825         | 0.586        | 0.631            | 25.03    | 3281.06   | 131.09            | 0.6083  |
| Gemini_3_Pro_Preview   | 0.593        | 0.611            | 59.49    | 5267.50   | 88.55             | 0.6019  |
| Grok41_Fast            | 0.552        | 0.601            | 22.38    | 2054.22   | 91.81             | 0.5764  |
| GPT51_Codex_mini       | 0.536        | 0.613            | 22.76    | 2861.39   | 125.71            | 0.5742  |
| DeepSeek_v32           | 0.512        | 0.559            | 174.16   | 2769.89   | 15.90             | 0.5353  |
| Gemini_3_Flash_Preview | 0.511        | 0.554            | 30.97    | 3389.94   | 109.47            | 0.5325  |
| AmazonNovaPremier      | 0.238        | 0.210            | 25.93    | 865.61    | 33.39             | 0.2239  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                  | Hard Accuracy | Hard Completeness | Light Accuracy | Light Completeness | Score ↓ |
|------------------------|---------------|-------------------|----------------|--------------------|---------|
| Grok_Code_0825         | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Claude_Opus_45         | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Gemini_3_Flash_Preview | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Claude_Sonnet_45       | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Gemini_3_Pro_Preview   | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| GPT51_Codex            | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Grok4_0709             | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT52_1211             | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT52_1211_high        | 3             | 4                 | 4              | 4                  | 0.925   |
| Grok41_FastReasoning   | 3.5           | 4                 | 3              | 4                  | 0.9125  |
| Claude_Haiku_45        | 3             | 4                 | 3.5            | 4                  | 0.9     |
| Grok4FastReasoning     | 2.5           | 3                 | 4              | 4                  | 0.8125  |
| Kimi_K2                | 3             | 3                 | 3.5            | 3.5                | 0.8     |
| DeepSeek_v32           | 2             | 3                 | 3.75           | 3.75               | 0.75    |
| GPT51_Codex_mini       | 3             | 2                 | 2.5            | 3                  | 0.65    |
| MiniMaxM2              | 2             | 1.5               | 3.5            | 3.5                | 0.6125  |
| Grok41_Fast            | 2             | 1.5               | 3              | 3                  | 0.5625  |
| GPT5_Mini_high         | 1             | 1                 | 4              | 4                  | 0.55    |
| GPT5_Nano_high         | 0             | 1                 | 3.5            | 3.5                | 0.425   |
| AmazonNovaPremier      | 0             | 1                 | 2.5            | 2.75               | 0.3375  |
| GPT_OSS_120B           | 0             | 0                 | 3.5            | 3                  | 0.325   |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal significant insights about current LLM capabilities for software engineering tasks:

**Market Leadership**
GPT-5.2 (12-11) establishes a new benchmark record with 85.05% total score (high reasoning variant) and 82.29% (regular variant), surpassing GPT-5.1 (83.96%/83.36%). The model features the most recent
knowledge cutoff (Aug 31, 2025) and updated pricing ($1.75/$14.00 per MTok). The high reasoning variant achieves balanced performance across all categories (code translation: 87.33%, code generation:
78.46%, documentation: 81.89%, LCIF: 92.50%). The regular variant delivers solid performance with better efficiency (64.96 min execution vs. 114.74 min, 79.19 tokens/sec vs. 70.43
tokens/sec, $4.87 cost vs. $7.34), demonstrating that extended reasoning provides meaningful improvement (+2.76 percentage points) with reasonable cost increase. Compared to GPT-5.1, GPT-5.2 high
reasoning executes faster (114.74 min vs. 171.48 min) while achieving higher scores.

Claude Opus 4.5 achieves 83.18% total score, representing Anthropic's first cross-platform flagship model available on all major cloud providers (Google Vertex AI, Azure, AWS, Anthropic API). Strong
performance across categories (code translation: 82.83%, code generation: 73.96%, documentation: 77.42%, LCIF: 98.50%). Execution time 142.09 min at $17.08 cost. Pricing reduced from $15/$75 to $5/$25
per MTok, making the flagship model significantly more accessible.

Claude Sonnet 4.5 achieves 82.19% total score with balanced performance across all categories without requiring reasoning mode. Strong code documentation (79.53%), code generation (75.92%), and
excellent LCIF (96.25%). Suggests Anthropic has integrated reasoning capabilities directly into base architecture.

Claude Haiku 4.5 achieves 81.83% total score while representing Anthropic's smaller, cost-effective model tier. Strong code documentation (80.64%), code translation (82.63%), and code generation (
74.04%). With exceptional speed (180.66 T/S) and competitive pricing ($1/$5 per MTok), ideal for high-volume coding applications.

**OpenAI Model Tiers**
GPT-5.2 leads with benchmark-record performance (85.05% high, 82.29% regular). GPT-5.1 Codex (78.72%) is a specialized coding model with strong code generation (79.15%) and excellent LCIF (96.25%),
but experiences significant operational issues: extremely slow LCIF execution (~90 min vs typical 10 min) and frequent tool call errors with repeated file reads/writes. Performs better in multimodal
tasks (79.94%) where tool handling limitations are less critical. GPT-5.1 Codex mini (61.58%) shows similar tool handling issues but outperforms in multimodal benchmark (77.75%). GPT-5 Mini (71.28%)
demonstrates strong code translation (80.92%) and documentation (78.64%) despite weak LCIF (55%). GPT-5 Nano (58.61%) offers ultra-low-cost operations ($0.33) but with significant limitations -
dedicates ~95% of output tokens to reasoning rather than actual output, causing LCIF failure (42.50%).

**Anthropic's Model Evolution**
The Claude model family shows remarkable evolution across both flagship and smaller model tiers. Claude Sonnet 4.5 (82.19%) represents a significant leap over Claude 4 Sonnet (75.68%), with
improvements across all coding categories. Claude Haiku 4.5 demonstrates that Anthropic has successfully brought flagship-level capabilities to smaller models, achieving 81.83% score with Sonnet-like
behavior and quality while maintaining exceptional speed and cost-effectiveness. The data reveals that reasoning mode consistently reduces coding performance across the Claude 4 line (base: 75.68% vs.
thinking: 73.73%), while both Claude Sonnet 4.5 and Haiku 4.5 achieve top performance without requiring reasoning mode. This suggests Anthropic has successfully integrated advanced reasoning
capabilities directly into the base architecture across their model lineup, eliminating the performance penalty previously associated with explicit
reasoning modes.

**xAI's Competitive Performance and Efficiency Breakthrough**
xAI demonstrates significant advancement with Grok 4 Fast achieving 79.45% score, positioning it as a strong contender in the coding benchmark. This model delivers exceptional cost-effectiveness
at $0.22 with faster execution time (41.22 min vs. 80.75 min for Grok 4), while maintaining excellent performance across categories. The original Grok 4 (07-09) achieves 73.33% score with solid
performance, while Grok Code Fast delivers 71.74% score with exceptional speed (165.54 tokens/sec) and outstanding cost efficiency ($0.33 total cost). Grok Code Fast particularly excels in LCIF tasks
(98.5% score), making xAI's models excellent choices for budget-conscious organizations requiring fast development cycles.

However, Grok 4.1 models show concerning regression. Grok 4.1 Fast Reasoning (67.90%) suffers from a response truncation bug where the model generates reasoning tokens but then abruptly truncates
output after 15-50 tokens with 200 OK status, causing low completeness (0.628) particularly on large contexts. This results in critically poor code translation (38.08%) while maintaining acceptable
code generation (71.42%), documentation (70.83%), and LCIF (91.25%). Grok 4.1 Fast (60.09%) performs below its predecessor Grok 4 Fast (79.45%) despite version upgrade, requiring multiple LCIF
attempts to achieve passing results. Both 4.1 variants demonstrate that newer versions do not guarantee improvements. Grok 4 Fast's 2M token context window and state-of-the-art cost-efficiency make it
ideal for large-scale software engineering projects.

**Google's Token-Efficient Gemini 3 Architecture**
Google trained Gemini 3 models for token efficiency with concise, direct outputs by default. System prompt engineering was required to achieve current coding benchmark results.

Gemini 3 Pro Preview achieves 73.52% in coding tasks with excellent LCIF (96.25%, tied 2nd) and strong code translation (76.04%). The token-efficient design yields moderate code documentation (60.19%)
and generation (61.58%) despite prompt optimization. Execution time 59.55 min at 103.40 T/S for $5.22 cost, with pricing at $2/$12 for <200K context.

Gemini 3 Flash Preview achieves 72.47% with exceptional speed (32.01 min, 141.06 T/S) and very low cost ($1.01). Demonstrates excellent LCIF performance (98.50%, tied 1st) and strong code
translation (77.29%). Similar token efficiency characteristics result in moderate documentation (53.25%) and generation (60.85%) scores. Offers best value proposition for cost-sensitive deployments.

Both models excel in multimodal tasks where concise outputs align with their design philosophy - Gemini 3 Flash Preview leads multimodal benchmark at 83.35% (#1), while Gemini 3 Pro Preview achieves
82.54% (#2), significantly outperforming their coding results.

**Open-Source Models**
Kimi K2 Thinking (74.79%) leads open-source models with strong code translation (80.58%) and solid LCIF (80.00%). Excellent speed (137.12 T/S) and reasonable execution (62.49 min) at mid-tier cost ($
1.48). Weaker in code generation (69.35%) and documentation (69.25%).

MiniMax M2 (71.14%) utilizes efficient MoE architecture (230B total, 10B active) with excellent code translation (81.63%) and agentic task capabilities. Struggles with LCIF (61.25%) and large content
generation. Slower execution (172.20 min, 31.67 T/S) at $0.49 cost.

DeepSeek V3.2 (65.93%) has the slowest execution (132.66 min, 26.08 T/S) but maintains ultra-low cost ($0.53). Moderate performance across categories with weak documentation (53.53%). Suitable for
organizations with less time-sensitive requirements.

gpt-oss-120b achieves 62.19% score with extraordinary speed (555.99 tokens/sec) and ultra-low cost ($0.23), completing all tasks in just 6.71 minutes. While Kimi K2 and MiniMax M2 offer better
quality, gpt-oss-120b provides fastest execution and lowest costs, demonstrating that open-source alternatives can deliver competitive performance for organizations seeking cost-effective solutions.

**Key Performance Insights**

- **Speed Champions**: gpt-oss-120b (555.99 T/S), Claude Haiku 4.5 (180.66 T/S), Grok Code Fast (165.54 T/S), Gemini 3 Flash Preview (141.06 T/S), Grok 4 Fast (125.84 T/S)
- **Cost-Effectiveness Leaders**: Grok 4 Fast ($0.22), gpt-oss-120b ($0.23), GPT-5 Nano ($0.33), Grok Code Fast ($0.33), MiniMax M2 ($0.49), Gemini 3 Flash Preview ($1.01)
- **LCIF Excellence**: Grok Code Fast (98.5%), Claude Opus 4.5 (98.5%), Gemini 3 Flash Preview (98.5%), Claude Sonnet 4.5 (96.25%), Gemini 3 Pro Preview (96.25%), GPT-5.1 Codex (96.25%)
- **Code Translation Leaders**: GPT-5.2 (12-11) (high) (87.33%), GPT-5.2 (12-11) (84.88%), Claude Opus 4.5 (82.83%), Claude Haiku 4.5 (82.63%), MiniMax M2 (81.63%)
- **Code Generation Leaders**: Grok 4 Fast (80.38%), GPT-5.1 Codex (79.15%), GPT-5.2 (12-11) (high) (78.46%), Claude Sonnet 4.5 (75.92%), Claude Haiku 4.5 (74.04%)
- **Code Documentation Leaders**: GPT-5.2 (12-11) (high) (81.89%), Claude Haiku 4.5 (80.64%), Claude Sonnet 4.5 (79.53%), GPT-5.2 (12-11) (78.94%), GPT-5 Mini (78.64%)

**Organizations Recommendations**

- **Maximum Quality**: GPT-5.2 (12-11) (high) for top overall coding performance (85.05%), GPT-5.2 regular for excellent quality/cost balance (82.29%, $4.87)
- **Cross-Platform Excellence**: Claude Opus 4.5 (83.18%) for organizations requiring availability across all major cloud providers, with reduced pricing ($5/$25 per MTok)
- **High-Performance Budget Option**: Claude Haiku 4.5 for premium performance at mid-tier pricing (81.83%), excellent for high-volume coding applications with strong code documentation (80.64%)
- **Balanced Performance**: GPT-5.2 (12-11) offers the best balance of quality and capability across all coding categories (82.29%), Claude Sonnet 4.5 for strong balanced performance (82.19%)
- **Cost-Effective Excellence**: Grok 4 Fast for outstanding performance with exceptional cost efficiency ($0.22), GPT-5 Mini ($1.38) for mid-tier cost-effective
- **Speed & Budget**: Grok Code Fast for rapid development cycles with minimal expenses, Claude Haiku 4.5 for speed with quality, gpt-oss-120b for fastest execution
- **Open-Source**: Kimi K2 Thinking for top open-source performance (74.79%, strong code translation), MiniMax M2 for agentic tasks (71.14%, excellent code translation), gpt-oss-120b for
  speed-critical and budget-constrained deployments

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>