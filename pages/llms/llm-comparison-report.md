# LLM's Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google DeepMind, xAI and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                  | Benchmark model ID      | Reasoning  | Execution Date | Code Translation | Code Generation | Code Document | LCIF   | Total Score |
|------------------------|-------------------------|------------|----------------|------------------|-----------------|---------------|--------|-------------|
| GPT52_1211_high        | GPT-5.2 (12-11) (high)  | Yes (high) | 2025-12-24     | 85.33%           | 81.42%          | 82.86%        | 92.50% | 85.53%      |
| Claude_Opus_45_high    | Claude Opus 4.5 Think   | Yes        | 2026-01-12     | 83.25%           | 76.62%          | 82.89%        | 98.50% | 85.31%      |
| Claude_Opus_45         | Claude Opus 4.5         | No         | 2026-01-09     | 82.92%           | 78.27%          | 81.03%        | 98.50% | 85.18%      |
| GPT52_1211             | GPT-5.2 (12-11)         | No         | 2025-12-24     | 82.96%           | 80.27%          | 82.72%        | 92.50% | 84.61%      |
| Claude_Sonnet_45_high  | Claude Sonnet 4.5 Think | Yes        | 2026-01-12     | 77.58%           | 76.50%          | 85.31%        | 96.25% | 83.91%      |
| Claude_Sonnet_45       | Claude Sonnet 4.5       | No         | 2026-01-08     | 75.96%           | 76.15%          | 84.06%        | 96.25% | 83.10%      |
| GPT51_Codex            | GPT-5.1 Codex           | Yes (high) | 2026-01-08     | 78.17%           | 78.00%          | 76.64%        | 96.25% | 82.26%      |
| Claude_Haiku_45        | Claude Haiku 4.5        | No         | 2026-01-08     | 74.50%           | 73.38%          | 80.42%        | 90.00% | 79.58%      |
| Kimi_K2                | Kimi K2 Thinking        | Yes        | 2026-01-08     | 78.38%           | 76.27%          | 79.19%        | 80.00% | 78.46%      |
| Grok4_0709             | Grok 4 (07-09)          | Yes        | 2026-01-08     | 70.33%           | 69.27%          | 64.81%        | 92.50% | 74.23%      |
| GPT5_Mini_high         | GPT-5 Mini              | Yes (high) | 2026-01-08     | 79.71%           | 74.12%          | 83.86%        | 55.00% | 73.17%      |
| DeepSeek_v32           | DeepSeek V3.2           | Yes        | 2026-01-08     | 73.96%           | 72.15%          | 68.97%        | 75.00% | 72.52%      |
| Grok_Code_0825         | Grok Code Fast          | Yes        | 2026-01-08     | 67.75%           | 64.35%          | 61.42%        | 93.50% | 71.75%      |
| Gemini_3_Pro_Preview   | Gemini 3 Pro Preview    | Yes (high) | 2025-12-24     | 71.88%           | 61.19%          | 54.44%        | 92.50% | 70.00%      |
| GPT51_Codex_mini       | GPT-5.1 Codex mini      | Yes (high) | 2026-01-08     | 77.71%           | 61.88%          | 73.22%        | 65.00% | 69.45%      |
| Gemini_3_Flash_Preview | Gemini 3 Flash Preview  | Yes        | 2025-12-24     | 70.50%           | 56.62%          | 50.00%        | 96.25% | 68.34%      |
| MiniMax_M21            | MiniMax M2.1            | Yes        | 2026-01-08     | 70.13%           | 59.88%          | 79.67%        | 61.25% | 67.73%      |
| Grok41_FastReasoning   | Grok 4.1 Fast Reasoning | Yes        | 2026-01-08     | 20.33%           | 66.00%          | 75.33%        | 91.25% | 63.23%      |
| Grok41_Fast            | Grok 4.1 Fast           | No         | 2026-01-08     | 66.00%           | 59.58%          | 66.83%        | 56.25% | 62.17%      |
| GPT5_Nano_high         | GPT-5 Nano              | Yes (high) | 2026-01-08     | 68.21%           | 53.27%          | 71.78%        | 35.00% | 57.06%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT52_1211_high        | 0.810        | 0.897            | 224.35   | 18292.75  | 81.54             | 0.8533  |
| Claude_Opus_45_high    | 0.806        | 0.859            | 244.46   | 18028.17  | 73.75             | 0.8325  |
| GPT52_1211             | 0.789        | 0.870            | 115.80   | 13278.75  | 114.67            | 0.8296  |
| Claude_Opus_45         | 0.807        | 0.852            | 229.45   | 17100.00  | 74.52             | 0.8292  |
| GPT5_Mini_high         | 0.741        | 0.853            | 280.85   | 18084.08  | 64.39             | 0.7971  |
| Kimi_K2                | 0.749        | 0.818            | 103.44   | 17580.33  | 169.95            | 0.7838  |
| GPT51_Codex            | 0.742        | 0.822            | 495.06   | 39962.58  | 80.72             | 0.7817  |
| GPT51_Codex_mini       | 0.740        | 0.814            | 356.54   | 42905.25  | 120.34            | 0.7771  |
| Claude_Sonnet_45_high  | 0.751        | 0.801            | 176.86   | 15196.67  | 85.92             | 0.7758  |
| Claude_Sonnet_45       | 0.743        | 0.776            | 160.50   | 14257.25  | 88.83             | 0.7596  |
| Claude_Haiku_45        | 0.733        | 0.757            | 89.39    | 17842.50  | 199.59            | 0.7450  |
| DeepSeek_v32           | 0.697        | 0.783            | 208.24   | 11630.42  | 55.85             | 0.7396  |
| Gemini_3_Pro_Preview   | 0.653        | 0.785            | 116.17   | 13114.33  | 112.89            | 0.7188  |
| Gemini_3_Flash_Preview | 0.652        | 0.758            | 44.72    | 8079.50   | 180.69            | 0.7050  |
| Grok4_0709             | 0.646        | 0.761            | 203.87   | 11472.75  | 56.27             | 0.7033  |
| MiniMax_M21            | 0.717        | 0.686            | 94.59    | 13107.25  | 138.57            | 0.7013  |
| GPT5_Nano_high         | 0.650        | 0.714            | 171.29   | 25463.58  | 148.66            | 0.6821  |
| Grok_Code_0825         | 0.631        | 0.724            | 99.38    | 9526.58   | 95.86             | 0.6775  |
| Grok41_Fast            | 0.679        | 0.641            | 29.71    | 6570.83   | 221.15            | 0.6600  |
| Grok41_FastReasoning   | 0.192        | 0.215            | 67.65    | 11125.00  | 164.45            | 0.2033  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT52_1211_high        | 0.802        | 0.827            | 322.63   | 20894.77  | 64.76             | 0.8142  |
| GPT52_1211             | 0.815        | 0.791            | 152.82   | 14923.92  | 97.66             | 0.8027  |
| Claude_Opus_45         | 0.784        | 0.782            | 495.04   | 38363.54  | 77.50             | 0.7827  |
| GPT51_Codex            | 0.789        | 0.771            | 368.28   | 33874.77  | 91.98             | 0.7800  |
| Claude_Opus_45_high    | 0.764        | 0.768            | 508.25   | 38713.92  | 76.17             | 0.7662  |
| Claude_Sonnet_45_high  | 0.772        | 0.758            | 282.90   | 26806.38  | 94.75             | 0.7650  |
| Kimi_K2                | 0.742        | 0.783            | 101.42   | 18483.00  | 182.24            | 0.7627  |
| Claude_Sonnet_45       | 0.766        | 0.757            | 303.43   | 29641.92  | 97.69             | 0.7615  |
| GPT5_Mini_high         | 0.738        | 0.744            | 303.58   | 19367.08  | 63.80             | 0.7412  |
| Claude_Haiku_45        | 0.709        | 0.758            | 152.86   | 32930.46  | 215.42            | 0.7338  |
| DeepSeek_v32           | 0.723        | 0.720            | 173.73   | 17780.23  | 102.35            | 0.7215  |
| Grok4_0709             | 0.685        | 0.701            | 129.52   | 6293.85   | 48.59             | 0.6927  |
| Grok41_FastReasoning   | 0.664        | 0.656            | 72.57    | 12955.69  | 178.52            | 0.6600  |
| Grok_Code_0825         | 0.642        | 0.645            | 76.08    | 5777.54   | 75.94             | 0.6435  |
| GPT51_Codex_mini       | 0.609        | 0.628            | 173.26   | 22360.38  | 129.06            | 0.6188  |
| Gemini_3_Pro_Preview   | 0.619        | 0.605            | 74.21    | 7703.00   | 103.81            | 0.6119  |
| MiniMax_M21            | 0.622        | 0.576            | 75.70    | 12949.31  | 171.05            | 0.5988  |
| Grok41_Fast            | 0.624        | 0.568            | 32.33    | 6715.23   | 207.68            | 0.5958  |
| Gemini_3_Flash_Preview | 0.579        | 0.553            | 32.39    | 5416.38   | 167.23            | 0.5662  |
| GPT5_Nano_high         | 0.570        | 0.495            | 199.06   | 21545.62  | 108.24            | 0.5327  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Claude_Sonnet_45_high  | 0.843        | 0.863            | 363.62   | 23469.17  | 64.54             | 0.8531  |
| Claude_Sonnet_45       | 0.826        | 0.855            | 351.10   | 23421.44  | 66.71             | 0.8406  |
| GPT5_Mini_high         | 0.824        | 0.853            | 214.17   | 15967.22  | 74.56             | 0.8386  |
| Claude_Opus_45_high    | 0.811        | 0.847            | 272.06   | 16949.44  | 62.30             | 0.8289  |
| GPT52_1211_high        | 0.817        | 0.840            | 131.60   | 7709.61   | 58.59             | 0.8286  |
| GPT52_1211             | 0.807        | 0.847            | 98.77    | 6614.89   | 66.97             | 0.8272  |
| Claude_Opus_45         | 0.799        | 0.821            | 250.73   | 15946.61  | 63.60             | 0.8103  |
| Claude_Haiku_45        | 0.781        | 0.827            | 166.74   | 25545.00  | 153.20            | 0.8042  |
| MiniMax_M21            | 0.798        | 0.796            | 87.57    | 8509.72   | 97.18             | 0.7967  |
| Kimi_K2                | 0.775        | 0.809            | 67.21    | 8785.94   | 130.72            | 0.7919  |
| GPT51_Codex            | 0.747        | 0.786            | 65.37    | 6430.11   | 98.37             | 0.7664  |
| Grok41_FastReasoning   | 0.760        | 0.747            | 29.00    | 4169.33   | 143.79            | 0.7533  |
| GPT51_Codex_mini       | 0.733        | 0.732            | 38.16    | 5001.50   | 131.06            | 0.7322  |
| GPT5_Nano_high         | 0.671        | 0.765            | 124.50   | 15638.28  | 125.61            | 0.7178  |
| DeepSeek_v32           | 0.663        | 0.717            | 56.65    | 5790.33   | 102.21            | 0.6897  |
| Grok41_Fast            | 0.656        | 0.681            | 20.18    | 2966.50   | 147.04            | 0.6683  |
| Grok4_0709             | 0.630        | 0.666            | 86.72    | 3881.89   | 44.76             | 0.6481  |
| Grok_Code_0825         | 0.615        | 0.613            | 69.76    | 3786.94   | 54.28             | 0.6142  |
| Gemini_3_Pro_Preview   | 0.526        | 0.563            | 49.20    | 4246.61   | 86.31             | 0.5444  |
| Gemini_3_Flash_Preview | 0.505        | 0.495            | 23.46    | 2896.39   | 123.48            | 0.5000  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                  | Hard Accuracy | Hard Completeness | Light Accuracy | Light Completeness | Score ↓ |
|------------------------|---------------|-------------------|----------------|--------------------|---------|
| Claude_Opus_45         | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Claude_Opus_45_high    | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Gemini_3_Flash_Preview | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Claude_Sonnet_45       | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| GPT51_Codex            | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Claude_Sonnet_45_high  | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Grok_Code_0825         | 3.8           | 4                 | 4              | 3                  | 0.935   |
| Gemini_3_Pro_Preview   | 3.5           | 3.5               | 4              | 4                  | 0.925   |
| Grok4_0709             | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT52_1211             | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT52_1211_high        | 3             | 4                 | 4              | 4                  | 0.925   |
| Grok41_FastReasoning   | 3.5           | 4                 | 3              | 4                  | 0.9125  |
| Claude_Haiku_45        | 3             | 4                 | 3.5            | 4                  | 0.9     |
| Kimi_K2                | 3             | 3                 | 3.5            | 3.5                | 0.8     |
| DeepSeek_v32           | 2             | 3                 | 3.75           | 3.75               | 0.75    |
| GPT51_Codex_mini       | 3             | 2                 | 2.5            | 3                  | 0.65    |
| MiniMax_M21            | 2             | 1.5               | 3.5            | 3.5                | 0.6125  |
| Grok41_Fast            | 2             | 1.5               | 3              | 3                  | 0.5625  |
| GPT5_Mini_high         | 1             | 1                 | 4              | 4                  | 0.55    |
| GPT5_Nano_high         | 0             | 0                 | 3.5            | 3.5                | 0.35    |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark v3.1 results reveal significant insights about current LLM capabilities for software engineering tasks:

**Shared Leadership: OpenAI and Anthropic**

GPT-5.2 (12-11) (high) and Claude models share leadership with closely matched performance. GPT-5.2 (high) achieves 85.53%, excelling in code translation (85.33%) and code generation (81.42%), with execution time 154.25 min at $9.39 cost. The regular variant achieves 84.61% with faster execution (85.90 min, 91.66 T/S) and lower cost ($7.18), demonstrating efficiency without extended reasoning.

Claude Opus 4.5 Think achieves 85.31% with reasoning mode, delivering excellent code translation (83.25%), documentation (82.89%), and LCIF (98.50%), execution time 240.63 min at $27.69 cost. The non-reasoning variant achieves 85.18% with minimal performance difference, indicating Anthropic's effective reasoning integration. Claude Sonnet 4.5 Think (83.91%) leads in code documentation (85.31%), while non-reasoning variant (83.10%) maintains strong documentation performance (84.06%) and excellent LCIF (96.25%).

Claude Haiku 4.5 achieves 79.58% with exceptional speed (181.81 T/S) and highest token generation (1.1M tokens), strong code documentation (80.42%), execution time 101.02 min at $5.92 cost. The Claude family consistently generates highest output volumes across benchmark, demonstrating Anthropic's optimization for comprehensive code generation.

**OpenAI Model Tiers and Tool Handling**

GPT-5.1 Codex achieves 82.26% with balanced performance (code translation: 78.17%, code generation: 78.00%, documentation: 76.64%, LCIF: 96.25%), execution time 198.42 min at $10.76 cost. The model demonstrates unique tool handling behavior: when tests require extensive output generation, it may respond with "no access to write tools, please provide tools and I will generate results" messages instead of producing code directly. This behavior particularly affects high-output scenarios but doesn't impact multimodal performance (79.94%), where tool usage requirements are minimal.

GPT-5.1 Codex mini (69.45%) shows similar tool handling characteristics with strong code translation (77.71%) but significantly exceeds coding performance in multimodal benchmark (77.75%). GPT-5 Mini (73.17%) demonstrates strong code translation (79.71%) and excellent documentation (83.86%) despite weak LCIF (55.00%), execution time 186.19 min at $1.59 cost. GPT-5 Nano (57.06%) offers ultra-low cost ($0.36) but with severe LCIF limitations (35.00%).

**Reasoning Mode Impact**

Claude models demonstrate minimal performance difference between reasoning and non-reasoning variants, suggesting effective integration of reasoning capabilities into base architecture. Claude Opus 4.5 Think (85.31%) vs non-reasoning (85.18%) shows only 0.13 percentage point difference, while Claude Sonnet 4.5 Think (83.91%) vs non-reasoning (83.10%) shows 0.81 percentage point difference. Both Think variants excel in documentation tasks, with Sonnet Think leading overall (85.31%).

**xAI Grok Models: Regression and Limitations**

Grok 4 (07-09) achieves 74.23% with moderate balanced performance (code translation: 70.33%, code generation: 69.27%, documentation: 64.81%, LCIF: 92.50%), execution time 94.85 min at $5.39 cost. Grok Code Fast delivers 71.75% with LCIF excellence (93.50%), fast execution (57.29 min) and low cost ($0.45).

Newer Grok 4.1 variants show significant regression. Grok 4.1 Fast Reasoning (63.23%) continues to suffer from truncation bug in code translation tasks, where model generates reasoning tokens but abruptly truncates output after 15-50 tokens, resulting in critically poor code translation (20.33%) while maintaining acceptable code generation (66.00%), documentation (75.33%), and LCIF (91.25%). Execution time 37.95 min at ultra-low cost ($0.15). Grok 4.1 Fast (62.17%) avoids the truncation issue but shows moderate overall results (code translation: 66.00%, code generation: 59.58%, documentation: 66.83%, LCIF: 56.25%), execution time 19.00 min at ultra-low cost ($0.18).

**Google Gemini Token Generation Constraints**

Gemini 3 models demonstrate significant token generation limitations despite 64k theoretical output capacity. Models generate only ~7-10k tokens per scenario, resulting in ~300k total output tokens across benchmark, compared to 1M+ tokens from leading models. This constraint severely impacts coding performance where verbose outputs are required.

Gemini 3 Pro Preview achieves 70.00% with strong LCIF (92.50%) and code translation (71.88%), but limited code generation (61.19%) and documentation (54.44%) due to output constraints. Execution time 54.07 min at 102.93 T/S for $4.78 cost. Gemini 3 Flash Preview achieves 68.34% with exceptional speed (23.00 min, 159.08 T/S) and low cost ($0.85), strong LCIF (96.25%) and code translation (70.50%), but limited code generation (56.62%) and documentation (50.00%).

Previous Gemini 2.5 Flash achieved 800k+ tokens in earlier benchmarks, but Google's recent adjustments reduced token generation significantly, impacting coding performance while improving cost-efficiency. Both models excel in multimodal tasks (Flash: 83.35%, Pro: 82.54%) where concise outputs align with their design philosophy, significantly outperforming coding results.

**Open-Source Models Performance**

Kimi K2 Thinking achieves 78.46% as top open-source model, delivering strong balanced performance across all categories (code translation: 78.38%, code generation: 76.27%, documentation: 79.19%, LCIF: 80.00%) with excellent speed (161.66 T/S), fast execution (62.83 min) at low cost ($1.72).

DeepSeek V3.2 demonstrates improved performance as reasoning model, achieving 72.52% with balanced results (code translation: 73.96%, code generation: 72.15%, documentation: 68.97%, LCIF: 75.00%), execution time 96.28 min at ultra-low cost ($0.99). MiniMax M2.1 achieves 67.73% with strong code documentation (79.67%) and code translation (70.13%), but weaker LCIF (61.25%), execution time 61.59 min at competitive pricing ($0.67).

**Key Performance Insights**

- **Speed Champions**: Grok 4.1 Fast (192.58 T/S), Claude Haiku 4.5 (181.81 T/S), Kimi K2 Thinking (161.66 T/S), Gemini 3 Flash Preview (159.08 T/S), MiniMax M2.1 (129.56 T/S)
- **Cost-Effectiveness Leaders**: Grok 4.1 Fast Reasoning ($0.15), Grok 4.1 Fast ($0.18), GPT-5 Nano ($0.36), Grok Code Fast ($0.45), MiniMax M2.1 ($0.67), Gemini 3 Flash Preview ($0.85)
- **LCIF Excellence**: Claude Opus 4.5 (98.50%), Claude Opus 4.5 Think (98.50%), Gemini 3 Flash Preview (96.25%), Claude Sonnet 4.5 (96.25%), GPT-5.1 Codex (96.25%), Claude Sonnet 4.5 Think (96.25%)
- **Code Translation Leaders**: GPT-5.2 (12-11) (high) (85.33%), Claude Opus 4.5 Think (83.25%), GPT-5.2 (12-11) (82.96%), Claude Opus 4.5 (82.92%), GPT-5 Mini (79.71%)
- **Code Generation Leaders**: GPT-5.2 (12-11) (high) (81.42%), GPT-5.2 (12-11) (80.27%), Claude Opus 4.5 (78.27%), GPT-5.1 Codex (78.00%), Claude Opus 4.5 Think (76.62%)
- **Code Documentation Leaders**: Claude Sonnet 4.5 Think (85.31%), Claude Sonnet 4.5 (84.06%), GPT-5 Mini (83.86%), Claude Opus 4.5 Think (82.89%), GPT-5.2 (12-11) (high) (82.86%)

**Organizations Recommendations**

- **Maximum Quality**: GPT-5.2 (12-11) (high) for top overall coding performance (85.53%), GPT-5.2 regular for excellent quality/cost balance (84.61%, $7.18)
- **Premium with Reasoning**: Claude Opus 4.5 Think (85.31%) for organizations needing reasoning transparency with top-tier performance, Claude Sonnet 4.5 Think (83.91%) for code documentation excellence (85.31%)
- **Cross-Platform Excellence**: Claude Opus 4.5 (85.18%) for organizations requiring availability across all major cloud providers with flagship performance
- **High-Volume Applications**: Claude Haiku 4.5 for high token generation (1.1M tokens) with exceptional speed (181.81 T/S) at mid-tier pricing (79.58%, $5.92)
- **Balanced Performance**: GPT-5.2 (12-11) offers best balance of quality and capability across all coding categories (84.61%), Claude Sonnet 4.5 for strong balanced performance (83.10%)
- **Cost-Effective Options**: Grok 4.1 Fast Reasoning ($0.15) for ultra-low cost despite limitations, GPT-5 Nano ($0.36) for budget-constrained deployments, Grok Code Fast ($0.45) for LCIF tasks
- **Open-Source**: Kimi K2 Thinking for top open-source performance (78.46%, strong balanced results), DeepSeek V3.2 for reasoning capabilities (72.52%, ultra-low cost $0.99), MiniMax M2.1 for documentation tasks (67.73%, strong documentation 79.67%)

<p align="center">
    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>