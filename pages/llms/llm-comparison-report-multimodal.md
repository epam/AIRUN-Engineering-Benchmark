# LLM's Multimodal Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) in multimodal category. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google
Deepmind, xAI, Amazon.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach Multimodal](llm-approach-multimodal.md)

| Benchmark model ID   | Name                   | Reasoning  | Date       | Accuracy | Completeness | Total Time | Speed (T/S) | Total input | Total Thinking | Total output | Total Price $ | Score in % |
|----------------------|------------------------|------------|------------|----------|--------------|------------|-------------|-------------|----------------|--------------|---------------|------------|
| Gemini_3_Pro_Preview | Gemini 3 Pro Preview   | Yes (high) | 2025-11-19 | 0.809    | 0.973        | 25.70      | 81.67       | 743882      | 107774         | 125944       | 3.00          | 82.54%     |
| GPT5_Mini_high       | GPT-5 Mini             | Yes (high) | 2025-10-24 | 0.769    | 0.997        | 51.23      | 52.28       | 636192      | 124352         | 160700       | 0.48          | 79.21%     |
| GPT51_1113           | GPT-5.1 (11-13)        | No         | 2025-11-14 | 0.713    | 1.000        | 20.05      | 39.70       | 610241      | -              | 47761        | 1.24          | 74.17%     |
| GPT5_Codex           | GPT-5 Codex            | Yes (low)  | 2025-09-26 | 0.704    | 0.970        | 11.67      | 49.14       | 610301      | 23232          | 34411        | 1.11          | 73.06%     |
| GPT51_1113_high      | GPT-5.1 (11-13) (high) | Yes (high) | 2025-11-14 | 0.672    | 0.992        | 64.07      | 39.27       | 610241      | 97171          | 150970       | 2.27          | 70.43%     |
| GPT5_Nano_high       | GPT-5 Nano             | Yes (high) | 2025-10-24 | 0.627    | 0.994        | 46.74      | 86.49       | 649510      | 208768         | 242562       | 0.13          | 66.34%     |
| Claude_Haiku_45      | Claude Haiku 4.5       | No         | 2025-10-16 | 0.571    | 0.971        | 4.64       | 74.89       | 801240      | -              | 20831        | 0.91          | 61.13%     |
| Claude_Sonnet_45     | Claude Sonnet 4.5      | No         | 2025-09-30 | 0.503    | 0.949        | 8.46       | 37.12       | 801210      | -              | 18843        | 2.69          | 54.76%     |
| AmazonNovaPremier    | Amazon Nova Premier    | No         | 2025-09-11 | 0.489    | 0.928        | 14.85      | 16.78       | 767489      | -              | 14954        | 2.11          | 53.26%     |
| Grok4FastReasoning   | Grok 4 Fast            | Yes        | 2025-09-26 | 0.455    | 0.982        | 14.22      | 91.42       | 586517      | 32902          | 77976        | 0.16          | 50.74%     |
| Grok4_0709           | Grok 4 (07-09)         | Yes        | 2025-09-11 | 0.380    | 0.958        | 66.46      | 42.72       | 606242      | 138102         | 170368       | 4.37          | 43.75%     |

_Table 1. Results of evaluation LLMs in EPAM's Multimodal LLMs Benchmark._

## Conclusion

Gemini 3 Pro Preview establishes new multimodal leadership with 82.54% score, surpassing all previous models with excellent accuracy (80.9%), fast execution (25.70 min, 81.67 T/S), and reasonable
cost ($3.00). This represents Google's strongest multimodal performance, though pricing increased to $2/$12 for <200K context (up from $1.25/$10). Unlike its constrained coding performance (70.25%)
where token generation limits severely impact results, the model excels in multimodal tasks where output requirements remain moderate.

GPT-5 Mini achieves 79.21% in second place with excellent cost-effectiveness ($0.48), significantly outperforming its coding results (71.28%) and demonstrating strong multimodal capabilities.
GPT-5.1 (11-13) achieves 74.17% in third position with moderate execution time (20.05 min, 39.70 T/S, $1.24), notably outperforming its high reasoning variant (70.43%), contrasting with coding
performance where both variants achieve top positions (83.96% and 83.36%).

GPT-5 Codex (73.06%) shows strong cross-domain performance. GPT-5 Nano (66.34%) achieves best cost ($0.13) while outperforming its coding results (58.61%), following the same pattern as GPT-5 Mini
where multimodal performance exceeds coding performance. Claude Haiku 4.5 achieves 61.13% with ultrafast execution (4.64 min) and excellent cost-efficiency ($0.91), though significantly behind its
coding performance (81.83%). Claude Sonnet 4.5 (54.76%) underperforms in multimodal despite coding excellence (82.19%), while Grok models (50.74%, 43.75%)confirm specialization in text-based tasks.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>