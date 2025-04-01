# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

Key findings:

- Gemini 2.5 Pro Experimental takes the lead with an impressive 93.5% total score
- Claude 3.7 Sonnet follows closely with 91.6% total score
- OpenAI's o3-mini model demonstrates exceptional performance at 91.3%, confirming its suitability for coding tasks
- DeepSeek V3, an open-source model that can be self-hosted, shows significant improvements over R1 at 84.1%
- Amazon Nova Pro, while smaller in size, achieves 62.6% and shows potential as we await the more powerful Amazon Nova Premier model

Best results by category:

- Code Translation: Gemini 2.5 Pro leads with 91.2%, followed by Gemini 2.0 Pro Experimental at 90.9%
- Code Generation: Gemini 2.5 Pro ranks first (92.8%), followed by Gemini 2.0 Flash Thinking Experimental (92.7%)
- Code Documentation: Gemini 2.5 Pro dominates with 90.1%, followed by OpenAI o3-mini (87.2%)
- LCIF: Four models achieve 100%: Gemini 2.5 Pro, Claude 3.7 Sonnet, Claude 3.7 Sonnet (Thinking), and OpenAI o3-mini

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                                         | Execution Date | Benchmark | Code Translation | Generation | Document | Context | Total Score |
|-----------------------------------------------|----------------|-----------|------------------|------------|----------|---------|-------------|
| Gemini 2.5 Pro Experimental (0325)            | 2025-03-26     | v2        | 91.22%           | 92.80%     | 90.06%   | 100.00% | 93.52%      |
| Claude 3.7 Sonnet                             | 2025-03-20     | v2        | 88.83%           | 90.79%     | 86.88%   | 100.00% | 91.63%      |
| OpenAI o3-mini (2025-01-31)                   | 2025-03-20     | v2        | 88.22%           | 89.62%     | 87.24%   | 100.00% | 91.27%      |
| Gemini 2.0 Pro Experimental (0205)            | 2025-03-20     | v2        | 90.92%           | 90.03%     | 85.88%   | 96.88%  | 90.93%      |
| Claude 3.7 Sonnet (Thinking)                  | 2025-03-20     | v2        | 87.42%           | 91.61%     | 82.37%   | 100.00% | 90.35%      |
| Gemini 2.0 Flash Thinking Experimental (0121) | 2025-03-20     | v2        | 83.00%           | 92.65%     | 77.41%   | 87.50%  | 85.14%      |
| DeepSeek V3 (0324)                            | 2025-03-27     | v2        | 82.52%           | 82.71%     | 80.65%   | 90.63%  | 84.13%      |
| GPT-4.5 preview                               | 2025-03-20     | v2        | 66.83%           | 78.38%     | 74.91%   | 90.63%  | 77.69%      |
| DeepSeek R1                                   | 2025-03-20     | v2        | 75.00%           | 78.69%     | 77.67%   | 78.13%  | 77.37%      |
| Amazon Nova Pro                               | 2025-03-28     | v2        | 55.07%           | 71.19%     | 67.85%   | 56.25%  | 62.59%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Pro_0325         | 3.771        | 3.991            | 80.52    | 7992.71   | 99.26             | 0.9122  |
| Gemini_20_Pro_0205         | 3.794        | 4.000            | 75.54    | 5072.29   | 67.15             | 0.9092  |
| Claude_Sonnet_37           | 3.781        | 3.786            | 73.37    | 6240.14   | 85.05             | 0.8883  |
| OpenAi_o3_mini_0131        | 3.674        | 3.687            | 47.52    | 5598.00   | 117.80            | 0.8822  |
| Claude_Sonnet_37_Thinking  | 3.657        | 3.857            | 145.33   | 12453.29  | 85.69             | 0.8742  |
| Gemini_20_Flash_Think_0121 | 2.963        | 3.531            | 25.15    | 5312.86   | 211.27            | 0.8300  |
| DeepSeekV3_0324            | 3.491        | 3.680            | 123.30   | 4374.71   | 35.48             | 0.8252  |
| DeepSeekR1                 | 3.356        | 2.989            | 65.33    | 4757.00   | 72.82             | 0.7500  |
| GPT45_0227                 | 3.364        | 2.496            | 183.17   | 1757.86   | 9.60              | 0.6683  |
| AmazonNovaPro              | 2.551        | 1.723            | 24.82    | 2084.57   | 83.99             | 0.5507  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Pro_0325         | 3.989        | 3.923            | 82.71    | 8241.88   | 99.65             | 0.9280  |
| Gemini_20_Flash_Think_0121 | 3.879        | 3.486            | 20.13    | 3812.63   | 189.41            | 0.9265  |
| Claude_Sonnet_37_Thinking  | 3.944        | 3.939            | 125.64   | 10304.25  | 82.01             | 0.9161  |
| Claude_Sonnet_37           | 3.886        | 3.873            | 66.44    | 5169.75   | 77.81             | 0.9079  |
| Gemini_20_Pro_0205         | 3.925        | 3.813            | 74.63    | 4777.63   | 64.02             | 0.9003  |
| OpenAi_o3_mini_0131        | 3.938        | 3.438            | 28.29    | 3471.13   | 122.70            | 0.8962  |
| DeepSeekV3_0324            | 3.883        | 3.249            | 63.38    | 2316.63   | 36.55             | 0.8271  |
| DeepSeekR1                 | 3.634        | 3.094            | 73.97    | 4766.50   | 64.44             | 0.7869  |
| GPT45_0227                 | 4.000        | 2.903            | 184.73   | 1449.38   | 7.85              | 0.7838  |
| AmazonNovaPro              | 3.273        | 2.431            | 19.28    | 1477.38   | 76.63             | 0.7119  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Pro_0325         | 3.904        | 3.787            | 65.61    | 5404.22   | 82.37             | 0.9006  |
| OpenAi_o3_mini_0131        | 3.824        | 3.378            | 25.42    | 2827.56   | 111.21            | 0.8724  |
| Claude_Sonnet_37           | 3.788        | 3.629            | 47.84    | 3062.89   | 64.03             | 0.8688  |
| Gemini_20_Pro_0205         | 3.769        | 3.617            | 80.13    | 5123.89   | 63.94             | 0.8588  |
| Claude_Sonnet_37_Thinking  | 3.724        | 3.320            | 56.33    | 3432.78   | 60.94             | 0.8237  |
| DeepSeekV3_0324            | 3.483        | 3.424            | 38.76    | 1295.00   | 33.41             | 0.8065  |
| DeepSeekR1                 | 3.420        | 3.036            | 25.56    | 1817.11   | 71.09             | 0.7767  |
| Gemini_20_Flash_Think_0121 | 3.222        | 3.011            | 33.57    | 5841.11   | 174.02            | 0.7741  |
| GPT45_0227                 | 3.461        | 3.139            | 183.29   | 1554.89   | 8.48              | 0.7491  |
| AmazonNovaPro              | 3.101        | 2.273            | 15.37    | 1278.56   | 83.21             | 0.6785  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                      | Avg Accuracy | Avg Completeness | Score ↓ |
|----------------------------|--------------|------------------|---------|
| Claude_Sonnet_37           | 4.0          | 4.0              | 1.00    |
| Claude_Sonnet_37_Thinking  | 4.0          | 4.0              | 1.00    |
| OpenAi_o3_mini_0131        | 4.0          | 4.0              | 1.00    |
| Gemini_25_Pro_0325         | 4.0          | 4.0              | 1.00    |
| Gemini_20_Pro_0205         | 3.75         | 4.0              | 0.96875 |
| GPT45_0227                 | 3.5          | 3.75             | 0.90625 |
| DeepSeekV3_0324            | 3.5          | 3.75             | 0.90625 |
| Gemini_15_Pro_002          | 3.5          | 3.5              | 0.875   |
| Gemini_20_Flash_Think_0121 | 3.75         | 3.25             | 0.875   |
| DeepSeekR1                 | 3.5          | 2.75             | 0.78125 |
| AmazonNovaPro              | 2.25         | 2.25             | 0.5625  |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution and Leadership:
    - Google has taken the lead with Gemini 2.5 Pro Experimental achieving the top position at 93.5% total score
    - Anthropic maintains strong market position with Claude 3.7 Sonnet at 91.6% total score
    - OpenAI shows competitive performance with o3-mini at 91.3% total score
    - Four models achieving perfect LCIF scores demonstrates advancement in handling complex instructions
    - DeepSeek's open-source models (V3 at 84.1% and R1 at 77.4%) represent significant achievements in the open-source space, allowing for self-hosting within organizations

2. Performance Patterns:
    - Specialized strengths emerge across different categories:
        * Code Translation: Gemini 2.5 Pro leads with 91.2%, followed by Gemini 2.0 Pro Experimental at 90.9%
        * Code Generation: Gemini 2.5 Pro dominates with 92.8%, followed by Gemini 2.0 Flash Thinking Experimental at 92.7%
        * Code Documentation: Gemini 2.5 Pro excels with 90.1%, followed by OpenAI o3-mini at 87.2%
        * LCIF: Four models (Gemini 2.5 Pro, Claude 3.7 Sonnet, Claude 3.7 Sonnet (Thinking), OpenAI o3-mini) achieve perfect scores
    - Top-tier models consistently achieve >90% scores across most categories
    - Gemini 2.0 Flash Thinking Experimental continues to show incredible speed, achieving 188 tokens per second
    - Processing efficiency varies significantly, with newer models generally showing improved performance

3. Market Implications:
    - Intense competition between major providers (Google, Anthropic, OpenAI) continues to drive rapid innovation
    - Performance of OpenAI's o3-mini demonstrates that smaller, more efficient models can compete with larger counterparts
    - Amazon Nova Pro, while scoring 62.6%, shows promise for enterprise applications as we await the more powerful Amazon Nova Premier model
    - Due to high price of GPT-4.5 preview, it appears OpenAI has decreased the amount of tokens generated in output
    - DeepSeek's open-source models provide viable alternatives for organizations seeking to host their own LLMs

4. Areas for Improvement:
    - Computational efficiency remains a challenge for some models, particularly GPT-4.5 preview with its low speed of 8.59 tokens per second
    - Response quality and consistency across different types of tasks varies significantly
    - Cost-performance balance continues to be a key consideration for model selection, with experimental models currently offering the best value

These findings indicate a maturing market with increasing sophistication in model capabilities. The strong performance of newer models (Gemini 2.5 Pro, Claude 3.7 Sonnet, o3-mini) suggests a trend
toward both higher performance and greater efficiency. Organizations now have more options to choose from, whether prioritizing overall performance, specific capabilities, deployment flexibility, or
cost-effectiveness, including self-hosting options with open-source models like DeepSeek.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>