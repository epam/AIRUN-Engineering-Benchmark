# LLM's Multimodal Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) in multimodal category. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google
Deepmind, xAI, Amazon.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach Multimodal](llm-approach-multimodal.md)

| Benchmark model ID       | Name                            | Reasoning  | Date       | Accuracy | Completeness | Total Time | Speed (T/S) | Total input | Total Thinking | Total output | Total Price $ | Score in % |
|--------------------------|---------------------------------|------------|------------|----------|--------------|------------|-------------|-------------|----------------|--------------|---------------|------------|
| GPT5_0807                | GPT-5 (08-07)                   | Yes (low)  | 2025-09-11 | 0.796    | 0.992        | 17.31      | 41.09       | 613046      | 21952          | 42680        | 1.19          | 81.59%     |
| Gemini_25_Flash          | Gemini 2.5 Flash                | Yes        | 2025-09-11 | 0.790    | 0.940        | 11.51      | 127.87      | 718866      | 61545          | 88295        | 0.42          | 80.50%     |
| GPT5_Mini_high           | GPT-5 Mini                      | Yes (high) | 2025-10-24 | 0.769    | 0.997        | 51.23      | 52.28       | 636192      | 124352         | 160700       | 0.48          | 79.21%     |
| Gemini_25_Pro            | Gemini 2.5 Pro                  | Yes        | 2025-09-11 | 0.769    | 0.962        | 20.49      | 77.01       | 718866      | 69631          | 94691        | 1.85          | 78.83%     |
| GPT51_1113               | GPT-5.1 (11-13)                 | No         | 2025-11-14 | 0.713    | 1.000        | 20.05      | 39.70       | 610241      | -              | 47761        | 1.24          | 74.17%     |
| GPT5_Codex               | GPT-5 Codex                     | Yes (low)  | 2025-09-26 | 0.704    | 0.970        | 11.67      | 49.14       | 610301      | 23232          | 34411        | 1.11          | 73.06%     |
| Gemini_25_Flash_0925     | Gemini 2.5 Flash Preview (0925) | Yes        | 2025-09-26 | 0.707    | 0.934        | 9.71       | 155.63      | 718866      | 68793          | 90663        | 0.44          | 72.97%     |
| GPT51_1113_high          | GPT-5.1 (11-13) (high)          | Yes (high) | 2025-11-14 | 0.672    | 0.992        | 64.07      | 39.27       | 610241      | 97171          | 150970       | 2.27          | 70.43%     |
| GPT5_Nano_high           | GPT-5 Nano                      | Yes (high) | 2025-10-24 | 0.627    | 0.994        | 46.74      | 86.49       | 649510      | 208768         | 242562       | 0.13          | 66.34%     |
| Claude_Haiku_45          | Claude Haiku 4.5                | No         | 2025-10-16 | 0.571    | 0.971        | 4.64       | 74.89       | 801240      | -              | 20831        | 0.91          | 61.13%     |
| Claude_Sonnet_4_Thinking | Claude Sonnet 4 (Thinking)      | Yes        | 2025-09-11 | 0.567    | 0.966        | 18.60      | 43.96       | 802110      | N/A            | 49062        | 3.14          | 60.66%     |
| Claude_Sonnet_4          | Claude Sonnet 4                 | No         | 2025-09-11 | 0.523    | 0.961        | 10.83      | 28.56       | 801240      | -              | 18563        | 2.68          | 56.68%     |
| Claude_Sonnet_45         | Claude Sonnet 4.5               | No         | 2025-09-30 | 0.503    | 0.949        | 8.46       | 37.12       | 801210      | -              | 18843        | 2.69          | 54.76%     |
| AmazonNovaPremier        | Amazon Nova Premier             | No         | 2025-09-11 | 0.489    | 0.928        | 14.85      | 16.78       | 767489      | -              | 14954        | 2.11          | 53.26%     |
| Grok4FastReasoning       | Grok 4 Fast                     | Yes        | 2025-09-26 | 0.455    | 0.982        | 14.22      | 91.42       | 586517      | 32902          | 77976        | 0.16          | 50.74%     |
| Grok4_0709               | Grok 4 (07-09)                  | Yes        | 2025-09-11 | 0.380    | 0.958        | 66.46      | 42.72       | 606242      | 138102         | 170368       | 4.37          | 43.75%     |

_Table 1. Results of evaluation LLMs in EPAM's Multimodal LLMs Benchmark._

## Conclusion

GPT-5 (81.59%) leads the multimodal benchmark, followed by Gemini 2.5 Flash (80.50%) and GPT-5 Mini (79.21%). GPT-5 Mini achieves 3rd place with excellent
cost-effectiveness ($0.48) and significantly outperforms its coding results (71.28%), demonstrating strong multimodal capabilities. Gemini 2.5 Pro (78.83%) shows Google's strength in multimodal reasoning. Gemini 2.5 Flash offers exceptional cost-effectiveness ($
0.42) with excellent speed (127.87 T/S).

GPT-5.1 (11-13) achieves 74.17% score in fifth position, showing moderate execution time (20.05 min, 39.70 tokens/sec, $1.24). Notably, the regular variant substantially outperforms its high reasoning
variant (70.43%). This contrasts with coding performance where both variants achieve top positions (83.96% and 83.36%).

GPT-5 Codex (73.06%) and Gemini 2.5 Flash Preview (72.97%) show strong cross-domain performance. GPT-5 Nano (66.34%) achieves the best
cost ($0.13) while outperforming its coding results (58.61%), following the same pattern as GPT-5 Mini where multimodal performance exceeds coding performance. Claude Haiku 4.5 achieves 61.13% with ultrafast execution (4.64 min) and excellent cost-efficiency ($
0.91), though significantly behind its coding performance (81.83%). Claude Sonnet 4.5 (54.76%) underperforms in multimodal despite coding excellence (82.19%), while Grok models (50.74%, 43.75%)
confirm specialization in text-based tasks.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>