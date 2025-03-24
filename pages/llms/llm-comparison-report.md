# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

Key findings:

- Claude 3.7 Sonnet leads the rankings with 91.9% total score
- OpenAI's o3-mini model showed better results than o1, in a way confirming that this model is more suitable for coding tasks
- Gemini 2.0 Pro Experimental has improved in ratings and entered the top 3 at the moment
- Gemini 2.0 Flash Thinking Experimental good in speed and code generation

Best results by category:

- Code Translation: Gemini 2.0 Pro Experimental leads with 90.9%, followed by Claude 3.7 Sonnet at 88.9%
- Code Generation: Gemini 2.0 Flash Thinking Experimental ranks first (92.9%), followed by Claude 3.7 Sonnet (Thinking) (91.6%)
- Code Documentation: OpenAI o3-mini leads (89.2%), followed by Claude 3.7 Sonnet (87.9%)
- LCIF: Three models achieve 100%: Claude 3.7 Sonnet, Claude 3.7 Sonnet (Thinking), and OpenAI o3-mini

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                                         | Execution Date | Benchmark | Code Translation | Generation | Document | Context | Total Score |
|-----------------------------------------------|----------------|-----------|------------------|------------|----------|---------|-------------|
| Claude 3.7 Sonnet                             | 2025-03-20     | v2        | 88.86%           | 90.85%     | 87.93%   | 100.00% | 91.91%      |
| OpenAI o3-mini (2025-01-31)                   | 2025-03-20     | v2        | 88.25%           | 89.77%     | 89.22%   | 100.00% | 91.81%      |
| Gemini 2.0 Pro Experimental (0205)            | 2025-03-20     | v2        | 90.94%           | 90.09%     | 86.51%   | 96.88%  | 91.10%      |
| Claude 3.7 Sonnet (Thinking)                  | 2025-03-20     | v2        | 87.43%           | 91.64%     | 83.26%   | 100.00% | 90.58%      |
| Gemini 2.0 Flash Thinking Experimental (0121) | 2025-03-20     | v2        | 83.06%           | 92.86%     | 78.91%   | 87.50%  | 85.58%      |
| DeepSeek R1                                   | 2025-03-20     | v2        | 75.02%           | 78.75%     | 79.64%   | 78.13%  | 77.88%      |
| GPT-4.5 preview                               | 2025-03-20     | v2        | 66.84%           | 78.41%     | 75.19%   | 90.63%  | 77.76%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._


> Additional info:  
> <sup>1</sup> - For models with "LLM-based" Evaluation Approach, evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the GPT-4o model.
> Please refer the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.  
> <sup>2</sup> - Evaluation was done more than 3 month ago, results are outdated

## Results by categories

### Code Translation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score  |
|----------------------------|--------------|------------------|----------|-----------|-------------------|--------|
| Gemini_20_Pro_0205         | 3.794        | 4.000            | 75.54    | 5072.29   | 67.15             | 0.9094 |
| Claude_Sonnet_37           | 3.781        | 3.786            | 73.37    | 6240.14   | 85.05             | 0.8886 |
| OpenAi_o3_mini_0131        | 3.674        | 3.687            | 47.52    | 5598.00   | 117.80            | 0.8825 |
| Claude_Sonnet_37_Thinking  | 3.657        | 3.857            | 145.33   | 12453.29  | 85.69             | 0.8743 |
| Gemini_20_Flash_Think_0121 | 2.963        | 3.531            | 25.15    | 5312.86   | 211.27            | 0.8306 |
| DeepSeekR1                 | 3.356        | 2.989            | 65.33    | 4757.00   | 72.82             | 0.7502 |
| GPT45_0227                 | 3.364        | 2.496            | 183.17   | 1757.86   | 9.60              | 0.6684 |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score  |
|----------------------------|--------------|------------------|----------|-----------|-------------------|--------|
| Gemini_20_Flash_Think_0121 | 3.879        | 3.486            | 20.13    | 3812.63   | 189.41            | 0.9286 |
| Claude_Sonnet_37_Thinking  | 3.944        | 3.939            | 125.64   | 10304.25  | 82.01             | 0.9164 |
| Claude_Sonnet_37           | 3.886        | 3.873            | 66.44    | 5169.75   | 77.81             | 0.9085 |
| Gemini_20_Pro_0205         | 3.925        | 3.813            | 74.63    | 4777.63   | 64.02             | 0.9009 |
| OpenAi_o3_mini_0131        | 3.938        | 3.438            | 28.29    | 3471.13   | 122.70            | 0.8977 |
| DeepSeekR1                 | 3.634        | 3.094            | 73.97    | 4766.50   | 64.44             | 0.7875 |
| GPT45_0227                 | 4.000        | 2.903            | 184.73   | 1449.38   | 7.85              | 0.7841 |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score  |
|----------------------------|--------------|------------------|----------|-----------|-------------------|--------|
| OpenAi_o3_mini_0131        | 3.824        | 3.378            | 25.42    | 2827.56   | 111.21            | 0.8922 |
| Claude_Sonnet_37           | 3.788        | 3.629            | 47.84    | 3062.89   | 64.03             | 0.8793 |
| Gemini_20_Pro_0205         | 3.769        | 3.617            | 80.13    | 5123.89   | 63.94             | 0.8651 |
| Claude_Sonnet_37_Thinking  | 3.724        | 3.320            | 56.33    | 3432.78   | 60.94             | 0.8326 |
| DeepSeekR1                 | 3.420        | 3.036            | 25.56    | 1817.11   | 71.09             | 0.7964 |
| Gemini_20_Flash_Think_0121 | 3.222        | 3.011            | 33.57    | 5841.11   | 174.02            | 0.7891 |
| GPT45_0227                 | 3.461        | 3.139            | 183.29   | 1554.89   | 8.48              | 0.7519 |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                      | Avg Accuracy | Avg Completeness | Score ↓ |
|----------------------------|--------------|------------------|---------|
| Claude_Sonnet_37           | 4.0          | 4.0              | 1.00    |
| Claude_Sonnet_37_Thinking  | 4.0          | 4.0              | 1.00    |
| OpenAi_o3_mini_0131        | 4.0          | 4.0              | 1.00    |
| Gemini_20_Pro_0205         | 3.75         | 4.0              | 0.9688  |
| GPT45_0227                 | 3.5          | 3.75             | 0.9063  |
| Gemini_20_Flash_Think_0121 | 3.75         | 2.75             | 0.8125  |
| DeepSeekR1                 | 3.5          | 2.75             | 0.78125 |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution and Leadership:
    - Anthropic maintains market leadership with Claude 3.7 Sonnet achieving the top position at 91.9% total score
    - OpenAI shows strong market position with o3-mini at 91.8% total score
    - Google's Gemini models show impressive capabilities, with Gemini 2.0 Pro achieving 91.1% overall
    - Three models achieving perfect LCIF scores demonstrates advancement in handling complex instructions
    - The performance gap between DeepSeek R1 (77.9%) and GPT-4.5 preview (77.8%) is surprisingly small, considering their price difference

2. Performance Patterns:
    - Specialized strengths emerge across different categories:
        * Code Translation: Gemini 2.0 Pro Experimental dominates with 90.9%
        * Code Generation: Gemini 2.0 Flash Thinking Experimental leads with 92.9%
        * Code Documentation: OpenAI o3-mini achieves 89.2%
        * LCIF: Three models (Claude 3.7 Sonnet, Claude 3.7 Sonnet (Thinking), OpenAI o3-mini) achieve perfect scores
    - Top-tier models consistently achieve >90% scores across most categories
    - Gemini 2.0 Flash Thinking Experimental shows incredible speed, achieving 188 tokens per second
    - Processing efficiency varies significantly, with newer models generally showing improved performance

3. Market Implications:
    - Intense competition between major providers (Anthropic, OpenAI, Google) continues to drive rapid innovation
    - Performance of OpenAI's o3-mini demonstrates that smaller, more efficient models can compete with larger counterparts
    - Looks like due to high price of GPT-4.5 preview it was decided to decrease amount of tokens generated in output
    - Performance patterns suggest that specialized models may outperform generalist models in specific domains

4. Areas for Improvement:
    - Computational efficiency remains a challenge for some models, particularly GPT-4.5 preview with its low speed of 8.59 tokens per second
    - Response quality and consistency across different types of tasks varies significantly
    - Cost-performance balance continues to be a key consideration for model selection

These findings indicate a maturing market with increasing sophistication in model capabilities. The strong performance of newer models (Claude 3.7 Sonnet, o3-mini, Gemini 2.0 series) suggests a trend
toward both higher performance and greater efficiency. Organizations now have more options to choose from, whether prioritizing overall performance, specific capabilities, deployment flexibility, or
cost-effectiveness.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>