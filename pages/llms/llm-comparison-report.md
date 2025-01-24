# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google Deepmind, xAI, and
open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction following (LCIF).

Key findings:

- OpenAI's o1-mini model demonstrated superior overall performance, achieving the highest total score of 91.7%
- Claude 3.5 Sonnet v2 and ChatGPT-4o showed strong capabilities, ranking second (89.6%) and third (89.4%) respectively
- GPT-4o (2024-11-20) showcased exceptional efficiency with the highest token processing speed (averaging 126-130 tokens/second)
- OpenAI o1 (1217) attained the highest accuracy in code translation with 94.0%.
- Claude 3.5 Sonnet v2 and Gemini Experimental (0612) both achieved perfect scores (100%) in LCIF, while maintaining strong performance across other categories
- OpenAI o1-mini excelled in code-related tasks, particularly in code documentation (96.2%) and code generation (91.9%)
- Significant performance gaps were observed between the top-tier models and more accessible options like GPT-3.5 Turbo (60.9%) and Llama3 70B (59.7%)

Best results by category:

- Code Translation: OpenAI o1 (1217) achieves the highest score (94.0%).
- Code Generation: OpenAI o1-mini (2024-09-12) ranks first (91.9%).
- Code Documentation: OpenAI o1-mini (2024-09-12) leads (96.2%).
- LCIF: Claude 3.5 Sonnet v2 and Gemini Experimental (0612) both reach 100%.

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                                                                                              | Execution Date | Benchmark version | Code Translation | Code Generation | Code Document | LCIF     | Total Score ↓ |
|----------------------------------------------------------------------------------------------------|----------------|-------------------|------------------|-----------------|---------------|----------|---------------|
| [OpenAI o1-mini (2024-09-12)](/pages/llms/llm-detailed-result/open-ai-o1-mini-2024-11-06.md)       | 2024-11-06     | v1                | 91.3%            | **91.9%**       | **96.2%**     | 87.5%    | **91.7%**     |
| [Claude 3.5 Sonnet v2](/pages/llms/llm-detailed-result/claude-35-sonnet-2024-11-06.md)             | 2024-11-06     | v1                | 91.5%            | 81.2%           | 85.7%         | **100%** | 89.6%         |
| [ChatGPT-4o](/pages/llms/llm-detailed-result/chat-gpt-4o-2024-11-06.md)                            | 2024-11-06     | v1                | 89.5%            | 84.1%           | 90.3%         | 93.8%    | 89.4%         |
| [OpenAI o1 (1217)](/pages/llms/llm-detailed-result/open-ai-o1-1217-2024-12-19.md)                  | 2024-12-19     | v1                | **94.0%**        | 78.6%           | 85.6%         | 96.88%   | 88.7%         |         
| [GPT-4o (2024-11-20)](/pages/llms/llm-detailed-result/gpt-4o-1120-2024-11-21.md)                   | 2024-11-21     | v1                | 91.7%            | 80.2%           | 95.4%         | 87.5%    | 88.7%         |
| [Claude 3.5 Haiku](/pages/llms/llm-detailed-result/claude-35-haiku-2024-11-06.md)                  | 2024-11-06     | v1                | 86.4%            | 85.6%           | 86.5%         | 87.5%    | 86.5%         |
| [Gemini Experimental (0612)](/pages/llms/llm-detailed-result/gemini-exp-1206-2024-12-19.md)        | 2024-12-19     | v1                | 90.5%            | 75.8%           | 74.6%         | 100%     | 85.2%         |
| [OpenAI o1-preview (2024-09-12)](/pages/llms/llm-detailed-result/open-ai-o1-preview-2024-11-06.md) | 2024-11-06     | v1                | 85.4%            | 81.7%           | 86.3%         | 87.5%    | 85.2%         |
| [Grok 2 (1212)](/pages/llms/llm-detailed-result/grok-2-1212-2024-12-19.md)                         | 2024-12-19     | v1                | 89.2%            | 81.7%           | 85.7%         | 81.25%   | 84.5%         |
| [Qwen 2.5 Coder 32B](llm-detailed-result/qwen25coder32b-2024-11-25.md)                             | 2024-11-25     | v1                | 90.2%            | 79.8%           | 87.7%         | 71.9%    | 82.4%         |
| [GPT-4o (2024-08-06)](/pages/llms/llm-detailed-result/gpt-4o-0806-2024-11-06.md)                   | 2024-11-06     | v1                | 84.7%            | 80.5%           | 76.1%         | 87.5%    | 82.2%         |
| [Gemini 1.5 Pro (002)](/pages/llms/llm-detailed-result/gemini-15-pro-2024-11-08.md)                | 2024-11-13     | v1                | 84.0%            | 71.3%           | 81.3%         | 87.5%    | 81.0%         |
| [Grok Beta](/pages/llms/llm-detailed-result/grok-beta-2024-11-15.md)                               | 2024-11-15     | v1                | 77.4%            | 72.4%           | 80.3%         | 81.3%    | 77.8%         |
| [Amazon Nova Pro](/pages/llms/llm-detailed-result/amazon-nova-pro-2024-12-06.md)                   | 2024-12-06     | v1                | 76.5%            | 67.6%           | 87.4%         | 56.25%   | 71.9%         |
| [Llama3.1 405B<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                     | 2024-08-01     | v1                | 75.8%            | 72.5%           | 67.7%         | 68.8%    | 71.2%         |
| [GPT-4o-mini](/pages/llms/llm-detailed-result/gpt-4o-mini-0718-2024-11-06.md)                      | 2024-11-06     | v1                | 75.9%            | 69.3%           | 81.6%         | 56.25%   | 70.8%         |
| [GPT-3.5 Turbo<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                     | 2024-08-05     | v1                | 68.8%            | 52.7%           | 78.4%         | 43.8%    | 60.9%         |
| [Llama3 70B<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                        | 2024-06-13     | v1                | 69.4%            | 72.6%           | 71.8%         | 25.0%    | 59.7%         |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

> Additional info:  
> <sup>1</sup> - For models with "LLM-based" Evaluation Approach, evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the GPT-4o model.
> Please refer the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.  
> <sup>2</sup> - Evaluation was done more than 3 month ago, results are outdated

## Results by categories

### Code Translation

| Model               | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o1_1217      | 1.000       | 4.000        | 4.000            | 68.238   | 3548.714  | 52.005            | 0.9399  |
| GPT4o_1120          | 1.000       | 3.621        | 3.546            | 15.233   | 1983.429  | 130.206           | 0.9167  |
| Claude_Sonnet_35v2  | 1.000       | 3.963        | 3.714            | 45.370   | 2790.571  | 61.507            | 0.9150  |
| OpenAi_o1_mini_0912 | 1.000       | 3.714        | 3.836            | 44.505   | 3378.286  | 75.909            | 0.9133  |
| Gemini_1206         | 1.000       | 3.861        | 3.860            | 95.260   | 4075.286  | 42.781            | 0.9050  |
| Qwen25Coder32B      | 1.000       | 3.584        | 3.714            | 26.864   | 2540.000  | 94.552            | 0.9025  |
| ChatGPT4o           | 1.000       | 3.761        | 3.503            | 22.510   | 2015.286  | 89.527            | 0.8952  |
| Grok2_1212          | 1.000       | 3.867        | 3.579            | 45.779   | 2853.857  | 62.340            | 0.8924  |
| Claude_Haiku_35     | 1.000       | 3.554        | 3.550            | 34.312   | 2377.000  | 69.275            | 0.8636  |
| OpenAi_o1_0912      | 1.000       | 3.993        | 3.460            | 245.472  | 2770.286  | 11.286            | 0.8540  |
| GPT4o_0806          | 1.000       | 3.676        | 3.311            | 35.101   | 2206.429  | 62.859            | 0.8470  |
| Gemini_15_Pro_002   | 1.000       | 3.414        | 3.686            | 69.323   | 2670.571  | 38.523            | 0.8396  |
| GrokBeta            | 1.000       | 3.193        | 3.150            | 41.902   | 2190.857  | 52.285            | 0.7744  |
| AmazonNovaPro       | 1.000       | 3.480        | 2.704            | 28.329   | 1703.571  | 60.136            | 0.7646  |
| GPT4o_mini_0718     | 1.000       | 3.410        | 2.797            | 33.108   | 1645.714  | 49.707            | 0.7589  |
| Llama31_405B        | 1.000       | 3.694        | 2.479            | 29.339   | 1563.000  | 53.274            | 0.7582  |
| Llama3_70B          | 1.000       | 3.344        | 2.496            | 121.700  | 1573.571  | 12.930            | 0.6939  |
| GPT35_Turbo_0125    | 1.000       | 3.327        | 2.021            | 18.624   | 1277.571  | 68.598            | 0.6875  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model               | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o1_mini_0912 | 1.000       | 3.547        | 3.694            | 22.358   | 2676.429  | 119.706           | 0.9186  |
| Claude_Haiku_35     | 1.000       | 3.704        | 3.346            | 24.092   | 1547.286  | 64.225            | 0.8557  |
| ChatGPT4o           | 1.000       | 3.500        | 3.251            | 13.840   | 1163.571  | 84.071            | 0.8415  |
| Grok2_1212          | 1.000       | 3.360        | 3.324            | 26.784   | 1650.714  | 61.630            | 0.8171  |
| OpenAi_o1_0912      | 1.000       | 3.459        | 3.437            | 65.719   | 2246.000  | 34.176            | 0.8165  |
| Claude_Sonnet_35v2  | 1.000       | 3.693        | 2.960            | 27.767   | 1636.429  | 58.934            | 0.8118  |
| GPT4o_0806          | 1.000       | 3.417        | 3.156            | 17.411   | 1042.714  | 59.889            | 0.8045  |
| GPT4o_1120          | 1.000       | 3.403        | 2.617            | 9.023    | 1143.429  | 126.723           | 0.8020  |
| Qwen25Coder32B      | 1.000       | 3.396        | 2.847            | 17.689   | 1654.143  | 93.511            | 0.7981  |
| OpenAi_o1_1217      | 1.000       | 3.373        | 2.991            | 26.431   | 1649.000  | 62.389            | 0.7857  |
| Gemini_1206         | 1.000       | 3.289        | 2.957            | 61.595   | 2612.571  | 42.415            | 0.7580  |
| Llama3_70B          | 1.000       | 3.330        | 2.830            | 62.691   | 808.167   | 12.891            | 0.7262  |
| Llama31_405B        | 1.000       | 3.127        | 2.816            | 30.388   | 1165.429  | 38.352            | 0.7246  |
| GrokBeta            | 1.000       | 3.516        | 2.324            | 20.738   | 1045.857  | 50.432            | 0.7238  |
| Gemini_15_Pro_002   | 1.000       | 2.864        | 2.923            | 27.487   | 1189.571  | 43.277            | 0.7129  |
| GPT4o_mini_0718     | 1.000       | 2.866        | 2.566            | 14.007   | 881.143   | 62.906            | 0.6928  |
| AmazonNovaPro       | 1.000       | 2.717        | 2.647            | 19.778   | 985.000   | 49.803            | 0.6757  |
| GPT35_Turbo_0125    | 1.000       | 2.513        | 1.281            | 7.132    | 431.286   | 60.474            | 0.5272  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model               | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o1_mini_0912 | 1.000       | 3.734        | 3.890            | 22.890   | 2938.222  | 128.362           | 0.9624  |
| GPT4o_1120          | 1.000       | 3.774        | 3.809            | 12.471   | 1535.667  | 123.142           | 0.9543  |
| ChatGPT4o           | 1.000       | 3.762        | 3.624            | 20.633   | 1700.889  | 82.435            | 0.9029  |
| Qwen25Coder32B      | 1.000       | 3.464        | 3.589            | 11.575   | 1060.889  | 91.657            | 0.8767  |
| AmazonNovaPro       | 1.000       | 3.517        | 3.741            | 17.757   | 1094.222  | 61.622            | 0.8738  |
| Claude_Haiku_35     | 1.000       | 3.669        | 3.501            | 14.084   | 860.778   | 61.117            | 0.8646  |
| OpenAi_o1_0912      | 1.000       | 3.633        | 3.727            | 69.490   | 2395.222  | 34.469            | 0.8629  |
| Claude_Sonnet_35v2  | 1.000       | 3.674        | 3.464            | 17.195   | 962.556   | 55.977            | 0.8575  |
| Grok2_1212          | 1.000       | 3.614        | 3.458            | 23.575   | 1498.333  | 63.556            | 0.8567  |
| OpenAi_o1_1217      | 1.000       | 3.561        | 3.504            | 27.209   | 1714.111  | 62.998            | 0.8556  |
| GPT4o_mini_0718     | 1.000       | 3.419        | 3.310            | 16.548   | 922.111   | 55.724            | 0.8163  |
| Gemini_15_Pro_002   | 1.000       | 3.429        | 3.463            | 35.696   | 1072.000  | 30.031            | 0.8126  |
| GrokBeta            | 1.000       | 3.358        | 3.269            | 20.916   | 1087.444  | 51.990            | 0.8032  |
| GPT35_Turbo_0125    | 1.000       | 3.409        | 2.959            | 9.818    | 589.778   | 60.071            | 0.7836  |
| GPT4o_0806          | 1.000       | 3.271        | 3.149            | 36.855   | 901.556   | 24.462            | 0.7611  |
| Gemini_1206         | 1.000       | 3.428        | 2.869            | 110.399  | 2249.556  | 20.377            | 0.7455  |
| Llama3_70B          | 1.000       | 3.342        | 2.736            | 69.926   | 880.000   | 12.585            | 0.7176  |
| Llama31_405B        | 1.000       | 2.690        | 2.658            | 17.266   | 933.222   | 54.048            | 0.6769  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model               | Avg Accuracy | Avg Completeness | Score ↓ |
|---------------------|--------------|------------------|---------|
| Claude_Sonnet_35v2  | 4.0          | 4.0              | 1.00    |
| Gemini_1206         | 4.0          | 4.0              | 1.0     |
| OpenAi_o1_1217      | 4.0          | 3.75             | 0.9688  |
| ChatGPT4o           | 3.5          | 4.0              | 0.9375  |
| OpenAi_o1_mini_0912 | 3.5          | 3.5              | 0.875   |
| OpenAi_o1_0912      | 3.5          | 3.5              | 0.875   |
| GPT4o_1120          | 3.0          | 4.0              | 0.875   |
| GPT4o_0806          | 4.0          | 3.0              | 0.875   |
| Claude_Haiku_35     | 3.5          | 3.5              | 0.875   |
| Gemini_15_Pro_002   | 3.0          | 3.2              | 0.875   |
| Grok2_1212          | 3.5          | 3.0              | 0.8125  |
| GrokBeta            | 2.5          | 4.0              | 0.8125  |
| Qwen25Coder32B      | 3.0          | 2.75             | 0.7186  |
| Llama31_405B        | 2.5          | 3.0              | 0.6875  |
| AmazonNovaPro       | 2.25         | 2.25             | 0.5625  |
| GPT4o_mini_0718     | 2.5          | 2.0              | 0.5625  |
| GPT35_Turbo_0125    | 2.0          | 1.5              | 0.4375  |
| Llama3_70B          | 1.0          | 1.0              | 0.25    |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution: Newer models (o1-mini, Claude 3.5 Sonnet v2, GPT-4o (2024-11-20)) consistently outperform their predecessors, demonstrating the rapid pace of advancement in LLM technology. The performance gap between top-tier models (>
   85%) and lower-tier models (<70%) is particularly pronounced across all evaluation categories.

2. Specialized Strengths: Different models exhibit distinct strengths:
    - OpenAI o1-mini excels in code-related tasks, achieving the highest scores in code generation (91.9%) and documentation (96.2%)
    - GPT-4o (2024-11-20) demonstrates outstanding efficiency and accuracy, leading in code translation (91.7%) and processing speed (126-130 tokens/second)
    - Claude 3.5 Sonnet v2 demonstrates exceptional performance in LCIF by achieving a perfect score (100%)

3. Performance Patterns:
    - Code Documentation shows strong results among top-tier models, with four models scoring above 90%
    - LCIF shows high variance in performance, ranging from 100% to 25%, indicating significant differences in model capabilities
    - Code Translation demonstrates consistent high performance among top models, with several achieving above 90%
    - Processing efficiency has become a key differentiator, with GPT-4o (2024-11-20) setting new standards for speed while maintaining high accuracy

4. Areas for Improvement:
    - Lower-tier models struggle significantly with LCIF tasks, with some scoring below 50%
    - Response times vary significantly across models, from 9-245 seconds in code translation tasks
    - Token processing efficiency shows wide variation, with some models processing over 100 tokens/second while others manage only 11-12 tokens/second

These findings suggest that while LLM technology has made significant strides, there is still room for improvement in areas like processing efficiency and LCIF capabilities, particularly for models outside the top tier. The emergence of
GPT-4o (2024-11-20) demonstrates that it's possible to achieve both high speed and accuracy, setting a new benchmark for model performance. The benchmark also highlights the importance of considering multiple metrics when evaluating LLM
performance, as raw capability scores don't always correlate with practical efficiency measures like response time and token processing speed.

## Outdated Evaluation Reports

- [OpenAI o1 family (end of September 2024)](/pages/llms/llm-reports/o1-family.md)
- [Claude 3.5 Sonnet, GPT-4o, Gemini 1.5 Pro, ChatGPT-4o (September 2024)](/pages/llms/llm-reports/chat-gpt4o-vs-gpt4o-0806-vs-claude3.5sonnet-vs-gemini1.5pro.md)
- [GPT-4o mini, Llama3.1 405B, GPT-3.5 Turbo, Llama 3 70B - Compare Low-cost models](/pages/llms/llm-reports/low-cost-models-august.md)

| Model                                                                                                               | Execution Date | Benchmark version | Code Translation | Code Generation | Code Document | LCIF  | Total Score |
|---------------------------------------------------------------------------------------------------------------------|----------------|-------------------|------------------|-----------------|---------------|-------|-------------|
| [Claude 3.5 Sonnet](/pages/llms/llm-reports/chat-gpt4o-vs-gpt4o-0806-vs-claude3.5sonnet-vs-gemini1.5pro.md)         | 2024-08-13     | v1                | 95.7%            | 80.5%           | 84.0%         | 100%  | 90.1%       |
| [Gemini 1.5-Pro (0801-exp)](/pages/llms/llm-reports/chat-gpt4o-vs-gpt4o-0806-vs-claude3.5sonnet-vs-gemini1.5pro.md) | 2024-04-25     | v1                | 83.3%            | 78.2%           | 76.7%         | 81.3% | 79.9%       |
| [GPT-4o (2024-05-13)](/pages/llms/llm-reports/gpt-4o-0513.md)                                                       | 2024-05-20     | v0                | 79.4%            | 78.2%           | 83.7%         | 87.5% | 82.2%       |
| [Claude 3 Opus](/pages/llms/llm-reports/claude-3-opus-gemini-pro-gpt-4-turbo.md)                                    | 2024-04-25     | v0                | 79.8%            | 78.3%           | 87.4%         | 87.5% | 83.3%       |
| [Gemini 1.5-Pro (0409)](/pages/llms/llm-reports/claude-3-opus-gemini-pro-gpt-4-turbo.md)                            | 2024-04-25     | v0                | 76.9%            | 66.3%           | 75.7%         | 81.3% | 75.0%       |
| [GPT-4 Turbo (0409)](/pages/llms/llm-reports/claude-3-opus-gemini-pro-gpt-4-turbo.md)                               | 2024-04-26     | v0                | 68.9%            | 65.0%           | 83.9%         | 81.3% | 74.8%       |

<p align="center">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>