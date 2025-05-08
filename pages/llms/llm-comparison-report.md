# LLM's Evaluation Results

## Abstract

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

Key findings:

- Gemini 2.5 Pro Preview takes the lead with an exceptional 93.7% total score
- OpenAI o3 ranks second with an impressive 92.9% total score, showing particular strength in code documentation
- Grok 3 mini beta comes in third with 92.3% total score
- Claude 3.7 Sonnet follows closely with 91.4% total score
- OpenAI o4-mini demonstrates excellent performance at 91.0%, offering strong capabilities at a more accessible price point
- OpenAI's o3-mini model continues to perform well at 90.8%, confirming its suitability for coding tasks
- GPT-4.1 mini shows impressive capabilities at 89.4%, particularly in code generation
- GPT-4.1 achieves a solid 88.5% total score with perfect LCIF performance
- Gemini 2.0 Pro Experimental and Claude 3.7 Sonnet (Thinking) show strong results at 90.7% and 90.2% respectively
- Grok 3 beta achieves an impressive 89.4% total score
- ChatGPT-4o shows strong overall performance at 87.8%, making it a competitive option
- OpenAI o1 demonstrates solid capabilities at 84.5%, performing similarly to Gemini 2.0 Flash Thinking
- DeepSeek V3, an open-source model that can be self-hosted, shows significant improvements over R1 at 83.9%
- Llama 4 Maverick demonstrates competitive performance at 74.5%, showing Meta's progress in the LLM space
- Amazon Nova Pro, while smaller, achieves 61.8% and shows potential as we await the more powerful Amazon Nova Premier model

Performance metrics highlights:

- Fastest token generation: Gemini 2.0 Flash Thinking Experimental (188.16 tokens/sec), followed by Grok 3 mini beta (152.47 tokens/sec) and OpenAI o3 (128.14 tokens/sec)
- Shortest execution time: ChatGPT-4o (6.53 minutes), followed by Llama 4 Maverick (6.48 minutes) and OpenAI o3 (13.06 minutes)
- Most tokens generated: Grok 3 mini beta (220,054 tokens), followed by Claude 3.7 Sonnet Thinking (200,502 tokens) and OpenAI o4-mini (161,478 tokens)
- Most cost-effective high performers: Grok 3 mini beta (92.3% score at $0.30/$0.50 per MTok), OpenAI o4-mini (91.0% score at $1.10/$4.40 per MTok), and GPT-4.1 mini (89.4% score at $0.40/$1.60 per
  MTok)

Best results by category:

- Code Translation: Gemini 2.5 Pro leads with 91.2%, followed by OpenAI o3 at 90.0% and GPT-4.1 mini at 90.0%
- Code Generation: Gemini 2.5 Pro ranks first (93.4%), followed by Grok 3 mini beta (93.0%) and GPT-4.1 mini (92.3%)
- Code Documentation: OpenAI o3 leads impressively with 92.4%, followed by Grok 3 mini beta (90.2%) and Gemini 2.5 Pro (90.1%)
- LCIF: Seven models achieve perfect 100% scores: Gemini 2.5 Pro, OpenAI o3, Claude 3.7 Sonnet, OpenAI o4-mini, Claude 3.7 Sonnet (Thinking), GPT-4.1, Grok 3 beta, and OpenAI o3-mini

The final conclusion in the [end](#conclusion) of the report.

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                              | Benchmark model ID         | Execution Date | Benchmark | Code Translation | Code Generation | Code Document | LCIF    | Total Score |
| ---------------------------------- | -------------------------- | -------------- | --------- | ---------------- | --------------- | ------------- | ------- | ----------- |
| Gemini 2.5 Pro Preview (0325)      | Gemini_25_Pro_0325         | 2025-04-14     | v2        | 91.21%           | 93.37%          | 90.09%        | 100.00% | 93.67%      |
| OpenAI o3 (high) (0416)            | OpenAi_o3_0416             | 2025-04-16     | v2        | 90.02%           | 89.08%          | 92.44%        | 100.00% | 92.89%      |
| Grok 3 mini beta (high)            | Grok3mini_beta             | 2025-04-13     | v2        | 89.38%           | 92.95%          | 90.16%        | 96.88%  | 92.34%      |
| Claude 3.7 Sonnet                  | Claude_Sonnet_37           | 2025-03-20     | v2        | 88.44%           | 90.40%          | 86.65%        | 100.00% | 91.37%      |
| OpenAI o4 mini (high) (0416)       | OpenAi_o4_mini_0416        | 2025-04-16     | v2        | 85.98%           | 88.56%          | 89.63%        | 100.00% | 91.04%      |
| OpenAI o3-mini (medium) (0131)     | OpenAi_o3_mini_0131        | 2025-03-20     | v2        | 87.60%           | 88.69%          | 86.79%        | 100.00% | 90.77%      |
| Gemini 2.0 Pro (02-05 Exp)         | Gemini_20_Pro_0205         | 2025-03-20     | v2        | 90.53%           | 89.68%          | 85.74%        | 96.88%  | 90.71%      |
| Claude 3.7 Sonnet (Thinking)       | Claude_Sonnet_37_Thinking  | 2025-03-20     | v2        | 87.22%           | 91.40%          | 82.16%        | 100.00% | 90.20%      |
| GPT 4.1 mini (0414)                | GPT41mini_0414             | 2025-04-15     | v2        | 90.01%           | 92.27%          | 81.49%        | 93.75%  | 89.38%      |
| Grok 3 Beta                        | Grok3_beta                 | 2025-04-11     | v2        | 88.75%           | 87.49%          | 81.22%        | 100.00% | 89.37%      |
| GPT 4.1 (0414)                     | GPT41_0414                 | 2025-04-15     | v2        | 86.13%           | 89.40%          | 78.64%        | 100.00% | 88.54%      |
| ChatGPT-4o                         | ChatGPT4o                  | 2025-03-20     | v2        | 86.36%           | 85.43%          | 85.85%        | 93.75%  | 87.85%      |
| OpenAI o1 (medium) (1217)          | OpenAi_o1_1217             | 2025-03-20     | v2        | 83.73%           | 81.79%          | 75.77%        | 96.88%  | 84.54%      |
| Gemini 2.0 Flash Think (01-21 exp) | Gemini_20_Flash_Think_0121 | 2025-03-20     | v2        | 81.84%           | 91.34%          | 77.07%        | 87.50%  | 84.44%      |
| DeepSeek V3 (0324)                 | DeepSeekV3_0324            | 2025-03-27     | v2        | 82.29%           | 82.30%          | 80.36%        | 90.63%  | 83.89%      |
| GPT-4.5 preview                    | GPT45_0227                 | 2025-03-20     | v2        | 66.67%           | 78.24%          | 74.85%        | 90.63%  | 77.60%      |
| DeepSeek R1                        | DeepSeekR1                 | 2025-03-20     | v2        | 74.55%           | 78.33%          | 77.23%        | 78.13%  | 77.06%      |
| Llama 4 Maverick                   | Llama_4_Maverick           | 2025-04-07     | v2        | 68.94%           | 76.15%          | 68.41%        | 84.38%  | 74.47%      |
| GPT-4.1 nano (0414)                | GPT41nano_0414             | 2025-04-25     | v2        | 83.41%           | 85.25%          | 76.07%        | 46.88%  | 72.90%      |
| Amazon Nova Pro                    | AmazonNovaPro              | 2025-03-28     | v2        | 53.90%           | 69.83%          | 67.11%        | 56.25%  | 61.8%       |
| Gemma 3 12B Q4                     | Gemma_3_12B                | 2025-05-07     | v2        | 52.11%           | 67.41%          | 74.78%        | 0.00%   | 48.57%      |
| Gemma 3 4B                         | Gemma_3_4B                 | 2025-04-25     | v2        | 27.77%           | 44.31%          | 58.44%        | 37.50%  | 42.01%      |
| Gemma 3 1B                         | Gemma_3_1B                 | 2025-04-25     | v2        | 19.44%           | 29.16%          | 36.57%        | 0.00%   | 21.29%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
| -------------------------- | ------------ | ---------------- | -------- | --------- | ----------------- | ------- |
| Gemini_25_Pro_0325         | 3.807        | 3.994            | 100.37   | 10592.14  | 105.53            | 0.9121  |
| Gemini_20_Pro_0205         | 3.794        | 4.000            | 75.54    | 5072.29   | 67.15             | 0.9053  |
| OpenAi_o3_0416             | 3.850        | 3.587            | 34.39    | 5222.71   | 151.85            | 0.9002  |
| GPT41mini_0414             | 4.000        | 3.780            | 79.04    | 4289.14   | 54.27             | 0.9001  |
| Grok3mini_beta             | 3.767        | 3.769            | 94.12    | 14279.71  | 151.72            | 0.8938  |
| Grok3_beta                 | 3.829        | 3.666            | 41.70    | 3807.71   | 91.30             | 0.8875  |
| Claude_Sonnet_37           | 3.781        | 3.786            | 73.37    | 6240.14   | 85.05             | 0.8844  |
| OpenAi_o3_mini_0131        | 3.674        | 3.687            | 47.52    | 5598.00   | 117.80            | 0.8760  |
| Claude_Sonnet_37_Thinking  | 3.657        | 3.857            | 145.33   | 12453.29  | 85.69             | 0.8722  |
| ChatGPT4o                  | 3.449        | 3.480            | 19.00    | 2738.00   | 144.11            | 0.8636  |
| GPT41nano_0414             | 3.347        | 3.179            | 12.00    | 2607.57   | 217.32            | 0.8341  |
| GPT41_0414                 | 3.780        | 3.666            | 80.39    | 4010.86   | 49.89             | 0.8613  |
| OpenAi_o4_mini_0416        | 3.853        | 3.510            | 104.89   | 9954.29   | 94.90             | 0.8598  |
| OpenAi_o1_1217             | 3.670        | 3.559            | 89.62    | 5107.86   | 56.99             | 0.8373  |
| DeepSeekV3_0324            | 3.491        | 3.680            | 123.30   | 4374.71   | 35.48             | 0.8229  |
| Gemini_20_Flash_Think_0121 | 2.963        | 3.531            | 25.15    | 5312.86   | 211.27            | 0.8184  |
| DeepSeekR1                 | 3.356        | 2.989            | 65.33    | 4757.00   | 72.82             | 0.7455  |
| Llama_4_Maverick           | 3.116        | 2.420            | 22.70    | 2379.86   | 104.82            | 0.6894  |
| GPT45_0227                 | 3.364        | 2.496            | 183.17   | 1757.86   | 9.60              | 0.6667  |
| AmazonNovaPro              | 2.551        | 1.723            | 24.82    | 2084.57   | 83.99             | 0.5390  |
| Gemma_3_12B                | 2.539        | 2.001            | 109.35   | 2291.86   | 20.96             | 0.5211  |
| Gemma_3_4B                 | 1.454        | 0.879            | 67.32    | 1868.14   | 27.75             | 0.2777  |
| Gemma_3_1B                 | 0.524        | 0.793            | 22.52    | 1921.00   | 85.29             | 0.1944  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
| -------------------------- | ------------ | ---------------- | -------- | --------- | ----------------- | ------- |
| Gemini_25_Pro_0325         | 4.000        | 3.994            | 101.25   | 10532.63  | 104.03            | 0.9337  |
| Grok3mini_beta             | 4.000        | 3.823            | 62.36    | 9035.00   | 144.88            | 0.9295  |
| GPT41mini_0414             | 4.000        | 3.873            | 41.27    | 3135.75   | 75.99             | 0.9227  |
| Claude_Sonnet_37_Thinking  | 3.944        | 3.939            | 125.64   | 10304.25  | 82.01             | 0.9140  |
| Gemini_20_Flash_Think_0121 | 3.879        | 3.486            | 20.13    | 3812.63   | 189.41            | 0.9134  |
| Claude_Sonnet_37           | 3.886        | 3.873            | 66.44    | 5169.75   | 77.81             | 0.9040  |
| Gemini_20_Pro_0205         | 3.925        | 3.813            | 74.63    | 4777.63   | 64.02             | 0.8968  |
| GPT41_0414                 | 4.000        | 3.706            | 53.87    | 2854.88   | 53.00             | 0.8940  |
| OpenAi_o3_0416             | 4.000        | 3.450            | 35.84    | 4502.13   | 125.61            | 0.8908  |
| OpenAi_o3_mini_0131        | 3.938        | 3.438            | 28.29    | 3471.13   | 122.70            | 0.8869  |
| OpenAi_o4_mini_0416        | 3.874        | 3.633            | 62.88    | 7136.38   | 113.49            | 0.8856  |
| Grok3_beta                 | 3.861        | 3.520            | 30.55    | 2493.00   | 81.61             | 0.8749  |
| GPT41nano_0414             | 3.806        | 2.883            | 7.67     | 1752.13   | 228.59            | 0.8525  |
| ChatGPT4o                  | 3.813        | 3.076            | 15.01    | 1850.50   | 123.33            | 0.8543  |
| DeepSeekV3_0324            | 3.883        | 3.249            | 63.38    | 2316.63   | 36.55             | 0.8230  |
| OpenAi_o1_1217             | 4.000        | 3.043            | 61.21    | 3280.38   | 53.59             | 0.8179  |
| DeepSeekR1                 | 3.634        | 3.094            | 73.97    | 4766.50   | 64.44             | 0.7833  |
| GPT45_0227                 | 4.000        | 2.903            | 184.73   | 1449.38   | 7.85              | 0.7824  |
| Llama_4_Maverick           | 3.511        | 2.568            | 14.03    | 1470.75   | 104.86            | 0.7615  |
| AmazonNovaPro              | 3.273        | 2.431            | 19.28    | 1477.38   | 76.63             | 0.6983  |
| Gemma_3_12B                | 3.426        | 2.490            | 93.15    | 1890.89   | 20.30             | 0.6741  |
| Gemma_3_4B                 | 2.132        | 1.696            | 59.75    | 1644.22   | 27.52             | 0.4431  |
| Gemma_3_1B                 | 1.383        | 0.858            | 18.17    | 1530.89   | 84.25             | 0.2916  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                      | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
| -------------------------- | ------------ | ---------------- | -------- | --------- | ----------------- | ------- |
| OpenAi_o3_0416             | 3.997        | 3.738            | 28.42    | 3088.44   | 108.65            | 0.9244  |
| Grok3mini_beta             | 3.891        | 3.512            | 31.73    | 5312.89   | 167.45            | 0.9016  |
| Gemini_25_Pro_0325         | 3.954        | 3.771            | 91.51    | 7828.67   | 85.55             | 0.9009  |
| OpenAi_o4_mini_0416        | 3.931        | 3.586            | 34.76    | 3856.33   | 110.93            | 0.8963  |
| OpenAi_o3_mini_0131        | 3.824        | 3.378            | 25.42    | 2827.56   | 111.21            | 0.8679  |
| Claude_Sonnet_37           | 3.788        | 3.629            | 47.84    | 3062.89   | 64.03             | 0.8665  |
| ChatGPT4o                  | 3.653        | 3.332            | 15.40    | 1615.11   | 104.86            | 0.8585  |
| Gemini_20_Pro_0205         | 3.769        | 3.617            | 80.13    | 5123.89   | 63.94             | 0.8574  |
| Claude_Sonnet_37_Thinking  | 3.724        | 3.320            | 56.33    | 3432.78   | 60.94             | 0.8216  |
| GPT41mini_0414             | 3.810        | 3.143            | 40.93    | 2371.33   | 57.94             | 0.8149  |
| Grok3_beta                 | 3.626        | 3.236            | 32.77    | 2325.89   | 70.98             | 0.8122  |
| DeepSeekV3_0324            | 3.483        | 3.424            | 38.76    | 1295.00   | 33.41             | 0.8036  |
| GPT41_0414                 | 3.547        | 3.226            | 52.29    | 2180.67   | 41.71             | 0.7864  |
| DeepSeekR1                 | 3.420        | 3.036            | 25.56    | 1817.11   | 71.09             | 0.7723  |
| GPT41nano_0414             | 3.301        | 2.572            | 9.45     | 1641.44   | 173.70            | 0.7607  |
| Gemini_20_Flash_Think_0121 | 3.222        | 3.011            | 33.57    | 5841.11   | 174.02            | 0.7707  |
| OpenAi_o1_1217             | 3.473        | 3.027            | 56.48    | 2921.22   | 51.73             | 0.7577  |
| Gemma_3_12B                | 3.436        | 3.113            | 92.50    | 1903.67   | 20.58             | 0.7478  |
| GPT45_0227                 | 3.461        | 3.139            | 183.29   | 1554.89   | 8.48              | 0.7485  |
| Llama_4_Maverick           | 2.897        | 2.486            | 13.09    | 1302.11   | 99.47             | 0.6841  |
| AmazonNovaPro              | 3.101        | 2.273            | 15.37    | 1278.56   | 83.21             | 0.6711  |
| Gemma_3_4B                 | 2.734        | 2.301            | 47.13    | 1302.33   | 27.63             | 0.5844  |
| Gemma_3_1B                 | 1.177        | 1.658            | 21.09    | 1791.00   | 84.91             | 0.3657  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                      | Avg Accuracy | Avg Completeness | Score ↓ |
| -------------------------- | ------------ | ---------------- | ------- |
| Gemini_25_Pro_0325         | 4            | 4                | 1       |
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
| AmazonNovaPro              | 2.25         | 2.25             | 0.5625  |
| GPT41nano_0414             | 2.5          | 1.25             | 0.46875 |
| Gemma_3_4B                 | 2.5          | 0.5              | 0.375   |
| Gemma_3_1B                 | 0            | 0                | 0       |
| Gemma_3_12B                | 0            | 0                | 0       |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal several significant insights about the current state of LLM capabilities:

1. Model Evolution and Leadership:
    - Google has consolidated its lead with Gemini 2.5 Pro Preview achieving the top position at 93.7% total score
    - OpenAI has made significant strides with its o3 model ranking second at 92.9% total score, showing exceptional strength in code documentation (92.4%)
    - xAI's Grok 3 mini beta sits in third place at 92.3% total score, demonstrating impressive performance particularly in code generation (93.0%) and code documentation (90.2%)
    - OpenAI's o4-mini model debuts strongly at 91.0% total score, offering excellent performance at a more accessible price point
    - GPT-4.1 mini and GPT-4.1 show strong capabilities at 89.4% and 88.5% respectively, with GPT-4.1 mini excelling in code generation (92.3%)
    - Anthropic maintains strong market position with Claude 3.7 Sonnet at 91.4% total score
    - OpenAI continues to show competitive performance with o3-mini at 90.8% total score
    - Gemini 2.0 Pro Experimental (90.7%) and Claude 3.7 Sonnet Thinking (90.2%) maintain strong positions
    - Grok 3 beta demonstrates solid capabilities at 89.4% total score
    - ChatGPT-4o demonstrates strong performance at 87.8%, making it a viable option for many use cases
    - OpenAI o1 (1217) shows solid capabilities at 84.5%, comparable to Gemini 2.0 Flash Thinking (84.4%)
    - Seven models achieving perfect LCIF scores demonstrates advancement in handling complex instructions
    - DeepSeek's open-source models (V3 at 83.9% and R1 at 77.1%) represent significant achievements in the open-source space, allowing for self-hosting within organizations
    - Meta's Llama 4 Maverick (74.5%) shows notable performance with only 17B active parameters despite having 400B total parameters, demonstrating efficient scaling with its mixture-of-experts
      architecture (128 experts)

2. Performance Patterns:
    - Specialized strengths emerge across different categories:
        * Code Translation: Gemini 2.5 Pro leads with 91.2%, followed by OpenAI o3 at 90.0% and GPT-4.1 mini at 90.0%
        * Code Generation: Gemini 2.5 Pro ranks first (93.4%), followed by Grok 3 mini beta (93.0%) and GPT-4.1 mini (92.3%)
        * Code Documentation: OpenAI o3 leads impressively with 92.4%, followed by Grok 3 mini beta (90.2%) and Gemini 2.5 Pro (90.1%)
        * LCIF: Seven models (Gemini 2.5 Pro, OpenAI o3, Claude 3.7 Sonnet, OpenAI o4-mini, Claude 3.7 Sonnet Thinking, GPT-4.1, Grok 3 beta, and OpenAI o3-mini) achieve perfect scores
    - Top-tier models consistently achieve >90% scores across most categories
    - OpenAI o3 shows exceptional processing efficiency with fast token generation (128.1 tokens/sec) and very short execution time (13.06 minutes)
    - Grok 3 mini beta demonstrates exceptional token generation speed at 152.5 tokens per second, but its long total execution time (24.05 minutes) indicates it generates significantly more reasoning
      tokens during its processing
    - OpenAI o4-mini shows strong balance between speed (104.2 tokens/sec) and total output (161,478 tokens)
    - GPT-4.1 mini achieves good results with relatively modest output (76,452 tokens), showing efficient use of resources
    - Gemini 2.0 Flash Thinking Experimental continues to show incredible speed, achieving 188.2 tokens per second
    - Processing efficiency varies significantly, with newer models generally showing improved performance
    - ChatGPT-4o demonstrates excellent overall efficiency with high speed (123.9 tokens/sec) and remarkably short processing time (6.53 minutes), making it nearly four times faster than Grok 3 mini
      beta in total execution time

3. Market Implications:
    - Intense competition between major providers (Google, xAI, Anthropic, OpenAI, Meta) continues to drive rapid innovation
    - OpenAI's new models show significant improvements across the board:
        * o3 demonstrates exceptional capability at 92.9% total score, though at a higher price point ($10.00/$40.00 per MTok)
        * o4-mini offers excellent value with 91.0% performance at a more accessible price ($1.10/$4.40 per MTok)
        * GPT-4.1 mini provides strong capabilities (89.4%) at a very competitive price ($0.40/$1.60 per MTok)
        * GPT-4.1 delivers solid performance (88.5%) at a reasonable price point for premium services ($2.00/$8.00 per MTok)
    - xAI's Grok models continue to show impressive performance, with Grok 3 mini beta offering excellent value at low cost ($0.30/$0.50 per MTok)
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

These findings indicate a rapidly evolving market with increasing sophistication in model capabilities. The strong performance of newer models (Gemini 2.5 Pro, OpenAI o3, Grok 3 mini beta, Claude 3.7
Sonnet, OpenAI o4-mini) suggests a trend toward both higher performance and greater efficiency. OpenAI's expanded lineup (o3, o4-mini, GPT-4.1, GPT-4.1 mini) provides excellent options at different
price points, allowing organizations to choose models that balance performance and cost according to their specific needs. Organizations now have more options than ever before, whether prioritizing
overall performance, specific capabilities, deployment flexibility, or cost-effectiveness, including self-hosting options with open-source models like DeepSeek.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>