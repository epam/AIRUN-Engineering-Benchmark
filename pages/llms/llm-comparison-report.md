# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

Key findings:

- Gemini 2.5 Pro Experimental takes the lead with an impressive 93.3% total score
- Grok 3 mini beta ranks second with 92.3% total score
- Claude 3.7 Sonnet follows closely with 91.4% total score
- OpenAI's o3-mini model demonstrates exceptional performance at 90.8%, confirming its suitability for coding tasks
- Gemini 2.0 Pro Experimental and Claude 3.7 Sonnet (Thinking) show strong results at 90.7% and 90.2% respectively
- Grok 3 beta achieves an impressive 89.4% total score
- ChatGPT-4o shows strong overall performance at 87.8%, making it a competitive option
- OpenAI o1 demonstrates solid capabilities at 84.5%, performing similarly to Gemini 2.0 Flash Thinking
- DeepSeek V3, an open-source model that can be self-hosted, shows significant improvements over R1 at 83.9%
- Llama 4 Maverick demonstrates competitive performance at 74.5%, showing Meta's progress in the LLM space
- Amazon Nova Pro, while smaller, achieves 61.8% and shows potential as we await the more powerful Amazon Nova Premier model

Performance metrics highlights:

- Fastest token generation: Gemini 2.0 Flash Thinking Experimental (188.16 tokens/sec), followed by Grok 3 mini beta (152.47 tokens/sec)
- Shortest execution time: ChatGPT-4o (6.53 minutes), followed by Llama 4 Maverick (6.48 minutes)
- Most tokens generated: Grok 3 mini beta (220,054 tokens), followed by Claude 3.7 Sonnet Thinking (200,502 tokens)
- Most cost-effective high performers: Grok 3 mini beta (92.3% score at $0.30/$0.50 per MTok) and OpenAI o3-mini (90.8% score at $1.10/$4.40 per MTok)

Best results by category:

- Code Translation: Gemini 2.5 Pro leads with 90.9%, followed by Gemini 2.0 Pro Experimental at 90.5% and Grok 3 mini beta at 89.4%
- Code Generation: Grok 3 mini beta ranks first (93.0%), followed by Gemini 2.5 Pro (92.5%) and Claude 3.7 Sonnet (Thinking) (91.4%)
- Code Documentation: Grok 3 mini beta leads with 90.2%, followed by Gemini 2.5 Pro (89.9%) and OpenAI o3-mini (86.8%)
- LCIF: Five models achieve perfect 100% scores: Gemini 2.5 Pro, Claude 3.7 Sonnet, Grok 3 beta, Claude 3.7 Sonnet (Thinking), and OpenAI o3-mini

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                                         | Execution Date | Benchmark | Code Translation | Code Generation | Code Document | LCIF    | Total Score |
|-----------------------------------------------|----------------|-----------|------------------|-----------------|---------------|---------|-------------|
| Gemini 2.5 Pro Experimental (0325)            | 2025-03-26     | v2        | 90.86%           | 92.48%          | 89.89%        | 100.00% | 93.31%      |
| Grok 3 mini beta                              | 2025-04-13     | v2        | 89.38%           | 92.95%          | 90.16%        | 96.88%  | 92.34%      |
| Claude 3.7 Sonnet                             | 2025-03-20     | v2        | 88.44%           | 90.40%          | 86.65%        | 100.00% | 91.37%      |
| OpenAI o3-mini (2025-01-31)                   | 2025-03-20     | v2        | 87.60%           | 88.69%          | 86.79%        | 100.00% | 90.77%      |
| Gemini 2.0 Pro Experimental (0205)            | 2025-03-20     | v2        | 90.53%           | 89.68%          | 85.74%        | 96.88%  | 90.71%      |
| Claude 3.7 Sonnet (Thinking)                  | 2025-03-20     | v2        | 87.22%           | 91.40%          | 82.16%        | 100.00% | 90.20%      |
| Grok 3 beta                                   | 2025-04-11     | v2        | 88.75%           | 87.49%          | 81.22%        | 100.00% | 89.37%      |
| ChatGPT-4o                                    | 2025-03-20     | v2        | 86.36%           | 85.43%          | 85.85%        | 93.75%  | 87.85%      |
| OpenAI o1 (1217)                              | 2025-03-20     | v2        | 83.73%           | 81.79%          | 75.77%        | 96.88%  | 84.54%      |
| Gemini 2.0 Flash Thinking Experimental (0121) | 2025-03-20     | v2        | 81.84%           | 91.34%          | 77.07%        | 87.50%  | 84.44%      |
| DeepSeek V3 (0324)                            | 2025-03-27     | v2        | 82.29%           | 82.30%          | 80.36%        | 90.63%  | 83.89%      |
| GPT-4.5 preview                               | 2025-03-20     | v2        | 66.67%           | 78.24%          | 74.85%        | 90.63%  | 77.60%      |
| DeepSeek R1                                   | 2025-03-20     | v2        | 74.55%           | 78.33%          | 77.23%        | 78.13%  | 77.06%      |
| Llama 4 Maverick                              | 2025-04-07     | v2        | 68.94%           | 76.15%          | 68.41%        | 84.38%  | 74.47%      |
| Amazon Nova Pro                               | 2025-03-28     | v2        | 53.90%           | 69.83%          | 67.11%        | 56.25%  | 61.77%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Pro_0325         | 3.771        | 3.991            | 80.52    | 7992.71   | 99.26             | 0.9086  |
| Gemini_20_Pro_0205         | 3.794        | 4.000            | 75.54    | 5072.29   | 67.15             | 0.9053  |
| Grok3mini_beta             | 3.767        | 3.769            | 94.12    | 14279.71  | 151.72            | 0.8938  |
| Grok3_beta                 | 3.829        | 3.666            | 41.70    | 3807.71   | 91.30             | 0.8875  |
| Claude_Sonnet_37           | 3.781        | 3.786            | 73.37    | 6240.14   | 85.05             | 0.8844  |
| OpenAi_o3_mini_0131        | 3.674        | 3.687            | 47.52    | 5598.00   | 117.80            | 0.8760  |
| Claude_Sonnet_37_Thinking  | 3.657        | 3.857            | 145.33   | 12453.29  | 85.69             | 0.8722  |
| ChatGPT4o                  | 3.449        | 3.480            | 19.00    | 2738.00   | 144.11            | 0.8636  |
| OpenAi_o1_1217             | 3.670        | 3.559            | 89.62    | 5107.86   | 56.99             | 0.8373  |
| DeepSeekV3_0324            | 3.491        | 3.680            | 123.30   | 4374.71   | 35.48             | 0.8229  |
| Gemini_20_Flash_Think_0121 | 2.963        | 3.531            | 25.15    | 5312.86   | 211.27            | 0.8184  |
| DeepSeekR1                 | 3.356        | 2.989            | 65.33    | 4757.00   | 72.82             | 0.7455  |
| Llama_4_Maverick           | 3.116        | 2.420            | 22.70    | 2379.86   | 104.82            | 0.6894  |
| GPT45_0227                 | 3.364        | 2.496            | 183.17   | 1757.86   | 9.60              | 0.6667  |
| AmazonNovaPro              | 2.551        | 1.723            | 24.82    | 2084.57   | 83.99             | 0.5390  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Grok3mini_beta             | 4.000        | 3.823            | 62.36    | 9035.00   | 144.88            | 0.9295  |
| Gemini_25_Pro_0325         | 3.989        | 3.923            | 82.71    | 8241.88   | 99.65             | 0.9248  |
| Claude_Sonnet_37_Thinking  | 3.944        | 3.939            | 125.64   | 10304.25  | 82.01             | 0.9140  |
| Gemini_20_Flash_Think_0121 | 3.879        | 3.486            | 20.13    | 3812.63   | 189.41            | 0.9134  |
| Claude_Sonnet_37           | 3.886        | 3.873            | 66.44    | 5169.75   | 77.81             | 0.9040  |
| Gemini_20_Pro_0205         | 3.925        | 3.813            | 74.63    | 4777.63   | 64.02             | 0.8968  |
| OpenAi_o3_mini_0131        | 3.938        | 3.438            | 28.29    | 3471.13   | 122.70            | 0.8869  |
| Grok3_beta                 | 3.861        | 3.520            | 30.55    | 2493.00   | 81.61             | 0.8749  |
| ChatGPT4o                  | 3.813        | 3.076            | 15.01    | 1850.50   | 123.33            | 0.8543  |
| DeepSeekV3_0324            | 3.883        | 3.249            | 63.38    | 2316.63   | 36.55             | 0.8230  |
| OpenAi_o1_1217             | 4.000        | 3.043            | 61.21    | 3280.38   | 53.59             | 0.8179  |
| DeepSeekR1                 | 3.634        | 3.094            | 73.97    | 4766.50   | 64.44             | 0.7833  |
| GPT45_0227                 | 4.000        | 2.903            | 184.73   | 1449.38   | 7.85              | 0.7824  |
| Llama_4_Maverick           | 3.511        | 2.568            | 14.03    | 1470.75   | 104.86            | 0.7615  |
| AmazonNovaPro              | 3.273        | 2.431            | 19.28    | 1477.38   | 76.63             | 0.6983  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Grok3mini_beta             | 3.891        | 3.512            | 31.73    | 5312.89   | 167.45            | 0.9016  |
| Gemini_25_Pro_0325         | 3.904        | 3.787            | 65.61    | 5404.22   | 82.37             | 0.8989  |
| OpenAi_o3_mini_0131        | 3.824        | 3.378            | 25.42    | 2827.56   | 111.21            | 0.8679  |
| Claude_Sonnet_37           | 3.788        | 3.629            | 47.84    | 3062.89   | 64.03             | 0.8665  |
| ChatGPT4o                  | 3.653        | 3.332            | 15.40    | 1615.11   | 104.86            | 0.8585  |
| Gemini_20_Pro_0205         | 3.769        | 3.617            | 80.13    | 5123.89   | 63.94             | 0.8574  |
| Claude_Sonnet_37_Thinking  | 3.724        | 3.320            | 56.33    | 3432.78   | 60.94             | 0.8216  |
| Grok3_beta                 | 3.626        | 3.236            | 32.77    | 2325.89   | 70.98             | 0.8122  |
| DeepSeekV3_0324            | 3.483        | 3.424            | 38.76    | 1295.00   | 33.41             | 0.8036  |
| DeepSeekR1                 | 3.420        | 3.036            | 25.56    | 1817.11   | 71.09             | 0.7723  |
| Gemini_20_Flash_Think_0121 | 3.222        | 3.011            | 33.57    | 5841.11   | 174.02            | 0.7707  |
| OpenAi_o1_1217             | 3.473        | 3.027            | 56.48    | 2921.22   | 51.73             | 0.7577  |
| GPT45_0227                 | 3.461        | 3.139            | 183.29   | 1554.89   | 8.48              | 0.7485  |
| Llama_4_Maverick           | 2.897        | 2.486            | 13.09    | 1302.11   | 99.47             | 0.6841  |
| AmazonNovaPro              | 3.101        | 2.273            | 15.37    | 1278.56   | 83.21             | 0.6711  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                      | Avg Accuracy | Avg Completeness | Score ↓ |
|----------------------------|--------------|------------------|---------|
| Gemini_25_Pro_0325         | 4.0          | 4.0              | 1.00    |
| Claude_Sonnet_37           | 4.0          | 4.0              | 1.00    |
| Grok3_beta                 | 4.0          | 4.0              | 1.00    |
| Claude_Sonnet_37_Thinking  | 4.0          | 4.0              | 1.00    |
| OpenAi_o3_mini_0131        | 4.0          | 4.0              | 1.00    |
| Grok3mini_beta             | 3.75         | 4                | 0.96875 |
| OpenAi_o1_1217             | 4            | 3.75             | 0.96875 |
| Gemini_20_Pro_0205         | 3.75         | 4.0              | 0.96875 |
| ChatGPT4o                  | 3.5          | 4                | 0.9375  |
| GPT45_0227                 | 3.5          | 3.75             | 0.90625 |
| DeepSeekV3_0324            | 3.5          | 3.75             | 0.90625 |
| Gemini_15_Pro_002          | 3.5          | 3.5              | 0.875   |
| Gemini_20_Flash_Think_0121 | 3.75         | 3.25             | 0.875   |
| Llama_4_Maverick           | 3.5          | 3.25             | 0.84375 |
| DeepSeekR1                 | 3.5          | 2.75             | 0.78125 |
| AmazonNovaPro              | 2.25         | 2.25             | 0.5625  |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution and Leadership:
    - Google has taken the lead with Gemini 2.5 Pro Experimental achieving the top position at 93.3% total score
    - xAI's Grok 3 mini beta makes a strong debut at 92.3% total score, showing impressive performance particularly in code generation (93.0%) and code documentation (90.2%), though its high scores
      are partially due to its unique token generation approach
    - Anthropic maintains strong market position with Claude 3.7 Sonnet at 91.4% total score
    - OpenAI shows competitive performance with o3-mini at 90.8% total score
    - Gemini 2.0 Pro Experimental (90.7%) and Claude 3.7 Sonnet Thinking (90.2%) maintain strong positions
    - Grok 3 beta demonstrates solid capabilities at 89.4% total score
    - ChatGPT-4o demonstrates strong performance at 87.8%, making it a viable option for many use cases
    - OpenAI o1 (1217) shows solid capabilities at 84.5%, comparable to Gemini 2.0 Flash Thinking (84.4%)
    - Five models achieving perfect LCIF scores demonstrates advancement in handling complex instructions
    - DeepSeek's open-source models (V3 at 83.9% and R1 at 77.1%) represent significant achievements in the open-source space, allowing for self-hosting within organizations
    - Meta's Llama 4 Maverick (74.5%) shows notable performance with only 17B active parameters despite having 400B total parameters, demonstrating efficient scaling with its mixture-of-experts
      architecture (128 experts)

2. Performance Patterns:
    - Specialized strengths emerge across different categories:
        * Code Translation: Gemini 2.5 Pro leads with 90.9%, followed by Gemini 2.0 Pro Experimental at 90.5% and Grok 3 mini beta at 89.4%
        * Code Generation: Grok 3 mini beta ranks first (93.0%), followed by Gemini 2.5 Pro (92.5%) and Claude 3.7 Sonnet Thinking (91.4%)
        * Code Documentation: Grok 3 mini beta leads with 90.2%, followed by Gemini 2.5 Pro (89.9%) and OpenAI o3-mini (86.8%)
        * LCIF: Five models (Gemini 2.5 Pro, Claude 3.7 Sonnet, Grok 3 beta, Claude 3.7 Sonnet Thinking, and OpenAI o3-mini) achieve perfect scores
    - Top-tier models consistently achieve >90% scores across most categories
    - Grok 3 mini beta demonstrates exceptional token generation speed at 152.5 tokens per second, but its long total execution time (24.05 minutes) indicates it generates significantly more reasoning
      tokens during its processing
    - Gemini 2.0 Flash Thinking Experimental continues to show incredible speed, achieving 188.2 tokens per second
    - Processing efficiency varies significantly, with newer models generally showing improved performance
    - ChatGPT-4o demonstrates excellent overall efficiency with high speed (123.9 tokens/sec) and remarkably short processing time (6.53 minutes), making it nearly four times faster than Grok 3 mini
      beta in total execution time

3. Market Implications:
    - Intense competition between major providers (Google, xAI, Anthropic, OpenAI, Meta) continues to drive rapid innovation
    - xAI's Grok models show impressive performance, with Grok 3 mini beta offering excellent value at low cost ($0.30/$0.50 per MTok)
    - Performance of OpenAI's o3-mini demonstrates that smaller, more efficient models can compete with larger counterparts
    - ChatGPT-4o offers a good balance of performance, speed, and cost-effectiveness
    - OpenAI o1 (1217) provides strong capabilities but at a higher price point compared to newer models
    - Meta's Llama 4 Maverick combines good performance with excellent speed (103.2 tokens/sec) and very low cost ($0.05/$0.22 per MTok), making it a cost-effective option for general use cases,
      though its strengths lie more in social networking applications rather than dedicated software development tasks
    - Amazon Nova Pro, while scoring 61.8%, shows promise for enterprise applications as we await the more powerful Amazon Nova Premier model
    - Due to high price of GPT-4.5 preview, it appears OpenAI has decreased the amount of tokens generated in output
    - DeepSeek's open-source models provide viable alternatives for organizations seeking to host their own LLMs

4. Areas for Improvement:
    - Computational efficiency remains a challenge for some models, particularly GPT-4.5 preview with its low speed of 8.59 tokens per second
    - Response quality and consistency across different types of tasks varies significantly
    - Cost-performance balance continues to be a key consideration for model selection, with experimental models currently offering the best value

These findings indicate a maturing market with increasing sophistication in model capabilities. The strong performance of newer models (Gemini 2.5 Pro, Grok 3 mini beta, Claude 3.7 Sonnet, o3-mini)
suggests a trend toward both higher performance and greater efficiency. Organizations now have more options to choose from, whether prioritizing overall performance, specific capabilities, deployment
flexibility, or cost-effectiveness, including self-hosting options with open-source models like DeepSeek.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>