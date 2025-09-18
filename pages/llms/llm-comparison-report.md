# LLM's Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                    | Benchmark model ID         | Execution Date | Code Translation | Code Generation | Code Document | LCIF   | Total Score |
|--------------------------|----------------------------|----------------|------------------|-----------------|---------------|--------|-------------|
| GPT5_0807                | GPT-5 (08-07)              | 2025-09-05     | 84.79%           | 78.92%          | 79.81%        | 85.00% | 82.13%      |
| Claude_Sonnet_4          | Claude 4 Sonnet            | 2025-09-11     | 79.08%           | 74.65%          | 52.72%        | 96.25% | 75.68%      |
| Claude_Sonnet_4_Thinking | Claude 4 Sonnet (Thinking) | 2025-09-11     | 72.25%           | 72.81%          | 53.61%        | 96.25% | 73.73%      |
| Grok4_0709               | Grok 4 (07-09)             | 2025-09-11     | 70.63%           | 65.23%          | 64.94%        | 92.50% | 73.33%      |
| Grok_Code_0825           | Grok Code Fast             | 2025-09-11     | 71.13%           | 56.50%          | 60.83%        | 98.50% | 71.74%      |
| Gemini_25_Pro            | Gemini 2.5 Pro             | 2025-09-11     | 78.38%           | 55.15%          | 51.67%        | 77.50% | 65.67%      |
| GPT_OSS_120B             | gpt-oss-120b               | 2025-09-11     | 76.88%           | 71.54%          | 67.86%        | 32.50% | 62.19%      |
| Gemini_25_Flash          | Gemini 2.5 Flash           | 2025-09-11     | 77.96%           | 70.81%          | 53.06%        | 40.00% | 60.46%      |
| AmazonNovaPremier        | Amazon Nova Premier        | 2025-09-11     | 24.54%           | 26.88%          | 22.39%        | 33.75% | 26.89%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                    | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|--------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT5_0807                | 0.828        | 0.868            | 178.40   | 8836.92   | 49.53             | 0.8479  |
| Claude_Sonnet_4          | 0.771        | 0.811            | 103.56   | 9547.42   | 92.19             | 0.7908  |
| Gemini_25_Pro            | 0.737        | 0.831            | 135.12   | 15917.25  | 117.80            | 0.7838  |
| Gemini_25_Flash          | 0.749        | 0.810            | 96.89    | 19269.33  | 198.88            | 0.7796  |
| GPT_OSS_120B             | 0.753        | 0.785            | 9.64     | 6600.25   | 684.50            | 0.7688  |
| Claude_Sonnet_4_Thinking | 0.706        | 0.739            | 90.78    | 8085.17   | 89.06             | 0.7225  |
| Grok_Code_0825           | 0.738        | 0.684            | 27.02    | 5852.08   | 216.62            | 0.7113  |
| Grok4_0709               | 0.667        | 0.746            | 188.24   | 9413.75   | 50.01             | 0.7063  |
| AmazonNovaPremier        | 0.303        | 0.188            | 18.65    | 1065.92   | 57.17             | 0.2454  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                    | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|--------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT5_0807                | 0.840        | 0.738            | 115.78   | 7745.23   | 66.90             | 0.7892  |
| Claude_Sonnet_4          | 0.728        | 0.765            | 130.09   | 12419.15  | 95.46             | 0.7465  |
| Claude_Sonnet_4_Thinking | 0.742        | 0.715            | 129.55   | 12058.62  | 93.08             | 0.7281  |
| GPT_OSS_120B             | 0.723        | 0.708            | 8.89     | 4849.08   | 545.55            | 0.7154  |
| Gemini_25_Flash          | 0.722        | 0.695            | 88.52    | 16725.69  | 188.95            | 0.7081  |
| Grok4_0709               | 0.705        | 0.600            | 83.24    | 3994.92   | 47.99             | 0.6523  |
| Grok_Code_0825           | 0.640        | 0.490            | 21.92    | 3548.92   | 161.89            | 0.5650  |
| Gemini_25_Pro            | 0.592        | 0.511            | 76.70    | 8157.85   | 106.36            | 0.5515  |
| AmazonNovaPremier        | 0.324        | 0.214            | 20.18    | 1229.85   | 60.94             | 0.2688  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                    | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|--------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT5_0807                | 0.754        | 0.842            | 105.88   | 5149.94   | 48.64             | 0.7981  |
| GPT_OSS_120B             | 0.671        | 0.687            | 9.53     | 4538.89   | 476.33            | 0.6786  |
| Grok4_0709               | 0.671        | 0.628            | 83.55    | 3292.06   | 39.40             | 0.6494  |
| Grok_Code_0825           | 0.586        | 0.631            | 25.03    | 3281.06   | 131.09            | 0.6083  |
| Claude_Sonnet_4_Thinking | 0.519        | 0.553            | 59.27    | 3520.78   | 59.40             | 0.5361  |
| Gemini_25_Flash          | 0.491        | 0.570            | 104.69   | 13906.56  | 132.84            | 0.5306  |
| Claude_Sonnet_4          | 0.517        | 0.537            | 51.15    | 3065.00   | 59.92             | 0.5272  |
| Gemini_25_Pro            | 0.501        | 0.533            | 67.08    | 6329.89   | 94.36             | 0.5167  |
| AmazonNovaPremier        | 0.238        | 0.210            | 25.93    | 865.61    | 33.39             | 0.2239  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                    | Hard Accuracy | Hard Completeness | Light Accuracy | Light Completeness | Score ↓ |
|--------------------------|---------------|-------------------|----------------|--------------------|---------|
| Grok_Code_0825           | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Claude_Sonnet_4          | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Claude_Sonnet_4_Thinking | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Grok4_0709               | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT5_0807                | 3             | 3                 | 4              | 4                  | 0.85    |
| Gemini_25_Pro            | 3             | 2                 | 4              | 4                  | 0.775   |
| Gemini_25_Flash          | 0             | 0                 | 4              | 4                  | 0.4     |
| AmazonNovaPremier        | 0             | 1                 | 2.5            | 2.75               | 0.3375  |
| GPT_OSS_120B             | 0             | 0                 | 3.5            | 3                  | 0.325   |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal significant insights about current LLM capabilities for software engineering tasks:

**Market Leadership**
GPT-5 (08-07) establishes clear dominance in the coding benchmark v3, achieving 82.13% total score with exceptional code translation performance (84.79%). This represents OpenAI's continued leadership in software engineering tasks, demonstrating superior accuracy (0.800) and completeness (0.818) across all categories.

**Anthropic's Strong Position**
Claude 4 Sonnet secures second place with 75.68% score, outperforming its Thinking mode variant (73.73%). Notably, the base Sonnet model proves more effective for coding tasks, contradicting the assumption that reasoning modes always improve performance. Claude demonstrates balanced capabilities with moderate execution time (64.24 min) and reasonable cost efficiency ($6.17).

**xAI's Competitive Performance**
Grok 4 (07-09) achieves 73.33% score with solid performance across categories, while Grok Code Fast delivers 71.74% score with exceptional speed (165.54 tokens/sec) and outstanding cost efficiency ($0.33 total cost). Grok Code Fast particularly excels in LCIF tasks (98.5% score), making it an excellent choice for budget-conscious organizations requiring fast development cycles.

**Google's Mixed Results**
Gemini models show varying performance: Gemini 2.5 Pro achieves 65.67% with high token generation (410,997 tokens) but struggles with accuracy, while Gemini 2.5 Flash scores 60.46% despite impressive speed (166.51 tokens/sec). Both models demonstrate strength in multimodal tasks but face challenges in pure coding scenarios.

**Open-Source Breakthrough**
gpt-oss-120b represents a significant milestone for open-source models, achieving 62.19% score with extraordinary speed (555.99 tokens/sec) and ultra-low cost ($0.23). The model completes all tasks in just 6.71 minutes, demonstrating that open-source alternatives can deliver competitive performance for organizations seeking cost-effective solutions.

**Key Performance Insights**
- **Speed Champions**: gpt-oss-120b (555.99 T/S), Grok Code Fast (165.54 T/S), Gemini 2.5 Flash (166.51 T/S)
- **Cost-Effectiveness Leaders**: gpt-oss-120b ($0.23), Grok Code Fast ($0.33), Amazon Nova Premier ($1.12)
- **LCIF Excellence**: Grok Code Fast (98.5%), Claude models (96.25%), Grok 4 (92.5%)
- **Code Translation Leaders**: GPT-5 (84.79%), Claude 4 Sonnet (79.08%), Gemini 2.5 Pro (78.38%)

**Organizations Recommendations**
- **Maximum Quality**: GPT-5 (08-07) for mission-critical code translation and generation
- **Balanced Performance**: Claude 4 Sonnet for comprehensive coding assistance with reasonable costs
- **Speed & Budget**: Grok Code Fast for rapid development cycles with minimal expenses
- **Open-Source**: gpt-oss-120b for local deployment and privacy-focused organizations


<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>