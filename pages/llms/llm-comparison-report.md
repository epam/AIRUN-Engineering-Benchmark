# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

Key findings:

- Gemini 2.5 Flash Preview takes the lead with an exceptional 94.47% total score
- Gemini 2.5 Pro Preview (05-06) follows with an impressive 92.7% total score
- OpenAI o3 ranks third with a strong 92.08% total score, showing particular strength in code documentation
- Grok 3 mini beta comes in fourth with 91.79% total score
- Claude 3.7 Sonnet follows closely with 90.93% total score
- OpenAI o4-mini demonstrates excellent performance at 90.56%, offering strong capabilities at a more accessible price point
- OpenAI's o3-mini model continues to perform well at 89.97%, confirming its suitability for coding tasks
- Claude 3.7 Sonnet (Thinking) shows strong results at 89.89%
- GPT-4.1 mini shows impressive capabilities at 88.87%, particularly in code generation
- Grok 3 beta achieves a solid 88.65% total score
- GPT-4.1 achieves a solid 88.13% total score with perfect LCIF performance
- ChatGPT-4o shows strong overall performance at 86.40%, making it a competitive option
- OpenAI o1 demonstrates solid capabilities at 84.16%
- DeepSeek V3, an open-source model that can be self-hosted, shows significant improvements over R1 at 83.53%
- GPT-4.5 preview shows middle-range results at 77.47%
- DeepSeek R1 performs at 76.56%
- Llama 4 Maverick demonstrates competitive performance at 73.04%, showing Meta's progress in the LLM space
- GPT-4.1 nano performs at 72.90%
- Amazon Nova Premier performs at 61.5%, showing only slight improvement over Amazon Nova Pro (60.61%)

Performance metrics highlights:

- Fastest token generation: GPT-4.1 nano (204.22 tokens/sec), followed by Grok 3 mini beta (152.47 tokens/sec) and Gemini 2.5 Flash Preview (148.46 tokens/sec)
- Shortest execution time: GPT-4.1 nano (3.84 minutes), followed by Llama 4 Maverick (6.48 minutes) and ChatGPT-4o (6.53 minutes)
- Most tokens generated: Grok 3 mini beta (220,054 tokens), followed by Gemini 2.5 Flash Preview (214,906 tokens), Claude 3.7 Sonnet (Thinking) (200,502 tokens) and Gemini 2.5 Pro Preview (05-06) (
  164,779 tokens)
- Most cost-effective high performers: Grok 3 mini beta (91.79% score at $0.30/$0.50 per MTok), OpenAI o4-mini (90.56% score at $1.10/$4.40 per MTok), and GPT-4.1 mini (88.87% score at $0.40/$1.60 per
  MTok)

Best results by category:

- Code Translation: Gemini 2.5 Flash Preview leads with 91.90%, followed by Gemini 2.5 Pro Preview (05-06) at 89.57% and GPT-4.1 mini at 89.53%
- Code Generation: Gemini 2.5 Flash Preview ranks first (92.45%), followed by Grok 3 mini beta (91.79%) and Gemini 2.5 Pro Preview (05-06) (90.36%)
- Code Documentation: Gemini 2.5 Flash Preview leads impressively with 93.52%, followed by OpenAI o3 (91.80%) and Gemini 2.5 Pro Preview (05-06) (90.81%)
- LCIF: Nine models achieve perfect 100% scores: Gemini 2.5 Flash Preview, Gemini 2.5 Pro Preview, OpenAI o3, Claude 3.7 Sonnet, OpenAI o4-mini, Claude 3.7 Sonnet (Thinking), GPT-4.1, Grok 3 beta, and
  OpenAI o3-mini

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                           | Benchmark model ID        | Execution Date | Benchmark | Code Translation | Code Generation | Code Document | LCIF    | Total Score |
|---------------------------------|---------------------------|----------------|-----------|------------------|-----------------|---------------|---------|-------------|
| Gemini 2.5 Flash Preview (0417) | Gemini_25_Flash_0417      | 2025-04-26     | v2        | 91.90%           | 92.45%          | 93.52%        | 100.00% | 94.47%      |
| Gemini 2.5 Pro Preview (0506)   | Gemini_25_Pro_0506        | 2025-05-14     | v2        | 89.57%           | 90.36%          | 90.81%        | 100.00% | 92.69%      |
| OpenAI o3 (high) (0416)         | OpenAi_o3_0416            | 2025-04-16     | v2        | 88.91%           | 87.63%          | 91.80%        | 100.00% | 92.08%      |
| Grok 3 mini beta (high)         | Grok3mini_beta            | 2025-04-13     | v2        | 88.90%           | 91.79%          | 89.60%        | 96.88%  | 91.79%      |
| Claude 3.7 Sonnet               | Claude_Sonnet_37          | 2025-03-20     | v2        | 87.90%           | 89.56%          | 86.27%        | 100.00% | 90.93%      |
| OpenAI o4 mini (high) (0416)    | OpenAi_o4_mini_0416       | 2025-04-16     | v2        | 85.59%           | 87.54%          | 89.11%        | 100.00% | 90.56%      |
| OpenAI o3-mini (medium) (0131)  | OpenAi_o3_mini_0131       | 2025-03-20     | v2        | 86.79%           | 87.01%          | 86.08%        | 100.00% | 89.97%      |
| Claude 3.7 Sonnet (Thinking)    | Claude_Sonnet_37_Thinking | 2025-03-20     | v2        | 86.92%           | 90.78%          | 81.84%        | 100.00% | 89.89%      |
| GPT 4.1 mini (0414)             | GPT41mini_0414            | 2025-04-15     | v2        | 89.53%           | 91.16%          | 81.05%        | 93.75%  | 88.87%      |
| Grok 3 Beta                     | Grok3_beta                | 2025-04-11     | v2        | 87.85%           | 86.08%          | 80.67%        | 100.00% | 88.65%      |
| GPT 4.1 (0414)                  | GPT41_0414                | 2025-04-15     | v2        | 85.66%           | 88.57%          | 78.29%        | 100.00% | 88.13%      |
| ChatGPT-4o                      | ChatGPT4o                 | 2025-03-20     | v2        | 84.42%           | 82.75%          | 84.67%        | 93.75%  | 86.40%      |
| OpenAI o1 (medium) (1217)       | OpenAi_o1_1217            | 2025-03-20     | v2        | 83.30%           | 81.03%          | 75.45%        | 96.88%  | 84.16%      |
| DeepSeek V3 (0324)              | DeepSeekV3_0324           | 2025-03-27     | v2        | 81.98%           | 81.63%          | 79.89%        | 90.63%  | 83.53%      |
| GPT-4.5 preview                 | GPT45_0227                | 2025-03-20     | v2        | 66.47%           | 78.03%          | 74.75%        | 90.63%  | 77.47%      |
| DeepSeek R1                     | DeepSeekR1                | 2025-03-20     | v2        | 73.97%           | 77.61%          | 76.52%        | 78.13%  | 76.56%      |
| Llama 4 Maverick                | Llama_4_Maverick          | 2025-04-07     | v2        | 67.33%           | 73.41%          | 67.02%        | 84.38%  | 73.04%      |
| GPT-4.1 nano (0414)             | GPT41nano_0414            | 2025-04-25     | v2        | 83.41%           | 85.25%          | 76.08%        | 46.88%  | 72.90%      |
| Amazon Nova Premier             | AmazonNovaPremier         | 2025-05-16     | v2        | 47.61%           | 64.11%          | 68.73%        | 65.63%  | 61.52%      |
| Amazon Nova Pro                 | AmazonNovaPro             | 2025-03-28     | v2        | 52.44%           | 67.83%          | 65.93%        | 56.25%  | 60.61%      |
| Gemma 3 12B Q4                  | Gemma_3_12B               | 2025-05-07     | v2        | 52.11%           | 67.41%          | 74.78%        | 0.00%   | 48.57%      |
| Gemma 3 4B                      | Gemma_3_4B                | 2025-04-25     | v2        | 27.77%           | 44.31%          | 58.44%        | 0.00%   | 32.63%      |
| Gemma 3 1B                      | Gemma_3_1B                | 2025-04-25     | v2        | 19.44%           | 29.16%          | 36.57%        | 0.00%   | 21.30%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Flash_0417      | 3.780        | 4.000            | 68.12    | 10331.00  | 151.67            | 0.9190  |
| Gemini_25_Pro_0506        | 3.839        | 3.984            | 149.38   | 7568.00   | 50.66             | 0.8957  |
| GPT41mini_0414            | 4.000        | 3.780            | 79.04    | 4289.14   | 54.27             | 0.8953  |
| OpenAi_o3_0416            | 3.850        | 3.587            | 34.39    | 5222.71   | 151.85            | 0.8891  |
| Grok3mini_beta            | 3.767        | 3.769            | 94.12    | 14279.71  | 151.72            | 0.8890  |
| Claude_Sonnet_37          | 3.781        | 3.786            | 73.37    | 6240.14   | 85.05             | 0.8790  |
| Grok3_beta                | 3.829        | 3.666            | 41.70    | 3807.71   | 91.30             | 0.8785  |
| Claude_Sonnet_37_Thinking | 3.657        | 3.857            | 145.33   | 12453.29  | 85.69             | 0.8692  |
| OpenAi_o3_mini_0131       | 3.674        | 3.687            | 47.52    | 5598.00   | 117.80            | 0.8679  |
| GPT41_0414                | 3.780        | 3.666            | 80.39    | 4010.86   | 49.89             | 0.8566  |
| OpenAi_o4_mini_0416       | 3.853        | 3.510            | 104.89   | 9954.29   | 94.90             | 0.8559  |
| ChatGPT4o                 | 3.449        | 3.480            | 19.00    | 2738.00   | 144.11            | 0.8442  |
| GPT41nano_0414            | 3.347        | 3.179            | 12.00    | 2607.57   | 217.32            | 0.8341  |
| OpenAi_o1_1217            | 3.670        | 3.559            | 89.62    | 5107.86   | 56.99             | 0.8330  |
| DeepSeekV3_0324           | 3.491        | 3.680            | 123.30   | 4374.71   | 35.48             | 0.8198  |
| DeepSeekR1                | 3.356        | 2.989            | 65.33    | 4757.00   | 72.82             | 0.7397  |
| Llama_4_Maverick          | 3.116        | 2.420            | 22.70    | 2379.86   | 104.82            | 0.6733  |
| GPT45_0227                | 3.364        | 2.496            | 183.17   | 1757.86   | 9.60              | 0.6647  |
| AmazonNovaPro             | 2.551        | 1.723            | 24.82    | 2084.57   | 83.99             | 0.5244  |
| Gemma_3_12B               | 2.539        | 2.001            | 109.35   | 2291.86   | 20.96             | 0.5211  |
| AmazonNovaPremier         | 2.781        | 1.169            | 30.56    | 1611.00   | 52.72             | 0.4761  |
| Gemma_3_4B                | 1.454        | 0.879            | 67.32    | 1868.14   | 27.75             | 0.2777  |
| Gemma_3_1B                | 0.524        | 0.793            | 22.52    | 1921.00   | 85.29             | 0.1944  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Flash_0417      | 3.884        | 3.944            | 59.74    | 10196.78  | 170.69            | 0.9245  |
| Grok3mini_beta            | 4.000        | 3.823            | 62.36    | 9035.00   | 144.88            | 0.9179  |
| GPT41mini_0414            | 4.000        | 3.873            | 41.27    | 3135.75   | 75.99             | 0.9116  |
| Claude_Sonnet_37_Thinking | 3.944        | 3.939            | 125.64   | 10304.25  | 82.01             | 0.9078  |
| Gemini_25_Pro_0506        | 4.000        | 3.938            | 179.38   | 6964.50   | 38.83             | 0.9036  |
| Claude_Sonnet_37          | 3.886        | 3.873            | 66.44    | 5169.75   | 77.81             | 0.8956  |
| GPT41_0414                | 4.000        | 3.706            | 53.87    | 2854.88   | 53.00             | 0.8857  |
| OpenAi_o3_0416            | 4.000        | 3.450            | 35.84    | 4502.13   | 125.61            | 0.8763  |
| OpenAi_o4_mini_0416       | 3.874        | 3.633            | 62.88    | 7136.38   | 113.49            | 0.8754  |
| OpenAi_o3_mini_0131       | 3.938        | 3.438            | 28.29    | 3471.13   | 122.70            | 0.8701  |
| Grok3_beta                | 3.861        | 3.520            | 30.55    | 2493.00   | 81.61             | 0.8608  |
| GPT41nano_0414            | 3.806        | 2.883            | 7.67     | 1752.13   | 228.59            | 0.8525  |
| ChatGPT4o                 | 3.813        | 3.076            | 15.01    | 1850.50   | 123.33            | 0.8275  |
| DeepSeekV3_0324           | 3.883        | 3.249            | 63.38    | 2316.63   | 36.55             | 0.8163  |
| OpenAi_o1_1217            | 4.000        | 3.043            | 61.21    | 3280.38   | 53.59             | 0.8103  |
| GPT45_0227                | 4.000        | 2.903            | 184.73   | 1449.38   | 7.85              | 0.7803  |
| DeepSeekR1                | 3.634        | 3.094            | 73.97    | 4766.50   | 64.44             | 0.7761  |
| Llama_4_Maverick          | 3.511        | 2.568            | 14.03    | 1470.75   | 104.86            | 0.7341  |
| AmazonNovaPro             | 3.273        | 2.431            | 19.28    | 1477.38   | 76.63             | 0.6783  |
| Gemma_3_12B               | 3.426        | 2.490            | 93.15    | 1890.89   | 20.30             | 0.6741  |
| AmazonNovaPremier         | 3.405        | 2.063            | 24.51    | 1161.50   | 47.38             | 0.6411  |
| Gemma_3_4B                | 2.132        | 1.696            | 59.75    | 1644.22   | 27.52             | 0.4431  |
| Gemma_3_1B                | 1.383        | 0.858            | 18.17    | 1530.89   | 84.25             | 0.2916  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Flash_0417      | 3.926        | 4.000            | 48.13    | 5646.44   | 117.33            | 0.9352  |
| OpenAi_o3_0416            | 3.997        | 3.738            | 28.42    | 3088.44   | 108.65            | 0.9180  |
| Gemini_25_Pro_0506        | 3.999        | 3.891            | 110.88   | 6231.89   | 56.20             | 0.9081  |
| Grok3mini_beta            | 3.891        | 3.512            | 31.73    | 5312.89   | 167.45            | 0.8960  |
| OpenAi_o4_mini_0416       | 3.931        | 3.586            | 34.76    | 3856.33   | 110.93            | 0.8911  |
| Claude_Sonnet_37          | 3.788        | 3.629            | 47.84    | 3062.89   | 64.03             | 0.8627  |
| OpenAi_o3_mini_0131       | 3.824        | 3.378            | 25.42    | 2827.56   | 111.21            | 0.8608  |
| ChatGPT4o                 | 3.653        | 3.332            | 15.40    | 1615.11   | 104.86            | 0.8467  |
| Claude_Sonnet_37_Thinking | 3.724        | 3.320            | 56.33    | 3432.78   | 60.94             | 0.8184  |
| GPT41mini_0414            | 3.810        | 3.143            | 40.93    | 2371.33   | 57.94             | 0.8105  |
| Grok3_beta                | 3.626        | 3.236            | 32.77    | 2325.89   | 70.98             | 0.8067  |
| DeepSeekV3_0324           | 3.483        | 3.424            | 38.76    | 1295.00   | 33.41             | 0.7989  |
| GPT41_0414                | 3.547        | 3.226            | 52.29    | 2180.67   | 41.71             | 0.7829  |
| DeepSeekR1                | 3.420        | 3.036            | 25.56    | 1817.11   | 71.09             | 0.7652  |
| GPT41nano_0414            | 3.301        | 2.572            | 9.45     | 1641.44   | 173.70            | 0.7608  |
| OpenAi_o1_1217            | 3.473        | 3.027            | 56.48    | 2921.22   | 51.73             | 0.7545  |
| Gemma_3_12B               | 3.436        | 3.113            | 92.50    | 1903.67   | 20.58             | 0.7478  |
| GPT45_0227                | 3.461        | 3.139            | 183.29   | 1554.89   | 8.48              | 0.7475  |
| AmazonNovaPremier         | 3.198        | 2.589            | 20.33    | 925.22    | 45.51             | 0.6873  |
| Llama_4_Maverick          | 2.897        | 2.486            | 13.09    | 1302.11   | 99.47             | 0.6702  |
| AmazonNovaPro             | 3.101        | 2.273            | 15.37    | 1278.56   | 83.21             | 0.6593  |
| Gemma_3_4B                | 2.734        | 2.301            | 47.13    | 1302.33   | 27.63             | 0.5844  |
| Gemma_3_1B                | 1.177        | 1.658            | 21.09    | 1791.00   | 84.91             | 0.3657  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                      | Avg Accuracy | Avg Completeness | Score ↓ |
|----------------------------|--------------|------------------|---------|
| Gemini_25_Flash_0417       | 4            | 4                | 1       |
| Gemini_25_Pro_0506         | 4            | 4                | 1       |
| OpenAi_o3_0416             | 4            | 4                | 1       |
| Claude_Sonnet_37           | 4            | 4                | 1       |
| OpenAi_o4_mini_0416        | 4            | 4                | 1       |
| Claude_Sonnet_37_Thinking  | 4            | 4                | 1       |
| GPT41_0414                 | 4            | 4                | 1       |
| Grok3_beta                 | 4            | 4                | 1       |
| OpenAi_o3_mini_0131        | 4            | 4                | 1       |
| Gemini_20_Pro_0205         | 3.75         | 4                | 0.96875 |
| OpenAi_o1_1217             | 4            | 3.75             | 0.96875 |
| Grok3mini_beta             | 3.75         | 4                | 0.96875 |
| ChatGPT4o                  | 3.5          | 4                | 0.9375  |
| GPT41mini_0414             | 3.75         | 3.75             | 0.9375  |
| GPT45_0227                 | 3.5          | 3.75             | 0.90625 |
| DeepSeekV3_0324            | 3.5          | 3.75             | 0.90625 |
| Gemini_20_Flash_Think_0121 | 3.75         | 3.25             | 0.875   |
| Llama_4_Maverick           | 3.5          | 3.25             | 0.84375 |
| DeepSeekR1                 | 3.5          | 2.75             | 0.78125 |
| AmazonNovaPremier          | 2.5          | 2.75             | 0.65625 |
| AmazonNovaPro              | 2.25         | 2.25             | 0.5625  |
| GPT41nano_0414             | 2.5          | 1.25             | 0.46875 |
| Gemma_3_4B                 | 0            | 0                | 0       |
| Gemma_3_1B                 | 0            | 0                | 0       |
| Gemma_3_12B                | 0            | 0                | 0       |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution and Leadership:
    - Google has consolidated its lead with Gemini 2.5 Flash Preview achieving the top position at 94.47% total score
    - Gemini 2.5 Pro Preview (05-06) follows closely in second place at 92.7% total score
    - OpenAI has made significant strides with its o3 model ranking third at 92.08% total score, showing exceptional strength in code documentation (91.80%)
    - xAI's Grok 3 mini beta sits in fourth place at 91.79% total score, demonstrating impressive performance particularly in code generation (91.79%) and code documentation (89.60%)
    - Anthropic maintains strong market position with Claude 3.7 Sonnet at 90.93% total score
    - OpenAI's o4-mini model debuts strongly at 90.56% total score, offering excellent performance at a more accessible price point
    - OpenAI continues to show competitive performance with o3-mini at 89.97% total score
    - Claude 3.7 Sonnet Thinking (89.89%) maintains a strong position
    - GPT-4.1 mini and GPT-4.1 show strong capabilities at 88.87% and 88.13% respectively, with GPT-4.1 mini excelling in code generation (91.16%)
    - Grok 3 beta demonstrates solid capabilities at 88.65% total score
    - ChatGPT-4o demonstrates strong performance at 86.40%, making it a viable option for many use cases
    - OpenAI o1 (1217) shows solid capabilities at 84.16%
    - Nine models achieving perfect LCIF scores demonstrates advancement in handling complex instructions
    - DeepSeek's open-source models (V3 at 83.53% and R1 at 76.56%) represent significant achievements in the open-source space, allowing for self-hosting within organizations
    - Meta's Llama 4 Maverick (73.04%) shows notable performance with only 17B active parameters despite having 400B total parameters, demonstrating efficient scaling with its mixture-of-experts
      architecture (128 experts)

2. Performance Patterns:
    - Specialized strengths emerge across different categories:
        * Code Translation: Gemini 2.5 Flash Preview leads with 91.90%, followed by Gemini 2.5 Pro Preview (05-06) at 89.57% and GPT-4.1 mini at 89.53%
        * Code Generation: Gemini 2.5 Flash Preview ranks first (92.45%), followed by Grok 3 mini beta (91.79%) and Gemini 2.5 Pro Preview (05-06) at 90.36%
        * Code Documentation: Gemini 2.5 Flash Preview leads impressively with 93.52%, followed by OpenAI o3 (91.80%) and Gemini 2.5 Pro Preview (05-06) at 90.81%
        * LCIF: Nine models (Gemini 2.5 Flash Preview, Gemini 2.5 Pro Preview (05-06), OpenAI o3, Claude 3.7 Sonnet, OpenAI o4-mini, Claude 3.7 Sonnet Thinking, GPT-4.1, Grok 3 beta, and OpenAI
          o3-mini)
          achieve perfect scores
    - Top-tier models consistently achieve >90% scores across most categories
    - GPT-4.1 nano demonstrates the fastest token generation at 204.22 tokens per second with very short execution time (3.84 minutes)
    - OpenAI o3 shows exceptional processing efficiency with fast token generation (128.14 tokens/sec) and short execution time (13.06 minutes)
    - Gemini 2.5 Flash Preview demonstrates strong token generation speed at 148.46 tokens per second with a total execution time of 24.13 minutes
    - Grok 3 mini beta demonstrates exceptional token generation speed at 152.47 tokens per second, but its total execution time (24.05 minutes) indicates it generates significantly more reasoning
      tokens during its processing
    - OpenAI o4-mini shows strong balance between speed (104.17 tokens/sec) and total output (161,478 tokens)
    - GPT-4.1 mini achieves good results with relatively modest output (76,452 tokens), showing efficient use of resources
    - Processing efficiency varies significantly, with newer models generally showing improved performance
    - ChatGPT-4o demonstrates excellent overall efficiency with high speed (123.85 tokens/sec) and remarkably short processing time (6.53 minutes), making it nearly four times faster than Grok 3 mini
      beta in total execution time

3. Market Implications:
    - Intense competition between major providers (Google, xAI, Anthropic, OpenAI, Meta) continues to drive rapid innovation
    - Google's Gemini models dominate the top positions:
        * Gemini 2.5 Flash Preview achieves exceptional performance at 94.47% total score with reasonable pricing ($0.15/$3.50 per MTok)
        * Gemini 2.5 Pro Preview (05-06) follows at 92.7% total score but at a higher price point ($1.25/$10.00 per MTok up to 200K; $2.50/$15.00 per MTok beyond)
    - OpenAI's new models show significant improvements across the board:
        * o3 demonstrates exceptional capability at 92.08% total score, though at a higher price point ($10.00/$40.00 per MTok)
        * o4-mini offers excellent value with 90.56% performance at a more accessible price ($1.10/$4.40 per MTok)
        * GPT-4.1 mini provides strong capabilities (88.87%) at a very competitive price ($0.40/$1.60 per MTok)
        * GPT-4.1 delivers solid performance (88.13%) at a reasonable price point for premium services ($2.00/$8.00 per MTok)
    - xAI's Grok models continue to show impressive performance, with Grok 3 mini beta offering excellent value at low cost ($0.30/$0.50 per MTok)
    - Performance of OpenAI's o3-mini demonstrates that smaller, more efficient models can compete with larger counterparts
    - ChatGPT-4o offers a good balance of performance, speed, and cost-effectiveness
    - OpenAI o1 (1217) provides strong capabilities (84.16%) but at a higher price point compared to newer models
    - Meta's Llama 4 Maverick combines good performance with excellent speed (103.21 tokens/sec) and very low cost ($0.05/$0.22 per MTok), making it a cost-effective option for general use cases,
      though its strengths lie more in social networking applications rather than dedicated software development tasks
    - Amazon Nova Premier performs at 61.5%, showing only slight improvement over Amazon Nova Pro at 60.61%
    - Due to high price of GPT-4.5 preview ($75.00/$150.00 per MTok), it appears OpenAI has decreased the amount of tokens generated in output
    - DeepSeek's open-source models provide viable alternatives for organizations seeking to host their own LLMs

4. Areas for Improvement:
    - Computational efficiency remains a challenge for some models, particularly GPT-4.5 preview with its low speed of 8.59 tokens per second
    - Response quality and consistency across different types of tasks varies significantly
    - Cost-performance balance continues to be a key consideration for model selection, with experimental models currently offering the best value
    - Open-source models like Gemma 3 series show significant capabilities but still require improvement for large context handling, as shown by their 0% scores in LCIF

These findings indicate a rapidly evolving market with increasing sophistication in model capabilities. The strong performance of newer models (Gemini 2.5 Flash Preview, Gemini 2.5 Pro Preview, OpenAI
o3, Grok 3 mini beta, Claude 3.7 Sonnet, OpenAI o4-mini) suggests a trend toward both higher performance and greater efficiency. Google's Gemini 2.5 series models demonstrate exceptional capabilities
across all categories, particularly in code documentation. OpenAI's expanded lineup (o3, o4-mini, GPT-4.1, GPT-4.1 mini) provides excellent options at different price points, allowing organizations to
choose models that balance performance and cost according to their specific needs. Organizations now have more options than ever before, whether prioritizing overall performance, specific
capabilities, deployment flexibility, or cost-effectiveness, including self-hosting options with open-source models like DeepSeek.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>