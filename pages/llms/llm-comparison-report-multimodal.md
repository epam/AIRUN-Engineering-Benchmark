# LLM's Multimodal Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) in multimodal category. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google
Deepmind, xAI, Amazon.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach Multimodal](llm-approach-multimodal.md)

| Model                      | Benchmark model ID       | Execution Date | Benchmark | Total Time | Score  |
|----------------------------|--------------------------|----------------|-----------|------------|--------|
| GPT-5 (08-07)              | GPT5_0807                | 2025-09-10     | v3        | 17.311 min | 81.56% |
| Gemini 2.5 Flash           | Gemini_25_Flash          | 2025-09-11     | v3        | 11.509 min | 80.50% |
| Gemini 2.5 Pro             | Gemini_25_Pro            | 2025-09-11     | v3        | 20.494 min | 78.83% |
| Grok 4 (07-09)             | Grok4_0709               | 2025-09-11     | v3        | 66.464 min | 43.78% |
| Claude 4 Sonnet            | Claude_Sonnet_4          | 2025-09-11     | v3        | 10.832 min | 56.68% |
| Claude 4 Sonnet (Thinking) | Claude_Sonnet_4_Thinking | 2025-09-11     | v3        | 18.602 min | 60.69% |
| Amazon Nova Premier        | AmazonNovaPremier        | 2025-09-11     | v3        | 14.849 min | 53.29% |

_Table 1. Results of evaluation LLMs in EPAM's Multimodal LLMs Benchmark._

## Conclusion

The benchmark results identify three top-performing models: GPT5, Gemini 2.5 Flash, Gemini 2.5 Pro. Considering execution time and price the best choice is Gemini 2.5 Flash.
Claude 4 Sonnet takes middle position. Thinking mode slightly improves accuracy (60.69% vs. 56.68%) but takes 72% more time (18.602 min vs. 10.832 min).
Amazon Nova Premier delivers mid-level performance (53.29%) with a moderate execution time (14.849 min).
Grok 4 finishes in last place (43.78%) with the slowest execution time (66.464 min), making it impractical for most use cases.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>