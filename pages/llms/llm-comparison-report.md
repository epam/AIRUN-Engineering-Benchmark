# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google Deepmind, xAI, and
open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction following (LCIF).

Key findings:

- OpenAI's o3-mini model demonstrates strong performance while offering improved cost-efficiency and new features like function calling and structured outputs
- OpenAI's o1 maintains superior overall performance with the highest total score of 89.4%
- DeepSeek R1, a new open-source LLM, shows promising results for self-hosted solutions, though with notable computational overhead
- Claude 3.5 Sonnet v2, Gemini Experimental (0612), OpenAI o3-mini achieved perfect scores (100%) in LCIF
- Significant performance gaps persist between top-tier commercial models and more accessible options

- Best results by category:

Code Translation: OpenAI o3-mini leads with 96.8%
Code Generation: OpenAI o1-mini ranks first (92.4%)
Code Documentation: OpenAI o1-mini leads (96.2%)
LCIF: Three models achieve 100%: OpenAI o3-mini, Claude 3.5 Sonnet v2, and Gemini Experimental

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                                                                                              | Execution Date | Benchmark | Code Translation | Code Generation | Code Document | LCIF  | Total Score ↓ |
|----------------------------------------------------------------------------------------------------|----------------|-----------|------------------|-----------------|---------------|-------|---------------|
| [OpenAI o3-mini (2025-01-31)](/pages/llms/llm-detailed-result/open-ai-o3-mini-2025-02-03.md)       | 2025-02-03     | v1        | 96.8%            | 81.0%           | 91.6%         | 100%  | **92.4%**     |
| [OpenAI o1-mini (2024-09-12)](/pages/llms/llm-detailed-result/open-ai-o1-mini-2024-11-06.md)       | 2024-11-06     | v1        | 92.9%            | 92.4%           | 96.2%         | 87.5% | 92.3%         |
| [OpenAI o1 (1217)](/pages/llms/llm-detailed-result/open-ai-o1-1217-2024-12-19.md)                  | 2024-12-19     | v1        | 94.9%            | 79.8%           | 86.0%         | 96.9% | 89.4%         |
| [Claude 3.5 Sonnet v2](/pages/llms/llm-detailed-result/claude-35-sonnet-2024-11-06.md)             | 2024-11-06     | v1        | 90.2%            | 79.9%           | 84.9%         | 100%  | 88.7%         |
| [ChatGPT-4o](/pages/llms/llm-detailed-result/chat-gpt-4o-2024-11-06.md)                            | 2024-11-06     | v1        | 87.6%            | 82.4%           | 89.0%         | 93.8% | 88.2%         |
| [GPT-4o (2024-11-20)](/pages/llms/llm-detailed-result/gpt-4o-1120-2024-11-21.md)                   | 2024-11-21     | v1        | 88.8%            | 77.5%           | 93.5%         | 87.5% | 86.9%         |
| [OpenAI o1-preview (2024-09-12)](/pages/llms/llm-detailed-result/open-ai-o1-preview-2024-11-06.md) | 2024-11-06     | v1        | 86.7%            | 83.6%           | 88.3%         | 87.5% | 86.5%         |
| [Claude 3.5 Haiku](/pages/llms/llm-detailed-result/claude-35-haiku-2024-11-06.md)                  | 2024-11-06     | v1        | 84.9%            | 84.2%           | 85.5%         | 87.5% | 85.5%         |
| [Gemini Experimental (0612)](/pages/llms/llm-detailed-result/gemini-exp-1206-2024-12-19.md)        | 2024-12-19     | v1        | 89.6%            | 74.9%           | 74.2%         | 100%  | 84.7%         |
| [Grok 2 (1212)](/pages/llms/llm-detailed-result/grok-2-1212-2024-12-19.md)                         | 2024-12-19     | v1        | 87.9%            | 80.4%           | 84.7%         | 81.3% | 83.6%         |
| [GPT-4o (2024-08-06)](/pages/llms/llm-detailed-result/gpt-4o-0806-2024-11-06.md)                   | 2024-11-06     | v1        | 83.3%            | 79.2%           | 75.7%         | 87.5% | 81.4%         |
| [Qwen 2.5 Coder 32B](llm-detailed-result/qwen25coder32b-2024-11-25.md)                             | 2024-11-25     | v1        | 88.2%            | 77.8%           | 86.3%         | 71.9% | 81.0%         |
| [Gemini 1.5 Pro (002)](/pages/llms/llm-detailed-result/gemini-15-pro-2024-11-08.md)                | 2024-11-13     | v1        | 83.1%            | 70.4%           | 80.8%         | 87.5% | 80.4%         |
| [DeepSeek R1](/pages/llms/llm-detailed-result/deepseek-r1-2025-01-28.md)                           | 2025-01-28     | v1        | 83.9%            | 74.2%           | 82.8%         | 75.0% | 79.0%         |
| [Grok Beta](/pages/llms/llm-detailed-result/grok-beta-2024-11-15.md)                               | 2024-11-15     | v1        | 76.3%            | 71.3%           | 79.5%         | 81.3% | 77.1%         |
| [Amazon Nova Pro](/pages/llms/llm-detailed-result/amazon-nova-pro-2024-12-06.md)                   | 2024-12-06     | v1        | 75.2%            | 66.5%           | 86.4%         | 56.3% | 71.1%         |
| [Llama3.1 405B<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                     | 2024-08-01     | v1        | 74.7%            | 71.6%           | 66.9%         | 68.8% | 70.5%         |
| [GPT-4o-mini](/pages/llms/llm-detailed-result/gpt-4o-mini-0718-2024-11-06.md)                      | 2024-11-06     | v1        | 74.8%            | 67.9%           | 80.8%         | 56.3% | 69.9%         |
| [GPT-3.5 Turbo<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                     | 2024-08-05     | v1        | 67.3%            | 51.4%           | 77.4%         | 43.8% | 60.0%         |
| [Llama3 70B<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                        | 2024-06-13     | v1        | 69.1%            | 72.3%           | 71.6%         | 25.0% | 59.5%         |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._


> Additional info:  
> <sup>1</sup> - For models with "LLM-based" Evaluation Approach, evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the GPT-4o model.
> Please refer the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.  
> <sup>2</sup> - Evaluation was done more than 3 month ago, results are outdated

## Results by categories

### Code Translation

| Model               | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o3_mini_0131 | 1.000       | 3.823        | 3.857            | 31.948   | 5796.143  | 181.422           | 0.9680  |
| OpenAi_o1_1217      | 1.000       | 4.000        | 4.000            | 68.238   | 6072.143  | 88.984            | 0.9490  |
| OpenAi_o1_mini_0912 | 1.000       | 3.714        | 3.836            | 44.505   | 6002.286  | 134.869           | 0.9293  |
| Claude_Sonnet_35v2  | 1.000       | 3.963        | 3.714            | 45.370   | 2790.571  | 61.507            | 0.9016  |
| Gemini_1206         | 1.000       | 3.861        | 3.860            | 95.260   | 4075.286  | 42.781            | 0.8957  |
| GPT4o_1120          | 1.000       | 3.621        | 3.546            | 15.233   | 1983.429  | 130.206           | 0.8885  |
| Qwen25Coder32B      | 1.000       | 3.584        | 3.714            | 26.864   | 2540.000  | 94.552            | 0.8820  |
| Grok2_1212          | 1.000       | 3.867        | 3.579            | 45.779   | 2853.857  | 62.340            | 0.8789  |
| ChatGPT4o           | 1.000       | 3.761        | 3.503            | 22.510   | 2015.286  | 89.527            | 0.8758  |
| OpenAi_o1_0912      | 1.000       | 3.993        | 3.460            | 245.472  | 9490.286  | 38.661            | 0.8666  |
| Claude_Haiku_35     | 1.000       | 3.554        | 3.550            | 34.312   | 2377.000  | 69.275            | 0.8486  |
| DeepSeekR1          | 1.000       | 3.866        | 3.430            | 177.810  | 3182.714  | 17.899            | 0.8394  |
| GPT4o_0806          | 1.000       | 3.676        | 3.311            | 35.101   | 2206.429  | 62.859            | 0.8334  |
| Gemini_15_Pro_002   | 1.000       | 3.414        | 3.686            | 69.323   | 2670.571  | 38.523            | 0.8312  |
| GrokBeta            | 1.000       | 3.193        | 3.150            | 41.902   | 2190.857  | 52.285            | 0.7631  |
| AmazonNovaPro       | 1.000       | 3.480        | 2.704            | 28.329   | 1703.571  | 60.136            | 0.7516  |
| GPT4o_mini_0718     | 1.000       | 3.410        | 2.797            | 33.108   | 1645.714  | 49.707            | 0.7481  |
| Llama31_405B        | 1.000       | 3.694        | 2.479            | 29.339   | 1563.000  | 53.274            | 0.7467  |
| Llama3_70B          | 1.000       | 3.344        | 2.496            | 121.700  | 1573.571  | 12.930            | 0.6911  |
| GPT35_Turbo_0125    | 1.000       | 3.327        | 2.021            | 18.624   | 1277.571  | 68.598            | 0.6727  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model               | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o1_mini_0912 | 1.000       | 3.547        | 3.694            | 22.358   | 3874.143  | 173.275           | 0.9241  |
| Claude_Haiku_35     | 1.000       | 3.704        | 3.346            | 24.092   | 1547.286  | 64.225            | 0.8421  |
| OpenAi_o1_0912      | 1.000       | 3.459        | 3.437            | 65.719   | 5308.857  | 80.781            | 0.8362  |
| ChatGPT4o           | 1.000       | 3.500        | 3.251            | 13.840   | 1163.571  | 84.071            | 0.8237  |
| OpenAi_o3_mini_0131 | 1.000       | 3.369        | 2.919            | 31.094   | 4398.286  | 141.452           | 0.8103  |
| Grok2_1212          | 1.000       | 3.360        | 3.324            | 26.784   | 1650.714  | 61.630            | 0.8040  |
| Claude_Sonnet_35v2  | 1.000       | 3.693        | 2.960            | 27.767   | 1636.429  | 58.934            | 0.7993  |
| OpenAi_o1_1217      | 1.000       | 3.373        | 2.991            | 26.431   | 2810.143  | 106.321           | 0.7978  |
| GPT4o_0806          | 1.000       | 3.417        | 3.156            | 17.411   | 1042.714  | 59.889            | 0.7918  |
| Qwen25Coder32B      | 1.000       | 3.396        | 2.847            | 17.689   | 1654.143  | 93.511            | 0.7783  |
| GPT4o_1120          | 1.000       | 3.403        | 2.617            | 9.023    | 1143.429  | 126.723           | 0.7751  |
| Gemini_1206         | 1.000       | 3.289        | 2.957            | 61.595   | 2612.571  | 42.415            | 0.7490  |
| DeepSeekR1          | 1.000       | 3.369        | 2.951            | 204.696  | 3700.286  | 18.077            | 0.7424  |
| Llama3_70B          | 1.000       | 3.330        | 2.830            | 62.691   | 808.167   | 12.891            | 0.7234  |
| Llama31_405B        | 1.000       | 3.127        | 2.816            | 30.388   | 1165.429  | 38.352            | 0.7164  |
| GrokBeta            | 1.000       | 3.516        | 2.324            | 20.738   | 1045.857  | 50.432            | 0.7131  |
| Gemini_15_Pro_002   | 1.000       | 2.864        | 2.923            | 27.487   | 1189.571  | 43.277            | 0.7037  |
| GPT4o_mini_0718     | 1.000       | 2.866        | 2.566            | 14.007   | 881.143   | 62.906            | 0.6794  |
| AmazonNovaPro       | 1.000       | 2.717        | 2.647            | 19.778   | 985.000   | 49.803            | 0.6652  |
| GPT35_Turbo_0125    | 1.000       | 2.513        | 1.281            | 7.132    | 431.286   | 60.474            | 0.5143  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model               | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o1_mini_0912 | 1.000       | 3.734        | 3.890            | 22.890   | 3656.444  | 159.739           | 0.9624  |
| GPT4o_1120          | 1.000       | 3.774        | 3.809            | 12.471   | 1535.667  | 123.142           | 0.9354  |
| OpenAi_o3_mini_0131 | 1.000       | 3.470        | 3.759            | 14.252   | 2130.333  | 149.472           | 0.9165  |
| ChatGPT4o           | 1.000       | 3.762        | 3.624            | 20.633   | 1700.889  | 82.435            | 0.8903  |
| OpenAi_o1_0912      | 1.000       | 3.633        | 3.727            | 69.490   | 5189.889  | 74.686            | 0.8828  |
| AmazonNovaPro       | 1.000       | 3.517        | 3.741            | 17.757   | 1094.222  | 61.622            | 0.8644  |
| Qwen25Coder32B      | 1.000       | 3.464        | 3.589            | 11.575   | 1060.889  | 91.657            | 0.8627  |
| OpenAi_o1_1217      | 1.000       | 3.561        | 3.504            | 27.209   | 2332.778  | 85.736            | 0.8602  |
| Claude_Haiku_35     | 1.000       | 3.669        | 3.501            | 14.084   | 860.778   | 61.117            | 0.8553  |
| Claude_Sonnet_35v2  | 1.000       | 3.674        | 3.464            | 17.195   | 962.556   | 55.977            | 0.8489  |
| Grok2_1212          | 1.000       | 3.614        | 3.458            | 23.575   | 1498.333  | 63.556            | 0.8470  |
| DeepSeekR1          | 1.000       | 3.578        | 3.591            | 94.448   | 1647.889  | 17.448            | 0.8278  |
| Gemini_15_Pro_002   | 1.000       | 3.429        | 3.463            | 35.696   | 1072.000  | 30.031            | 0.8080  |
| GPT4o_mini_0718     | 1.000       | 3.419        | 3.310            | 16.548   | 922.111   | 55.724            | 0.8078  |
| GrokBeta            | 1.000       | 3.358        | 3.269            | 20.916   | 1087.444  | 51.990            | 0.7952  |
| GPT35_Turbo_0125    | 1.000       | 3.409        | 2.959            | 9.818    | 589.778   | 60.071            | 0.7744  |
| GPT4o_0806          | 1.000       | 3.271        | 3.149            | 36.855   | 901.556   | 24.462            | 0.7573  |
| Gemini_1206         | 1.000       | 3.428        | 2.869            | 110.399  | 2249.556  | 20.377            | 0.7424  |
| Llama3_70B          | 1.000       | 3.342        | 2.736            | 69.926   | 880.000   | 12.585            | 0.7157  |
| Llama31_405B        | 1.000       | 2.690        | 2.658            | 17.266   | 933.222   | 54.048            | 0.6686  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model               | Avg Accuracy | Avg Completeness | Score ↓ |
|---------------------|--------------|------------------|---------|
| OpenAi_o3_mini_0131 | 4.0          | 4.0              | 1.00    |
| Claude_Sonnet_35v2  | 4.0          | 4.0              | 1.00    |
| Gemini_1206         | 4.0          | 4.0              | 1.00    |
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
| DeepSeekR1          | 3.0          | 3.0              | 0.750   |
| Qwen25Coder32B      | 3.0          | 2.75             | 0.7186  |
| Llama31_405B        | 2.5          | 3.0              | 0.6875  |
| AmazonNovaPro       | 2.25         | 2.25             | 0.5625  |
| GPT4o_mini_0718     | 2.5          | 2.0              | 0.5625  |
| GPT35_Turbo_0125    | 2.0          | 1.5              | 0.4375  |
| Llama3_70B          | 1.0          | 1.0              | 0.25    |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution and Accessibility:
    - The introduction of OpenAI's o3-mini demonstrates that high performance can be achieved with improved cost-efficiency
    - New features like function calling and structured outputs in o3-mini represent meaningful advances in model capabilities
    - The emergence of competitive open-source models like DeepSeek R1 shows promise for self-hosted solutions, despite computational trade-offs
    - Newer models consistently outperform their predecessors

2. Performance Patterns:
    - Top-tier models consistently achieve >85% scores across categories
    - Code-related tasks show strong results among leading models, with several achieving above 90%
    - LCIF capabilities show high variance, with perfect scores from some models while others struggle significantly
    - Processing efficiency remains a key differentiator, particularly evident in DeepSeek R1's longer computation times

3. Market Implications:
    - The gap between commercial and open-source models is narrowing, though with clear trade-offs in computational efficiency
    - Cost-effectiveness is becoming a more prominent factor in model selection, as demonstrated by o3-mini's positioning
    - The ability to self-host models like DeepSeek R1 offers new possibilities for organizations with specific deployment requirements

4. Areas for Improvement:
    - Computational efficiency remains a challenge for open-source models
    - Response times vary significantly across models, particularly in complex reasoning tasks
    - Cost-performance balance continues to be a key consideration for model selection

These findings suggest that while LLM technology continues to advance, the market is diversifying with options optimized for different use cases and deployment scenarios. The introduction of more cost-effective models with advanced
features (like o3-mini) and capable open-source alternatives (like DeepSeek R1) indicates a maturing market that offers more choices for different organizational needs and constraints.

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
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>