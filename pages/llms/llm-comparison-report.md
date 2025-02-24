# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI, Anthropic, Google Deepmind, xAI, and
open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction following (LCIF).

Key findings:

- OpenAI's o3-mini and o1-mini models share the top position with 91.3% total score
- Gemini 2.0 Pro Experimental shows strong performance with 89.8% overall score
- Gemini 2.0 Flash Thinking excels in code translation with 97.5%
- Three models achieved perfect scores (100%) in LCIF: OpenAI o3-mini, Claude 3.5 Sonnet v2 and Gemini Experimental
- DeepSeek R1 demonstrates competitive performance (84.0%) as an open-source alternative

Best results by category:

- Code Translation: Gemini 2.0 Flash Thinking leads with 97.5%, followed by OpenAI o3-mini at 94.4%
- Code Generation: OpenAI o1-mini ranks first (91.2%), followed by Gemini 2.0 Flash Thinking (88.6%)
- Code Documentation: OpenAI o1-mini leads (95.3%), followed by GPT4o 1120 (92.8%)
- LCIF: Three models achieve 100%: OpenAI o3-mini, Claude 3.5 Sonnet v2, and Gemini Experimental

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                                                                                                                     | Execution Date | Benchmark | Code Translation | Code Generation | Code Document | LCIF   | Total Score ↓ |
|---------------------------------------------------------------------------------------------------------------------------|----------------|-----------|------------------|-----------------|---------------|--------|---------------|
| [OpenAI o3-mini (2025-01-31)](/pages/llms/llm-detailed-result/open-ai-o3-mini-2025-02-03.md)                              | 2025-02-03     | v1        | 94.4%            | 80.1%           | 90.7%         | 100.0% | 91.3%         |
| [OpenAI o1-mini (2024-09-12)](/pages/llms/llm-detailed-result/open-ai-o1-mini-2024-11-06.md)                              | 2024-11-06     | v1        | 91.1%            | 91.2%           | 95.3%         | 87.5%  | 91.3%         |
| [Gemini 2.0 Pro Experimental (0205)](/pages/llms/llm-detailed-result/gemini-20-pro-0205-2025-02-14.md)                    | 2025-02-14     | v1        | 90.8%            | 81.8%           | 89.6%         | 96.9%  | 89.8%         |
| [OpenAI o1 (1217)](/pages/llms/llm-detailed-result/open-ai-o1-1217-2024-12-19.md)                                         | 2024-12-19     | v1        | 93.7%            | 79.1%           | 85.5%         | 96.9%  | 88.8%         |
| [Gemini 2.0 Flash Thinking Experimental (0121)](/pages/llms/llm-detailed-result/gemini-20-flash-think-0121-2025-02-14.md) | 2025-02-14     | v1        | 97.5%            | 88.6%           | 87.0%         | 81.3%  | 88.6%         |
| [Claude 3.5 Sonnet v2](/pages/llms/llm-detailed-result/claude-35-sonnet-2024-11-06.md)                                    | 2024-11-06     | v1        | 89.3%            | 79.5%           | 84.6%         | 100.0% | 88.4%         |
| [ChatGPT-4o](/pages/llms/llm-detailed-result/chat-gpt-4o-2024-11-06.md)                                                   | 2024-11-06     | v1        | 86.4%            | 81.8%           | 88.5%         | 93.8%  | 87.6%         |
| [OpenAI o1-preview (2024-09-12)](/pages/llms/llm-detailed-result/open-ai-o1-preview-2024-11-06.md)                        | 2024-11-06     | v1        | 86.1%            | 83.1%           | 87.8%         | 87.5%  | 86.1%         |
| [GPT-4o (2024-11-20)](/pages/llms/llm-detailed-result/gpt-4o-1120-2024-11-21.md)                                          | 2024-11-21     | v1        | 87.1%            | 76.7%           | 92.8%         | 87.5%  | 86.0%         |
| [Claude 3.5 Haiku](/pages/llms/llm-detailed-result/claude-35-haiku-2024-11-06.md)                                         | 2024-11-06     | v1        | 83.9%            | 83.8%           | 85.2%         | 87.5%  | 85.1%         |
| [Gemini Experimental (1206)](/pages/llms/llm-detailed-result/gemini-exp-1206-2024-12-19.md)                               | 2024-12-19     | v1        | 89.0%            | 74.6%           | 74.1%         | 100.0% | 84.4%         |
| [DeepSeek R1](/pages/llms/llm-detailed-result/deepseek-r1-2025-02-18.md)                                                  | 2025-02-18     | v1        | 86.8%            | 83.9%           | 87.3%         | 78.1%  | 84.0%         |
| [Grok 2 (1212)](/pages/llms/llm-detailed-result/grok-2-1212-2024-12-19.md)                                                | 2024-12-19     | v1        | 87.1%            | 80.0%           | 84.3%         | 81.3%  | 83.2%         |
| [GPT-4o (2024-08-06)](/pages/llms/llm-detailed-result/gpt-4o-0806-2024-11-06.md)                                          | 2024-11-06     | v1        | 82.5%            | 78.8%           | 75.6%         | 87.5%  | 81.1%         |
| [Qwen 2.5 Coder 32B](llm-detailed-result/qwen25coder32b-2024-11-25.md)                                                    | 2024-11-25     | v1        | 86.9%            | 77.2%           | 85.7%         | 71.9%  | 80.4%         |
| [Gemini 1.5 Pro (002)](/pages/llms/llm-detailed-result/gemini-15-pro-2024-11-08.md)                                       | 2024-11-13     | v1        | 82.6%            | 70.1%           | 80.6%         | 87.5%  | 80.2%         |
| [Grok Beta](/pages/llms/llm-detailed-result/grok-beta-2024-11-15.md)                                                      | 2024-11-15     | v1        | 75.6%            | 71.0%           | 79.2%         | 81.3%  | 76.8%         |
| [Amazon Nova Pro](/pages/llms/llm-detailed-result/amazon-nova-pro-2024-12-06.md)                                          | 2024-12-06     | v1        | 74.3%            | 66.2%           | 86.1%         | 56.3%  | 70.7%         |
| [Llama3.1 405B<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                                            | 2024-08-01     | v1        | 73.9%            | 71.4%           | 66.5%         | 68.8%  | 70.2%         |
| [GPT-4o-mini](/pages/llms/llm-detailed-result/gpt-4o-mini-0718-2024-11-06.md)                                             | 2024-11-06     | v1        | 74.1%            | 67.5%           | 80.4%         | 56.3%  | 69.6%         |
| [GPT-3.5 Turbo<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                                            | 2024-08-05     | v1        | 66.3%            | 51.0%           | 77.1%         | 43.8%  | 59.5%         |
| [Llama3 70B<sup>2</sup>](/pages/llms/llm-reports/low-cost-models-august.md)                                               | 2024-06-13     | v1        | 68.9%            | 72.3%           | 71.5%         | 25.0%  | 59.4%         |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._


> Additional info:  
> <sup>1</sup> - For models with "LLM-based" Evaluation Approach, evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the GPT-4o model.
> Please refer the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.  
> <sup>2</sup> - Evaluation was done more than 3 month ago, results are outdated

## Results by categories

### Code Translation

| Model                      | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_20_Flash_Think_0121 | 1.000       | 3.859        | 3.896            | 20.847   | 5001.143  | 239.903           | 0.9754  |
| OpenAi_o3_mini_0131        | 1.000       | 3.823        | 3.857            | 31.948   | 5796.143  | 181.422           | 0.9436  |
| Gemini_20_Pro_0205         | 1.000       | 3.870        | 3.726            | 32.929   | 3834.286  | 116.440           | 0.9081  |
| OpenAi_o1_1217             | 1.000       | 4.000        | 4.000            | 68.238   | 6072.143  | 88.984            | 0.9371  |
| OpenAi_o1_mini_0912        | 1.000       | 3.714        | 3.836            | 44.505   | 6002.286  | 134.869           | 0.9112  |
| Claude_Sonnet_35v2         | 1.000       | 3.963        | 3.714            | 45.370   | 2790.571  | 61.507            | 0.8934  |
| Gemini_1206                | 1.000       | 3.861        | 3.860            | 95.260   | 4075.286  | 42.781            | 0.8900  |
| GPT4o_1120                 | 1.000       | 3.621        | 3.546            | 15.233   | 1983.429  | 130.206           | 0.8710  |
| Grok2_1212                 | 1.000       | 3.867        | 3.579            | 45.779   | 2853.857  | 62.340            | 0.8706  |
| Qwen25Coder32B             | 1.000       | 3.584        | 3.714            | 26.864   | 2540.000  | 94.552            | 0.8693  |
| DeepSeekR1                 | 1.000       | 3.736        | 3.714            | 77.168   | 4303.714  | 55.771            | 0.8682  |
| ChatGPT4o                  | 1.000       | 3.761        | 3.503            | 22.510   | 2015.286  | 89.527            | 0.8637  |
| OpenAi_o1_0912             | 1.000       | 3.993        | 3.460            | 245.472  | 9490.286  | 38.661            | 0.8614  |
| Claude_Haiku_35            | 1.000       | 3.554        | 3.550            | 34.312   | 2377.000  | 69.275            | 0.8393  |
| Gemini_15_Pro_002          | 1.000       | 3.414        | 3.686            | 69.323   | 2670.571  | 38.523            | 0.8261  |
| GPT4o_0806                 | 1.000       | 3.676        | 3.311            | 35.101   | 2206.429  | 62.859            | 0.8249  |
| GrokBeta                   | 1.000       | 3.193        | 3.150            | 41.902   | 2190.857  | 52.285            | 0.7561  |
| AmazonNovaPro              | 1.000       | 3.480        | 2.704            | 28.329   | 1703.571  | 60.136            | 0.7435  |
| GPT4o_mini_0718            | 1.000       | 3.410        | 2.797            | 33.108   | 1645.714  | 49.707            | 0.7414  |
| Llama31_405B               | 1.000       | 3.694        | 2.479            | 29.339   | 1563.000  | 53.274            | 0.7395  |
| Llama3_70B                 | 1.000       | 3.344        | 2.496            | 121.700  | 1573.571  | 12.930            | 0.6894  |
| GPT35_Turbo_0125           | 1.000       | 3.327        | 2.021            | 18.624   | 1277.571  | 68.598            | 0.6635  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                      | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o1_mini_0912        | 1.000       | 3.547        | 3.694            | 22.358   | 3874.143  | 173.275           | 0.9125  |
| Gemini_20_Flash_Think_0121 | 1.000       | 3.184        | 3.677            | 17.350   | 3402.571  | 196.113           | 0.8861  |
| DeepSeekR1                 | 1.000       | 3.549        | 3.610            | 74.952   | 3333.000  | 44.468            | 0.8385  |
| Claude_Haiku_35            | 1.000       | 3.704        | 3.346            | 24.092   | 1547.286  | 64.225            | 0.8377  |
| OpenAi_o1_0912             | 1.000       | 3.459        | 3.437            | 65.719   | 5308.857  | 80.781            | 0.8308  |
| Gemini_20_Pro_0205         | 1.000       | 3.083        | 3.563            | 25.374   | 2675.143  | 105.428           | 0.8183  |
| ChatGPT4o                  | 1.000       | 3.500        | 3.251            | 13.840   | 1163.571  | 84.071            | 0.8180  |
| OpenAi_o3_mini_0131        | 1.000       | 3.369        | 2.919            | 31.094   | 4398.286  | 141.452           | 0.8008  |
| Grok2_1212                 | 1.000       | 3.360        | 3.324            | 26.784   | 1650.714  | 61.630            | 0.7999  |
| Claude_Sonnet_35v2         | 1.000       | 3.693        | 2.960            | 27.767   | 1636.429  | 58.934            | 0.7953  |
| OpenAi_o1_1217             | 1.000       | 3.373        | 2.991            | 26.431   | 2810.143  | 106.321           | 0.7906  |
| GPT4o_0806                 | 1.000       | 3.417        | 3.156            | 17.411   | 1042.714  | 59.889            | 0.7878  |
| Qwen25Coder32B             | 1.000       | 3.396        | 2.847            | 17.689   | 1654.143  | 93.511            | 0.7720  |
| GPT4o_1120                 | 1.000       | 3.403        | 2.617            | 9.023    | 1143.429  | 126.723           | 0.7666  |
| Gemini_1206                | 1.000       | 3.289        | 2.957            | 61.595   | 2612.571  | 42.415            | 0.7462  |
| Llama3_70B                 | 1.000       | 3.330        | 2.830            | 62.691   | 808.167   | 12.891            | 0.7226  |
| Llama31_405B               | 1.000       | 3.127        | 2.816            | 30.388   | 1165.429  | 38.352            | 0.7138  |
| GrokBeta                   | 1.000       | 3.516        | 2.324            | 20.738   | 1045.857  | 50.432            | 0.7097  |
| Gemini_15_Pro_002          | 1.000       | 2.864        | 2.923            | 27.487   | 1189.571  | 43.277            | 0.7008  |
| GPT4o_mini_0718            | 1.000       | 2.866        | 2.566            | 14.007   | 881.143   | 62.906            | 0.6752  |
| AmazonNovaPro              | 1.000       | 2.717        | 2.647            | 19.778   | 985.000   | 49.803            | 0.6618  |
| GPT35_Turbo_0125           | 1.000       | 2.513        | 1.281            | 7.132    | 431.286   | 60.474            | 0.5103  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                      | Avg Attempt | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|-------------|--------------|------------------|----------|-----------|-------------------|---------|
| OpenAi_o1_mini_0912        | 1.000       | 3.734        | 3.890            | 22.890   | 3656.444  | 159.739           | 0.9528  |
| GPT4o_1120                 | 1.000       | 3.774        | 3.809            | 12.471   | 1535.667  | 123.142           | 0.9280  |
| OpenAi_o3_mini_0131        | 1.000       | 3.470        | 3.759            | 14.252   | 2130.333  | 149.472           | 0.9074  |
| Gemini_20_Pro_0205         | 1.000       | 3.676        | 3.753            | 43.076   | 4044.444  | 93.892            | 0.8960  |
| ChatGPT4o                  | 1.000       | 3.762        | 3.624            | 20.633   | 1700.889  | 82.435            | 0.8853  |
| OpenAi_o1_0912             | 1.000       | 3.633        | 3.727            | 69.490   | 5189.889  | 74.686            | 0.8782  |
| DeepSeekR1                 | 1.000       | 3.889        | 3.529            | 35.172   | 1938.111  | 55.103            | 0.8729  |
| Gemini_20_Flash_Think_0121 | 1.000       | 3.548        | 3.150            | 25.138   | 4444.222  | 176.790           | 0.8698  |
| AmazonNovaPro              | 1.000       | 3.517        | 3.741            | 17.757   | 1094.222  | 61.622            | 0.8606  |
| Qwen25Coder32B             | 1.000       | 3.464        | 3.589            | 11.575   | 1060.889  | 91.657            | 0.8572  |
| OpenAi_o1_1217             | 1.000       | 3.561        | 3.504            | 27.209   | 2332.778  | 85.736            | 0.8551  |
| Claude_Haiku_35            | 1.000       | 3.669        | 3.501            | 14.084   | 860.778   | 61.117            | 0.8516  |
| Claude_Sonnet_35v2         | 1.000       | 3.674        | 3.464            | 17.195   | 962.556   | 55.977            | 0.8456  |
| Grok2_1212                 | 1.000       | 3.614        | 3.458            | 23.575   | 1498.333  | 63.556            | 0.8432  |
| Gemini_15_Pro_002          | 1.000       | 3.429        | 3.463            | 35.696   | 1072.000  | 30.031            | 0.8062  |
| GPT4o_mini_0718            | 1.000       | 3.419        | 3.310            | 16.548   | 922.111   | 55.724            | 0.8044  |
| GrokBeta                   | 1.000       | 3.358        | 3.269            | 20.916   | 1087.444  | 51.990            | 0.7921  |
| GPT35_Turbo_0125           | 1.000       | 3.409        | 2.959            | 9.818    | 589.778   | 60.071            | 0.7708  |
| GPT4o_0806                 | 1.000       | 3.271        | 3.149            | 36.855   | 901.556   | 24.462            | 0.7558  |
| Gemini_1206                | 1.000       | 3.428        | 2.869            | 110.399  | 2249.556  | 20.377            | 0.7412  |
| Llama3_70B                 | 1.000       | 3.342        | 2.736            | 69.926   | 880.000   | 12.585            | 0.7149  |
| Llama31_405B               | 1.000       | 2.690        | 2.658            | 17.266   | 933.222   | 54.048            | 0.6653  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                      | Avg Accuracy | Avg Completeness | Score ↓ |
|----------------------------|--------------|------------------|---------|
| OpenAi_o3_mini_0131        | 4.0          | 4.0              | 1.00    |
| Claude_Sonnet_35v2         | 4.0          | 4.0              | 1.00    |
| Gemini_1206                | 4.0          | 4.0              | 1.00    |
| Gemini_20_Pro_0205         | 3.75         | 4.0              | 0.9688  |
| OpenAi_o1_1217             | 4.0          | 3.75             | 0.9688  |
| ChatGPT4o                  | 3.5          | 4.0              | 0.9375  |
| OpenAi_o1_mini_0912        | 3.5          | 3.5              | 0.875   |
| OpenAi_o1_0912             | 3.5          | 3.5              | 0.875   |
| GPT4o_1120                 | 3.0          | 4.0              | 0.875   |
| GPT4o_0806                 | 4.0          | 3.0              | 0.875   |
| Claude_Haiku_35            | 3.5          | 3.5              | 0.875   |
| Gemini_15_Pro_002          | 3.0          | 3.2              | 0.875   |
| Gemini_20_Flash_Think_0121 | 3.75         | 2.75             | 0.8125  |
| Grok2_1212                 | 3.5          | 3.0              | 0.8125  |
| GrokBeta                   | 2.5          | 4.0              | 0.8125  |
| DeepSeekR1                 | 3.5          | 2.75             | 0.78125 |
| Qwen25Coder32B             | 3.0          | 2.75             | 0.7186  |
| Llama31_405B               | 2.5          | 3.0              | 0.6875  |
| AmazonNovaPro              | 2.25         | 2.25             | 0.5625  |
| GPT4o_mini_0718            | 2.5          | 2.0              | 0.5625  |
| GPT35_Turbo_0125           | 2.0          | 1.5              | 0.4375  |
| Llama3_70B                 | 1.0          | 1.0              | 0.25    |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution and Leadership:
    - OpenAI maintains strong market position with o3-mini and o1-mini models jointly leading at 91.3% total score
    - Google's Gemini models show impressive capabilities, with Gemini 2.0 Pro achieving 89.8% overall and Gemini 2.0 Flash Thinking excelling in specific tasks
    - Multiple models achieving perfect LCIF scores demonstrates advancement in handling complex instructions
    - The competitive performance of DeepSeek R1 (84.0%) shows promising development in open-source alternatives

2. Performance Patterns:
    - Specialized strengths emerge across different categories:
        * Code Translation: Gemini 2.0 Flash Thinking dominates with 97.5%
        * Code Generation: OpenAI o1-mini leads with 91.2%
        * Code Documentation: OpenAI o1-mini achieves 95.3%
        * LCIF: Three models (OpenAI o3-mini, Claude 3.5 Sonnet v2, Gemini Experimental) achieve perfect scores
    - Top-tier models consistently achieve >85% scores across categories
    - Gemini 2.0 Flash Thinking 0121 shows incredible speed, achieving 200 tokens per second
    - Processing efficiency varies significantly, with newer models generally showing improved performance

3. Market Implications:
    - Competition between major providers (OpenAI, Google, Anthropic) drives rapid innovation
    - The emergence of strong open-source alternatives like DeepSeek R1 provides more options for organizations
    - Performance gaps between commercial and open-source models are narrowing, though differences in computational efficiency remain
    - The market offers diverse options optimized for different use cases and deployment scenarios

4. Areas for Improvement:
    - Computational efficiency remains a challenge, particularly for open-source models
    - Response times vary significantly across models, especially in complex tasks
    - Consistency across different types of tasks varies, with models showing strengths in specific areas
    - Cost-performance balance continues to be a key consideration for model selection

These findings indicate a maturing market with increasing sophistication in model capabilities. The strong performance of newer models (o3-mini, Gemini 2.0 series) alongside the emergence of capable open-source alternatives suggests a trend
toward both higher performance and greater accessibility. Organizations now have more options to choose from, whether prioritizing overall performance, specific capabilities, deployment flexibility, or cost-effectiveness.

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