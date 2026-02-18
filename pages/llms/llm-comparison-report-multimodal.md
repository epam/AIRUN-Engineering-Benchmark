# LLM's Multimodal Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) in multimodal category. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google
DeepMind, xAI and other companies.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach Multimodal](llm-approach-multimodal.md)

| Benchmark model ID     | Name                    | Reasoning      | Date       | Accuracy | Completeness | Total Time | Speed (T/S) | Total input | Total Thinking | Total output | Total Price $ | Score in % |
|------------------------|-------------------------|----------------|------------|----------|--------------|------------|-------------|-------------|----------------|--------------|---------------|------------|
| Claude_Sonnet_46       | Claude Sonnet 4.6       | Yes (adaptive) | 2026-02-18 | 0.824    | 0.978        | 37.70      | 59.54       | 801180      | 0              | 134687       | 4.42          | 83.91%     |
| Gemini_3_Flash_Preview | Gemini 3 Flash Preview  | Yes            | 2025-12-18 | 0.815    | 1.000        | 13.32      | 116.32      | 743882      | 77035          | 92991        | 0.65          | 83.35%     |
| Gemini_3_Pro_Preview   | Gemini 3 Pro Preview    | Yes (high)     | 2025-11-19 | 0.809    | 0.973        | 25.70      | 81.67       | 743882      | 107774         | 125944       | 3.00          | 82.54%     |
| GPT52_1211_high        | GPT-5.2 (12-11) (high)  | Yes (high)     | 2025-12-12 | 0.807    | 0.992        | 33.85      | 38.35       | 636192      | 39035          | 77897        | 2.20          | 82.52%     |
| GPT51_Codex            | GPT-5.1 Codex           | Yes (high)     | 2025-11-21 | 0.778    | 0.992        | 31.97      | 38.29       | 610241      | 60480          | 73432        | 1.50          | 79.94%     |
| GPT5_Mini_high         | GPT-5 Mini              | Yes (high)     | 2025-10-24 | 0.769    | 0.997        | 51.23      | 52.28       | 636192      | 124352         | 160700       | 0.48          | 79.21%     |
| GPT52_1211             | GPT-5.2 (12-11)         | No             | 2025-12-12 | 0.754    | 1.000        | 16.71      | 39.44       | 636192      | 0              | 39537        | 1.67          | 77.89%     |
| GPT51_Codex_mini       | GPT-5.1 Codex mini      | Yes (high)     | 2025-11-21 | 0.756    | 0.974        | 9.83       | 125.00      | 636192      | 60800          | 73687        | 0.31          | 77.75%     |
| Kimi_K2p5              | Kimi K2.5               | Yes            | 2026-02-16 | 0.721    | 0.984        | 19.20      | 66.80       | 672596      | 0              | 76944        | 0.63          | 74.76%     |
| Claude_Opus_46         | Claude Opus 4.6         | Yes (adaptive) | 2026-02-16 | 0.700    | 0.967        | 38.54      | 51.78       | 801180      | 0              | 119721       | 7.00          | 72.64%     |
| GPT5_Nano_high         | GPT-5 Nano              | Yes (high)     | 2025-10-24 | 0.627    | 0.994        | 46.74      | 86.49       | 649510      | 208768         | 242562       | 0.13          | 66.34%     |
| Claude_Haiku_45        | Claude Haiku 4.5        | No             | 2025-10-16 | 0.571    | 0.971        | 4.64       | 74.89       | 801240      | 0              | 20831        | 0.91          | 61.13%     |
| Grok4_0709             | Grok 4 (07-09)          | Yes            | 2025-09-11 | 0.380    | 0.958        | 66.46      | 42.72       | 606242      | 138102         | 170368       | 4.37          | 43.75%     |
| Grok41_FastReasoning   | Grok 4.1 Fast Reasoning | Yes            | 2025-11-21 | 0.375    | 0.974        | 18.69      | 25.58       | 587687      | 65856          | 28675        | 0.13          | 43.46%     |
| Grok41_Fast            | Grok 4.1 Fast           | No             | 2025-11-21 | 0.366    | 0.955        | 5.15       | 70.27       | 588047      | 0              | 21694        | 0.13          | 42.52%     |

_Table 1. Results of evaluation LLMs in EPAM's Multimodal LLMs Benchmark._

## Conclusion

**Claude Sonnet 4.6: Multimodal Leadership**

Claude Sonnet 4.6 achieves multimodal leadership with 83.91% score, demonstrating strong accuracy (82.4%), high completeness (97.8%), execution time 37.70 min at $4.42 cost. The model also delivers strong coding performance (85.75%), making it one of the most versatile models across both domains. Features adaptive reasoning mode and most recent training cutoff (Jan 2026).

**Google Gemini: Strong Multimodal Contenders**

Gemini 3 Flash Preview achieves 83.35% with excellent accuracy (81.5%), perfect completeness (100%), exceptional speed (13.32 min, 116.32 T/S), and outstanding cost-efficiency ($0.65). Google's token-efficient design aligns well with multimodal tasks, significantly outperforming coding results (68.34%).

Gemini 3 Pro Preview achieves 82.54%, demonstrating excellent accuracy (80.9%), fast execution (25.70 min, 81.67 T/S), and reasonable cost ($3.00). Token efficiency optimization excels in multimodal tasks, significantly outperforming its coding results (70.00%).

**OpenAI: Consistent Cross-Domain Performance**

GPT-5.2 (12-11) (high) achieves 82.52% with excellent accuracy (80.7%), near-perfect completeness (99.2%), and reasonable
cost ($2.20, 33.85 min), demonstrating consistent cross-domain excellence across coding (85.53%) and multimodal benchmarks. The regular variant achieves 77.89% (16.71 min, $1.67) with perfect
completeness (100%), offering faster execution and lower cost.

GPT-5.1 Codex (79.94%) and Codex mini (77.75%) perform comparably in multimodal tasks, with Codex achieving 79.94% (31.97 min, $1.50) and mini 77.75% (9.83 min, 125.00 T/S, $0.31). Both models
demonstrate that their tool handling limitations in coding tasks do not impact multimodal performance where tool usage requirements are minimal. GPT-5 Mini achieves 79.21% with excellent
cost-effectiveness ($0.48), significantly outperforming its coding results (73.17%). GPT-5 Nano (66.34%) achieves best cost ($0.13).

**Claude: Evolving Cross-Domain Performance**

Claude Sonnet 4.6 leads multimodal benchmark with 83.91% while also achieving strong coding performance (85.75%), demonstrating improved cross-domain versatility in the Claude family. Claude Opus 4.6 achieves 72.64% (38.54 min, $7.00), below coding leadership (86.78%), maintaining stronger coding specialization. Claude Haiku 4.5 achieves 61.13% with ultrafast execution (4.64 min, $0.91), significantly behind its coding performance (79.58%).

**xAI Grok: Text-Based Programming Specialization**

Grok models demonstrate consistent multimodal weakness, confirming xAI's specialization in text-based programming with limited visual reasoning capabilities. Grok 4 (07-09) achieves 43.75% vs coding
performance (74.23%). Grok 4.1 Fast Reasoning (43.46%) and Grok 4.1 Fast (42.52%) show lowest multimodal performance among tested models.

<p align="center">
    © 2026 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>