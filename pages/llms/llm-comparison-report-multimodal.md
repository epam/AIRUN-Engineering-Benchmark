# LLM's Multimodal Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) in multimodal category. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google
Deepmind, xAI, Amazon.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach Multimodal](llm-approach-multimodal.md)

| Benchmark model ID     | Name                    | Reasoning  | Date       | Accuracy | Completeness | Total Time | Speed (T/S) | Total input | Total Thinking | Total output | Total Price $ | Score in % |
|------------------------|-------------------------|------------|------------|----------|--------------|------------|-------------|-------------|----------------|--------------|---------------|------------|
| Gemini_3_Flash_Preview | Gemini 3 Flash Preview  | Yes        | 2025-12-18 | 0.815    | 1.000        | 13.32      | 116.32      | 743882      | 77035          | 92991        | 0.65          | 83.35%     |
| Gemini_3_Pro_Preview   | Gemini 3 Pro Preview    | Yes (high) | 2025-11-19 | 0.809    | 0.973        | 25.70      | 81.67       | 743882      | 107774         | 125944       | 3.00          | 82.54%     |
| GPT52_1211_high        | GPT-5.2 (12-11) (high)  | Yes (high) | 2025-12-12 | 0.807    | 0.992        | 33.85      | 38.35       | 636192      | 39035          | 77897        | 2.20          | 82.52%     |
| GPT51_Codex            | GPT-5.1 Codex           | Yes (high) | 2025-11-21 | 0.778    | 0.992        | 31.97      | 38.29       | 610241      | 60480          | 73432        | 1.50          | 79.94%     |
| GPT5_Mini_high         | GPT-5 Mini              | Yes (high) | 2025-10-24 | 0.769    | 0.997        | 51.23      | 52.28       | 636192      | 124352         | 160700       | 0.48          | 79.21%     |
| GPT52_1211             | GPT-5.2 (12-11)         | No         | 2025-12-12 | 0.754    | 1.000        | 16.71      | 39.44       | 636192      | -              | 39537        | 1.67          | 77.89%     |
| GPT51_Codex_mini       | GPT-5.1 Codex mini      | Yes (high) | 2025-11-21 | 0.756    | 0.974        | 9.83       | 125.00      | 636192      | 60800          | 73687        | 0.31          | 77.75%     |
| GPT5_Nano_high         | GPT-5 Nano              | Yes (high) | 2025-10-24 | 0.627    | 0.994        | 46.74      | 86.49       | 649510      | 208768         | 242562       | 0.13          | 66.34%     |
| Claude_Opus_45         | Claude Opus 4.5         | No         | 2025-11-25 | 0.622    | 0.982        | 10.43      | 38.32       | 801240      | -              | 23977        | 4.61          | 65.80%     |
| Claude_Haiku_45        | Claude Haiku 4.5        | No         | 2025-10-16 | 0.571    | 0.971        | 4.64       | 74.89       | 801240      | -              | 20831        | 0.91          | 61.13%     |
| Claude_Sonnet_45       | Claude Sonnet 4.5       | No         | 2025-09-30 | 0.503    | 0.949        | 8.46       | 37.12       | 801210      | -              | 18843        | 2.69          | 54.76%     |
| AmazonNovaPremier      | Amazon Nova Premier     | No         | 2025-09-11 | 0.489    | 0.928        | 14.85      | 16.78       | 767489      | -              | 14954        | 2.11          | 53.26%     |
| Grok4FastReasoning     | Grok 4 Fast             | Yes        | 2025-09-26 | 0.455    | 0.982        | 14.22      | 91.42       | 586517      | 32902          | 77976        | 0.16          | 50.74%     |
| Grok4_0709             | Grok 4 (07-09)          | Yes        | 2025-09-11 | 0.380    | 0.958        | 66.46      | 42.72       | 606242      | 138102         | 170368       | 4.37          | 43.75%     |
| Grok41_FastReasoning   | Grok 4.1 Fast Reasoning | Yes        | 2025-11-21 | 0.375    | 0.974        | 18.69      | 25.58       | 587687      | 65856          | 28675        | 0.13          | 43.46%     |
| Grok41_Fast            | Grok 4.1 Fast           | No         | 2025-11-21 | 0.366    | 0.955        | 5.15       | 70.27       | 588047      | -              | 21694        | 0.13          | 42.52%     |

_Table 1. Results of evaluation LLMs in EPAM's Multimodal LLMs Benchmark._

## Conclusion

Gemini 3 Flash Preview achieves multimodal leadership with 83.35% score, demonstrating excellent accuracy (81.5%), perfect completeness (100%), exceptional speed (13.32 min, 116.32 T/S), and
outstanding cost-efficiency ($0.65). This represents Google's strongest multimodal performance with the best value proposition. Google's token-efficient design - training models for concise outputs - perfectly aligns with multimodal tasks, enabling superior performance compared to moderate coding results (72.47%) where verbose outputs are essential.

Gemini 3 Pro Preview achieves 82.54% in second place, demonstrating excellent accuracy (80.9%), fast execution (25.70 min, 81.67 T/S), and reasonable cost ($3.00). Pricing increased to $2/$12 for
<200K context (up from $1.25/$10). The model's token efficiency optimization excels in multimodal tasks where concise outputs are preferred, outperforming its coding results (73.52%) where system prompt engineering was required to achieve current performance.

GPT-5.2 (12-11) (high) achieves 82.52% in third place, nearly tied with Gemini models for the top positions. With excellent accuracy (80.7%), near-perfect completeness (99.2%), and reasonable
cost ($2.20, 33.85 min), GPT-5.2 demonstrates consistent cross-domain excellence - also ranking first in coding benchmark (85.05%). The regular variant achieves 77.89% (16.71 min, $1.67) with perfect
completeness (100%), offering faster execution for cost-conscious deployments.

GPT-5.1 Codex achieves 79.94% in fourth place, dramatically exceeding its coding performance (78.72%). With excellent completeness (99.2%), good accuracy (77.8%), and reasonable
cost ($1.50, 31.97 min), the model demonstrates that its tool handling limitations in coding tasks do not impact multimodal performance where tool usage requirements are minimal.
GPT-5 Mini achieves 79.21% in fifth place with excellent cost-effectiveness ($0.48), significantly outperforming its coding results (71.28%) and demonstrating strong multimodal capabilities. GPT-5.1
Codex mini scores 77.75% in sixth place (9.83 min, 125.00 T/S, $0.31), dramatically surpassing its coding performance (61.58%) and confirming that Codex variants excel in visual reasoning tasks
despite coding limitations.

GPT-5 Nano (66.34%) achieves best cost ($0.13) while outperforming its coding results (58.61%), following the same pattern as GPT-5 Mini where multimodal performance exceeds coding performance. Claude
Opus 4.5 achieves 65.80% (10.43 min, $4.61), significantly underperforming compared to its coding excellence (83.18%, 3rd place), demonstrating Anthropic's optimization for text-based programming over
reasoning. Claude Haiku 4.5 achieves 61.13% with ultrafast execution (4.64 min) and excellent cost-efficiency ($0.91), though significantly behind its coding performance (81.83%). Claude Sonnet 4.5 (
54.76%) underperforms in multimodal despite coding excellence (82.19%), confirming the Claude family's specialization in text-based coding tasks. Grok models show consistent multimodal weakness: Grok
4 Fast (50.74% vs 79.45% coding), Grok 4.1 Fast Reasoning (43.46%), and Grok 4.1 Fast (42.52%, lowest among tested models), confirming xAI's specialization in text-based programming with limited
visual reasoning capabilities.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>