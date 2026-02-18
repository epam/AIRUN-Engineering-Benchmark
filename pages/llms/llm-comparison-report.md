# LLM's Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google DeepMind, xAI and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                  | Benchmark model ID      | Reasoning      | Execution Date | Code Translation | Code Generation | Code Document | LCIF    | Total Score |
|------------------------|-------------------------|----------------|----------------|------------------|-----------------|---------------|---------|-------------|
| Claude_Opus_46         | Claude Opus 4.6         | Yes (adaptive) | 2026-02-16     | 83.67%           | 82.00%          | 81.44%        | 100.00% | 86.78%      |
| Claude_Sonnet_46       | Claude Sonnet 4.6       | Yes (adaptive) | 2026-02-18     | 82.38%           | 80.77%          | 81.36%        | 98.50%  | 85.75%      |
| GPT52_1211_high        | GPT-5.2 (12-11) (high)  | Yes (high)     | 2025-12-24     | 85.33%           | 81.42%          | 82.86%        | 92.50%  | 85.53%      |
| GPT52_1211             | GPT-5.2 (12-11)         | No             | 2025-12-24     | 82.96%           | 80.27%          | 82.72%        | 92.50%  | 84.61%      |
| Kimi_K2p5              | Kimi K2.5               | Yes            | 2026-02-16     | 78.00%           | 79.77%          | 78.75%        | 95.25%  | 82.94%      |
| GPT51_Codex            | GPT-5.1 Codex           | Yes (high)     | 2026-01-08     | 78.17%           | 78.00%          | 76.64%        | 96.25%  | 82.26%      |
| Claude_Haiku_45        | Claude Haiku 4.5        | No             | 2026-01-08     | 74.50%           | 73.38%          | 80.42%        | 90.00%  | 79.58%      |
| GLM_5                  | GLM-5                   | Yes            | 2026-02-16     | 79.25%           | 71.88%          | 71.67%        | 95.25%  | 79.51%      |
| MiniMax_M2p5           | MiniMax M2.5            | Yes            | 2026-02-16     | 67.42%           | 64.15%          | 79.28%        | 91.50%  | 75.59%      |
| Grok4_0709             | Grok 4 (07-09)          | Yes            | 2026-01-08     | 70.33%           | 69.27%          | 64.81%        | 92.50%  | 74.23%      |
| GPT5_Mini_high         | GPT-5 Mini              | Yes (high)     | 2026-01-08     | 79.71%           | 74.12%          | 83.86%        | 55.00%  | 73.17%      |
| DeepSeek_v32           | DeepSeek V3.2           | Yes            | 2026-01-08     | 73.96%           | 72.15%          | 68.97%        | 75.00%  | 72.52%      |
| Grok_Code_0825         | Grok Code Fast          | Yes            | 2026-01-08     | 67.75%           | 64.35%          | 61.42%        | 93.50%  | 71.75%      |
| Gemini_3_Pro_Preview   | Gemini 3 Pro Preview    | Yes (high)     | 2025-12-24     | 71.88%           | 61.19%          | 54.44%        | 92.50%  | 70.00%      |
| GPT51_Codex_mini       | GPT-5.1 Codex mini      | Yes (high)     | 2026-01-08     | 77.71%           | 61.88%          | 73.22%        | 65.00%  | 69.45%      |
| Gemini_3_Flash_Preview | Gemini 3 Flash Preview  | Yes            | 2025-12-24     | 70.50%           | 56.62%          | 50.00%        | 96.25%  | 68.34%      |
| Grok41_FastReasoning   | Grok 4.1 Fast Reasoning | Yes            | 2026-01-08     | 20.33%           | 66.00%          | 75.33%        | 91.25%  | 63.23%      |
| Grok41_Fast            | Grok 4.1 Fast           | No             | 2026-01-08     | 66.00%           | 59.58%          | 66.83%        | 56.25%  | 62.17%      |
| GPT5_Nano_high         | GPT-5 Nano              | Yes (high)     | 2026-01-08     | 68.21%           | 53.27%          | 71.78%        | 35.00%  | 57.06%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT52_1211_high        | 0.810        | 0.897            | 224.35   | 18292.75  | 81.54             | 0.8533  |
| Claude_Opus_46         | 0.794        | 0.879            | 623.41   | 43859.83  | 70.36             | 0.8367  |
| GPT52_1211             | 0.789        | 0.870            | 115.80   | 13278.75  | 114.67            | 0.8296  |
| Claude_Sonnet_46       | 0.797        | 0.851            | 552.13   | 44186.33  | 80.03             | 0.8238  |
| GPT5_Mini_high         | 0.741        | 0.853            | 280.85   | 18084.08  | 64.39             | 0.7971  |
| GLM_5                  | 0.747        | 0.838            | 185.83   | 12979.50  | 69.85             | 0.7925  |
| GPT51_Codex            | 0.742        | 0.822            | 495.06   | 39962.58  | 80.72             | 0.7817  |
| Kimi_K2p5              | 0.739        | 0.821            | 91.72    | 17988.25  | 196.11            | 0.7800  |
| GPT51_Codex_mini       | 0.740        | 0.814            | 356.54   | 42905.25  | 120.34            | 0.7771  |
| Claude_Haiku_45        | 0.733        | 0.757            | 89.39    | 17842.50  | 199.59            | 0.7450  |
| DeepSeek_v32           | 0.697        | 0.783            | 208.24   | 11630.42  | 55.85             | 0.7396  |
| Gemini_3_Pro_Preview   | 0.653        | 0.785            | 116.17   | 13114.33  | 112.89            | 0.7188  |
| Gemini_3_Flash_Preview | 0.652        | 0.758            | 44.72    | 8079.50   | 180.69            | 0.7050  |
| Grok4_0709             | 0.646        | 0.761            | 203.87   | 11472.75  | 56.27             | 0.7033  |
| GPT5_Nano_high         | 0.650        | 0.714            | 171.29   | 25463.58  | 148.66            | 0.6821  |
| Grok_Code_0825         | 0.631        | 0.724            | 99.38    | 9526.58   | 95.86             | 0.6775  |
| MiniMax_M2p5           | 0.674        | 0.674            | 200.70   | 14394.83  | 71.72             | 0.6742  |
| Grok41_Fast            | 0.679        | 0.641            | 29.71    | 6570.83   | 221.15            | 0.6600  |
| Grok41_FastReasoning   | 0.192        | 0.215            | 67.65    | 11125.00  | 164.45            | 0.2033  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Claude_Opus_46         | 0.795        | 0.845            | 508.46   | 41739.08  | 82.09             | 0.8200  |
| GPT52_1211_high        | 0.802        | 0.827            | 322.63   | 20894.77  | 64.76             | 0.8142  |
| Claude_Sonnet_46       | 0.806        | 0.809            | 441.56   | 39412.46  | 89.26             | 0.8077  |
| GPT52_1211             | 0.815        | 0.791            | 152.82   | 14923.92  | 97.66             | 0.8027  |
| Kimi_K2p5              | 0.795        | 0.801            | 96.43    | 19298.77  | 200.13            | 0.7977  |
| GPT51_Codex            | 0.789        | 0.771            | 368.28   | 33874.77  | 91.98             | 0.7800  |
| GPT5_Mini_high         | 0.738        | 0.744            | 303.58   | 19367.08  | 63.80             | 0.7412  |
| Claude_Haiku_45        | 0.709        | 0.758            | 152.86   | 32930.46  | 215.42            | 0.7338  |
| DeepSeek_v32           | 0.723        | 0.720            | 173.73   | 17780.23  | 102.35            | 0.7215  |
| GLM_5                  | 0.720        | 0.718            | 263.34   | 20053.77  | 76.15             | 0.7188  |
| Grok4_0709             | 0.685        | 0.701            | 129.52   | 6293.85   | 48.59             | 0.6927  |
| Grok41_FastReasoning   | 0.664        | 0.656            | 72.57    | 12955.69  | 178.52            | 0.6600  |
| Grok_Code_0825         | 0.642        | 0.645            | 76.08    | 5777.54   | 75.94             | 0.6435  |
| MiniMax_M2p5           | 0.634        | 0.649            | 286.14   | 17539.92  | 61.30             | 0.6415  |
| GPT51_Codex_mini       | 0.609        | 0.628            | 173.26   | 22360.38  | 129.06            | 0.6188  |
| Gemini_3_Pro_Preview   | 0.619        | 0.605            | 74.21    | 7703.00   | 103.81            | 0.6119  |
| Grok41_Fast            | 0.624        | 0.568            | 32.33    | 6715.23   | 207.68            | 0.5958  |
| Gemini_3_Flash_Preview | 0.579        | 0.553            | 32.39    | 5416.38   | 167.23            | 0.5662  |
| GPT5_Nano_high         | 0.570        | 0.495            | 199.06   | 21545.62  | 108.24            | 0.5327  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                  | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT5_Mini_high         | 0.824        | 0.853            | 214.17   | 15967.22  | 74.56             | 0.8386  |
| GPT52_1211_high        | 0.817        | 0.840            | 131.60   | 7709.61   | 58.59             | 0.8286  |
| GPT52_1211             | 0.807        | 0.847            | 98.77    | 6614.89   | 66.97             | 0.8272  |
| Claude_Opus_46         | 0.789        | 0.840            | 144.69   | 8457.67   | 58.45             | 0.8144  |
| Claude_Sonnet_46       | 0.788        | 0.839            | 168.71   | 10110.00  | 59.92             | 0.8136  |
| Claude_Haiku_45        | 0.781        | 0.827            | 166.74   | 25545.00  | 153.20            | 0.8042  |
| MiniMax_M2p5           | 0.772        | 0.813            | 115.45   | 7798.11   | 67.54             | 0.7928  |
| Kimi_K2p5              | 0.778        | 0.797            | 41.47    | 6907.67   | 166.56            | 0.7875  |
| GPT51_Codex            | 0.747        | 0.786            | 65.37    | 6430.11   | 98.37             | 0.7664  |
| Grok41_FastReasoning   | 0.760        | 0.747            | 29.00    | 4169.33   | 143.79            | 0.7533  |
| GPT51_Codex_mini       | 0.733        | 0.732            | 38.16    | 5001.50   | 131.06            | 0.7322  |
| GPT5_Nano_high         | 0.671        | 0.765            | 124.50   | 15638.28  | 125.61            | 0.7178  |
| GLM_5                  | 0.714        | 0.719            | 188.31   | 9496.06   | 50.43             | 0.7167  |
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
| Claude_Opus_46         | 4             | 4                 | 4              | 4                  | 1       |
| Claude_Sonnet_46       | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Gemini_3_Flash_Preview | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| GPT51_Codex            | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Kimi_K2p5              | 3.5           | 4                 | 3.8            | 4                  | 0.9525  |
| GLM_5                  | 3.5           | 4                 | 3.8            | 4                  | 0.9525  |
| Grok_Code_0825         | 3.8           | 4                 | 4              | 3                  | 0.935   |
| Gemini_3_Pro_Preview   | 3.5           | 3.5               | 4              | 4                  | 0.925   |
| Grok4_0709             | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT52_1211             | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT52_1211_high        | 3             | 4                 | 4              | 4                  | 0.925   |
| MiniMax_M2p5           | 3.5           | 3.5               | 3.8            | 4                  | 0.915   |
| Grok41_FastReasoning   | 3.5           | 4                 | 3              | 4                  | 0.9125  |
| Claude_Haiku_45        | 3             | 4                 | 3.5            | 4                  | 0.9     |
| DeepSeek_v32           | 2             | 3                 | 3.75           | 3.75               | 0.75    |
| GPT51_Codex_mini       | 3             | 2                 | 2.5            | 3                  | 0.65    |
| Grok41_Fast            | 2             | 1.5               | 3              | 3                  | 0.5625  |
| GPT5_Mini_high         | 1             | 1                 | 4              | 4                  | 0.55    |
| GPT5_Nano_high         | 0             | 0                 | 3.5            | 3.5                | 0.35    |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark v3.1 results reveal significant insights about current LLM capabilities for software engineering tasks:

**Anthropic Leadership with Adaptive Reasoning**

Claude Opus 4.6 achieves coding benchmark leadership with 86.78% (code translation: 83.67%, code generation: 82.00%, documentation: 81.44%, LCIF: 100.00%), becoming the first model to reach perfect
LCIF score. The model introduces adaptive reasoning mode that adjusts complexity based on task requirements and increased max output (128K tokens). Execution time 278.25 min at $32.53 cost, highest
among tested models. With 1.22M tokens generated, Opus 4.6 demonstrates Anthropic's optimization for comprehensive outputs.

Claude Sonnet 4.6 achieves 85.75% (code translation: 82.38%, code generation: 80.77%, documentation: 81.36%, LCIF: 98.50%), execution time 256.71 min at $19.57 cost. Features adaptive reasoning mode
and has the most recent training cutoff (Jan 2026). Lower cost than Opus makes it attractive for many use cases. Note: adaptive reasoning in some cases consumed output budget with reasoning tokens,
requiring 3 migration tests to run without reasoning.

GPT-5.2 (12-11) (high) achieves 85.53%, excelling in code translation (85.33%) and code generation (81.42%), with faster execution (154.25
min, $9.39). The regular variant achieves 84.61% with significantly faster execution (85.90 min, 91.66 T/S) and lower cost ($7.18), demonstrating efficiency without extended reasoning.

Claude Haiku 4.5 achieves 79.58% with exceptional speed (181.81 T/S) and high token generation (1.1M tokens), execution time 101.02 min at $5.92 cost.

**OpenAI Model Tiers and Tool Handling**

GPT-5.1 Codex achieves 82.26% with balanced performance (code translation: 78.17%, code generation: 78.00%, documentation: 76.64%, LCIF: 96.25%), execution time 198.42 min at $10.76 cost. The model
demonstrates unique tool handling behavior: when tests require extensive output generation, it may respond with "no access to write tools, please provide tools and I will generate results" messages
instead of producing code directly. This behavior particularly affects high-output scenarios but doesn't impact multimodal performance (79.94%), where tool usage requirements are minimal.

GPT-5.1 Codex mini (69.45%) shows similar tool handling characteristics with strong code translation (77.71%) but significantly exceeds coding performance in multimodal benchmark (77.75%). GPT-5
Mini (73.17%) demonstrates strong code translation (79.71%) and excellent documentation (83.86%) despite weak LCIF (55.00%), execution time 186.19 min
at $1.59 cost. GPT-5 Nano (57.06%) offers ultra-low cost ($0.36) but with severe LCIF limitations (35.00%).

**Adaptive Reasoning: Benefits and Limitations**

Both Claude Opus 4.6 and Sonnet 4.6 feature adaptive reasoning mode that adjusts approach complexity based on task requirements. Opus 4.6 uses it effectively, achieving benchmark leadership (86.78%)
and perfect LCIF (100.00%) with increased output capacity (128K tokens). Sonnet 4.6 (85.75%) also delivers strong results with adaptive reasoning, though in some cases the reasoning consumed the
output budget, requiring 3 migration tests to run without reasoning. This issue should be considered when using adaptive reasoning in production scenarios with strict output requirements.

**xAI Grok Models: Regression and Limitations**

Grok 4 (07-09) achieves 74.23% with moderate balanced performance (code translation: 70.33%, code generation: 69.27%, documentation: 64.81%, LCIF: 92.50%), execution time 94.85 min
at $5.39 cost. Grok Code Fast delivers 71.75% with LCIF excellence (93.50%), fast execution (57.29 min) and low cost ($0.45).

Newer Grok 4.1 variants show significant regression. Grok 4.1 Fast Reasoning (63.23%) continues to suffer from truncation bug in code translation tasks, where model generates reasoning tokens but
abruptly truncates output after 15-50 tokens, resulting in critically poor code translation (20.33%) while maintaining acceptable code generation (66.00%), documentation (75.33%), and LCIF (91.25%).
Execution time 37.95 min at ultra-low
cost ($0.15). Grok 4.1 Fast (62.17%) avoids the truncation issue but shows moderate overall results (code translation: 66.00%, code generation: 59.58%, documentation: 66.83%, LCIF: 56.25%),
execution time 19.00 min at ultra-low cost ($0.18).

**Google Gemini Token Generation Constraints**

Gemini 3 models demonstrate significant token generation limitations despite 64k theoretical output capacity. Models generate only ~7-10k tokens per scenario, resulting in ~300k total output tokens
across benchmark, compared to 1M+ tokens from leading models. This constraint severely impacts coding performance where verbose outputs are required.

Gemini 3 Pro Preview achieves 70.00% with strong LCIF (92.50%) and code translation (71.88%), but limited code generation (61.19%) and documentation (54.44%) due to output constraints. Execution time
54.07 min at 102.93 T/S for $4.78 cost. Gemini 3 Flash Preview achieves 68.34% with exceptional speed (23.00 min, 159.08 T/S) and low cost ($0.85), strong LCIF (96.25%) and code translation (70.50%),
but limited code generation (56.62%) and documentation (50.00%).

Previous Gemini 2.5 Flash achieved 800k+ tokens in earlier benchmarks, but Google's recent adjustments reduced token generation significantly, impacting coding performance while improving
cost-efficiency. Both models excel in multimodal tasks (Flash: 83.35%, Pro: 82.54%) where concise outputs align with their design philosophy, significantly outperforming coding results.

**Open-Source Models Performance**

Kimi K2.5 achieves 82.94% as top open-source model, delivering balanced performance across all categories (code translation: 78.00%, code generation: 79.77%, documentation: 78.75%, LCIF: 95.25%) with
exceptional speed (190.62 T/S), fast execution (51.68 min) at low cost ($1.97).

GLM-5 achieves 79.51% with strong code translation (79.25%), solid code generation (71.88%), documentation (71.67%), and LCIF (95.25%), execution time 150.72 min
at $2.20 cost. MiniMax M2.5 achieves 75.59% with strong code documentation (79.28%), code translation (67.42%), code generation (64.15%), and LCIF (91.50%), execution time 136.77 min at competitive pricing ($
0.75). DeepSeek V3.2 demonstrates balanced reasoning performance, achieving 72.52% with execution time 96.28 min at ultra-low cost ($0.99).

**Key Performance Insights**

- **Speed Champions**: Grok 4.1 Fast (192.58 T/S), Kimi K2.5 (190.62 T/S), Claude Haiku 4.5 (181.81 T/S), Gemini 3 Flash Preview (159.08 T/S), GPT-5 Nano (125.96 T/S)
- **Cost-Effectiveness Leaders**: Grok 4.1 Fast ($0.18), Grok 4.1 Fast Reasoning ($0.25), GPT-5 Nano ($0.36), Grok Code Fast ($0.45), MiniMax M2.5 ($0.75), Gemini 3 Flash Preview ($0.85)
- **LCIF Excellence**: Claude Opus 4.6 (100.00%), Claude Sonnet 4.6 (98.50%), Gemini 3 Flash Preview (96.25%), GPT-5.1 Codex (96.25%), Kimi K2.5 (95.25%), GLM-5 (95.25%)
- **Code Translation Leaders**: GPT-5.2 (12-11) (high) (85.33%), Claude Opus 4.6 (83.67%), GPT-5.2 (12-11) (82.96%), Claude Sonnet 4.6 (82.38%), GPT-5 Mini (79.71%)
- **Code Generation Leaders**: Claude Opus 4.6 (82.00%), GPT-5.2 (12-11) (high) (81.42%), Claude Sonnet 4.6 (80.77%), GPT-5.2 (12-11) (80.27%), Kimi K2.5 (79.77%)
- **Code Documentation Leaders**: GPT-5 Mini (83.86%), GPT-5.2 (12-11) (high) (82.86%), Claude Opus 4.6 (81.44%), Claude Sonnet 4.6 (81.36%), Claude Haiku 4.5 (80.42%)

**Organizations Recommendations**

- **Maximum Quality**: Claude Opus 4.6 for benchmark leadership (86.78%) with first perfect LCIF score (100.00%) and adaptive reasoning, GPT-5.2 (12-11) (high) for strong performance (85.53%) with
  faster execution and lower cost
- **Cross-Domain Versatility**: Claude Sonnet 4.6 for strong performance across both coding (85.75%) and multimodal (83.91%) benchmarks, with most recent training cutoff (Jan 2026) and lower cost than
  Opus ($19.57 vs $32.53). Note: adaptive reasoning may require careful handling in some scenarios
- **Balanced Performance**: GPT-5.2 (12-11) offers best balance of quality and cost across all coding categories (84.61%, $7.18)
- **High-Volume Applications**: Claude Sonnet 4.6 for highest token generation (1.22M tokens), Claude Opus 4.6 (1.22M tokens) with comprehensive outputs, Claude Haiku 4.5 for high volume with
  exceptional speed (181.81 T/S, 1.1M tokens) at mid-tier pricing ($5.92)
- **Cost-Effective Options**: Grok 4.1 Fast ($0.18) for ultra-low cost despite limitations, GPT-5 Nano ($0.36) for budget-constrained deployments, Grok Code Fast ($0.45) for LCIF tasks
- **Open-Source**: Kimi K2.5 for top open-source performance (82.94%, strong balanced results with 190.62 T/S), GLM-5 for solid performance (79.51%, strong translation 79.25%), MiniMax M2.5 for
  documentation tasks (75.59%, strong documentation 79.28%), DeepSeek V3.2 for ultra-low cost reasoning ($0.99)

<p align="center">
    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>