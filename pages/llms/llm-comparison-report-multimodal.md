# LLM's Multimodal Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) in multimodal category. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google
Deepmind, xAI, Amazon.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach Multimodal](llm-approach-multimodal.md)

| Model                           | Benchmark model ID       | Reasoning | Execution Date | Total Time | Speed (T/S) | Total input | Total Thinking | Total output | Score in % |
|---------------------------------|--------------------------|-----------|----------------|------------|-------------|-------------|----------------|--------------|------------|
| GPT-5 (08-07)                   | GPT5_0807                | Yes (low) | 2025-09-11     | 17.31      | 41.09       | 613046      | 21952          | 42680        | 81.59%     |
| Gemini 2.5 Flash                | Gemini_25_Flash          | Yes       | 2025-09-11     | 11.51      | 127.87      | 718866      | 61545          | 88295        | 80.50%     |
| Gemini 2.5 Pro                  | Gemini_25_Pro            | Yes       | 2025-09-11     | 20.49      | 77.01       | 718866      | 69631          | 94691        | 78.83%     |
| GPT-5 Codex                     | GPT5_Codex               | Yes (low) | 2025-09-26     | 11.67      | 49.14       | 610301      | 23232          | 34411        | 73.06%     |
| Gemini 2.5 Flash Preview (0925) | Gemini_25_Flash_0925     | Yes       | 2025-09-26     | 9.71       | 155.63      | 718866      | 68793          | 90663        | 72.97%     |
| Claude 4 Sonnet (Thinking)      | Claude_Sonnet_4_Thinking | Yes       | 2025-09-11     | 18.60      | 43.96       | 802110      | N/A            | 49062        | 60.66%     |
| Claude 4 Sonnet                 | Claude_Sonnet_4          | No        | 2025-09-11     | 10.83      | 28.56       | 801240      | -              | 18563        | 56.68%     |
| Claude 4.5 Sonnet               | Claude_Sonnet_45         | No        | 2025-09-30     | 8.46       | 37.12       | 801210      | -              | 18843        | 54.76%     |
| Amazon Nova Premier             | AmazonNovaPremier        | No        | 2025-09-11     | 14.85      | 16.78       | 767489      | -              | 14954        | 53.26%     |
| Grok 4 Fast                     | Grok4FastReasoning       | Yes       | 2025-09-26     | 14.22      | 91.42       | 586517      | 32902          | 77976        | 50.74%     |
| Grok 4 (07-09)                  | Grok4_0709               | Yes       | 2025-09-11     | 66.46      | 42.72       | 606242      | 138102         | 170368       | 43.75%     |

_Table 1. Results of evaluation LLMs in EPAM's Multimodal LLMs Benchmark._

## Conclusion

GPT-5 (81.59%) leads the multimodal benchmark, followed by Gemini 2.5 Flash (80.50%) and Gemini 2.5 Pro (78.83%). Gemini 2.5 Flash offers the best cost-effectiveness ($0.42) with excellent speed (
127.87 T/S).

GPT-5 Codex (73.06%) and Gemini 2.5 Flash Preview (72.97%) show strong cross-domain performance. Claude 4.5 Sonnet (54.76%) underperforms in multimodal despite coding excellence (82.19%), while Grok
models (50.74%, 43.75%) confirm specialization in text-based tasks.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>