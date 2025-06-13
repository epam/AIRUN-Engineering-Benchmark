# LLM's Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                            | Benchmark model ID        | Execution Date | Benchmark | Code Translation | Code Generation | Code Document | LCIF    | Total Score |
|----------------------------------|---------------------------|----------------|-----------|------------------|-----------------|---------------|---------|-------------|
| Gemini 2.5 Flash Preview (05-20) | Gemini_25_Flash_0520      | 2025-05-22     | v2        | 95.09%           | 95.05%          | 93.80%        | 100.00% | 95.99%      |
| Codex Mini Latest                | Codex_Mini_Latest         | 2025-06-09     | v2        | 93.45%           | 89.41%          | 91.05%        | 100.00% | 93.48%      |
| Gemini 2.5 Pro Preview (05-06)   | Gemini_25_Pro_0506        | 2025-05-14     | v2        | 90.54%           | 91.18%          | 89.26%        | 100.00% | 92.75%      |
| Claude 4 Sonnet                  | Claude_Sonnet_4           | 2025-05-23     | v2        | 90.88%           | 92.75%          | 85.13%        | 100.00% | 92.19%      |
| OpenAI o3 (high) (04-16)         | OpenAi_o3_0416            | 2025-04-16     | v2        | 88.91%           | 87.63%          | 91.53%        | 100.00% | 92.02%      |
| Grok 3 mini beta (high)          | Grok3mini_beta            | 2025-04-13     | v2        | 88.90%           | 91.79%          | 89.17%        | 96.88%  | 91.68%      |
| Claude 4 Sonnet (Thinking)       | Claude_Sonnet_4_Thinking  | 2025-05-23     | v2        | 87.26%           | 91.72%          | 86.31%        | 100.00% | 91.32%      |
| Gemini 2.5 Pro Preview (06-05)   | Gemini_25_Pro_0605        | 2025-06-09     | v2        | 90.06%           | 88.20%          | 86.44%        | 100.00% | 91.17%      |
| Claude 4 Opus (Thinking)         | Claude_Opus_4_Thinking    | 2025-05-26     | v2        | 89.62%           | 92.56%          | 81.84%        | 100.00% | 91.01%      |    
| Claude 3.7 Sonnet                | Claude_Sonnet_37          | 2025-03-20     | v2        | 87.90%           | 89.56%          | 86.11%        | 100.00% | 90.89%      |
| OpenAI o4-mini (high) (04-16)    | OpenAi_o4_mini_0416       | 2025-04-16     | v2        | 85.59%           | 87.54%          | 88.83%        | 100.00% | 90.49%      |
| OpenAI o3-mini (medium) (01-31)  | OpenAi_o3_mini_0131       | 2025-03-20     | v2        | 86.79%           | 87.01%          | 85.80%        | 100.00% | 89.90%      |
| Claude 3.7 Sonnet (Thinking)     | Claude_Sonnet_37_Thinking | 2025-03-20     | v2        | 86.92%           | 90.78%          | 81.69%        | 100.00% | 89.85%      |
| GPT-4.1 mini (04-14)             | GPT41mini_0414            | 2025-04-15     | v2        | 89.53%           | 91.16%          | 80.90%        | 93.75%  | 88.83%      |
| Grok 3 Beta                      | Grok3_beta                | 2025-04-11     | v2        | 87.85%           | 86.08%          | 80.49%        | 100.00% | 88.61%      |
| GPT-4.1 (04-14)                  | GPT41_0414                | 2025-04-15     | v2        | 85.66%           | 88.57%          | 78.19%        | 100.00% | 88.10%      |
| ChatGPT-4o                       | ChatGPT4o                 | 2025-03-20     | v2        | 84.42%           | 82.75%          | 84.41%        | 93.75%  | 86.33%      |
| DeepSeek R1 (05-28)              | DeepSeekR1_0528           | 2025-05-30     | v2        | 76.67%           | 87.66%          | 81.61%        | 90.63%  | 84.14%      |
| OpenAI o1 (medium) (12-17)       | OpenAi_o1_1217            | 2025-03-20     | v2        | 83.30%           | 81.03%          | 75.32%        | 96.88%  | 84.13%      |  
| DeepSeek V3 (03-24)              | DeepSeekV3_0324           | 2025-03-27     | v2        | 81.98%           | 81.63%          | 79.81%        | 90.63%  | 83.51%      |
| GPT-4.5 preview                  | GPT45_0227                | 2025-03-20     | v2        | 66.47%           | 78.03%          | 74.73%        | 90.63%  | 77.47%      |
| DeepSeek R1                      | DeepSeekR1                | 2025-03-20     | v2        | 73.97%           | 77.61%          | 76.34%        | 78.13%  | 76.51%      |
| Llama 4 Maverick                 | Llama_4_Maverick          | 2025-04-07     | v2        | 67.33%           | 73.41%          | 66.77%        | 84.38%  | 72.97%      |
| GPT-4.1 nano (04-14)             | GPT41nano_0414            | 2025-04-25     | v2        | 83.41%           | 85.25%          | 75.63%        | 46.88%  | 72.79%      |
| Amazon Nova Premier              | AmazonNovaPremier         | 2025-05-16     | v2        | 47.61%           | 64.11%          | 68.62%        | 65.63%  | 61.49%      |
| Amazon Nova Pro                  | AmazonNovaPro             | 2025-03-28     | v2        | 52.44%           | 67.83%          | 65.72%        | 56.25%  | 60.56%      |
| Gemma 3 27B                      | Gemma_3_27B               | 2025-06-09     | v2        | 59.36%           | 60.69%          | 59.70%        | 43.75%  | 55.87%      |
| Gemma 3 12B Q4                   | Gemma_3_12B               | 2025-05-07     | v2        | 52.11%           | 67.41%          | 74.73%        | 0.00%   | 48.56%      |
| Phi 4                            | Phi_4                     | 2025-06-09     | v2        | 54.90%           | 66.19%          | 70.22%        | 0.00%   | 47.83%      |
| Gemma 3 4B                       | Gemma_3_4B                | 2025-04-25     | v2        | 27.77%           | 44.31%          | 58.37%        | 0.00%   | 32.61%      |
| Gemma 3 1B                       | Gemma_3_1B                | 2025-04-25     | v2        | 19.44%           | 29.16%          | 36.36%        | 0.00%   | 21.24%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Flash_0520      | 3.956        | 4.000            | 70.52    | 14528.43  | 206.03            | 0.9509  |
| Codex_Mini_Latest         | 4.000        | 3.980            | 96.83    | 12858.29  | 132.80            | 0.9345  |
| Claude_Sonnet_4           | 3.780        | 4.000            | 62.45    | 6487.43   | 103.88            | 0.9088  |
| Gemini_25_Pro_0506        | 3.813        | 4.000            | 178.93   | 17993.14  | 100.56            | 0.9054  |
| Gemini_25_Pro_0605        | 3.877        | 3.860            | 91.17    | 9343.57   | 102.49            | 0.9006  |
| Claude_Opus_4_Thinking    | 3.747        | 3.929            | 62.26    | 6234.14   | 100.13            | 0.8962  |
| GPT41mini_0414            | 4.000        | 3.780            | 79.04    | 4289.14   | 54.27             | 0.8953  |
| OpenAi_o3_0416            | 3.850        | 3.587            | 34.39    | 5222.71   | 151.85            | 0.8891  |
| Grok3mini_beta            | 3.767        | 3.769            | 94.12    | 14279.71  | 151.72            | 0.8890  |
| Claude_Sonnet_37          | 3.781        | 3.786            | 73.37    | 6240.14   | 85.05             | 0.8790  |
| Grok3_beta                | 3.829        | 3.666            | 41.70    | 3807.71   | 91.30             | 0.8785  |
| Claude_Sonnet_4_Thinking  | 3.804        | 3.691            | 77.92    | 7311.00   | 93.83             | 0.8726  |
| Claude_Sonnet_37_Thinking | 3.657        | 3.857            | 145.33   | 12453.29  | 85.69             | 0.8692  |
| OpenAi_o3_mini_0131       | 3.674        | 3.687            | 47.52    | 5598.00   | 117.80            | 0.8679  |
| GPT41_0414                | 3.780        | 3.666            | 80.39    | 4010.86   | 49.89             | 0.8566  |
| OpenAi_o4_mini_0416       | 3.853        | 3.510            | 104.89   | 9954.29   | 94.90             | 0.8559  |
| ChatGPT4o                 | 3.449        | 3.480            | 19.00    | 2738.00   | 144.11            | 0.8442  |
| GPT41nano_0414            | 3.347        | 3.179            | 12.00    | 2607.57   | 217.32            | 0.8341  |
| OpenAi_o1_1217            | 3.670        | 3.559            | 89.62    | 5107.86   | 56.99             | 0.8330  |
| DeepSeekV3_0324           | 3.491        | 3.680            | 123.30   | 4374.71   | 35.48             | 0.8198  |
| DeepSeekR1_0528           | 3.137        | 3.343            | 74.66    | 9626.57   | 128.94            | 0.7667  |
| DeepSeekR1                | 3.356        | 2.989            | 65.33    | 4757.00   | 72.82             | 0.7397  |
| Llama_4_Maverick          | 3.116        | 2.420            | 22.70    | 2379.86   | 104.82            | 0.6733  |
| GPT45_0227                | 3.364        | 2.496            | 183.17   | 1757.86   | 9.60              | 0.6647  |
| Gemma_3_27B               | 2.894        | 2.161            | 47.94    | 2564.57   | 53.50             | 0.5936  |
| Phi_4                     | 2.787        | 1.676            | 21.28    | 1730.86   | 81.34             | 0.5490  |
| AmazonNovaPro             | 2.551        | 1.723            | 24.82    | 2084.57   | 83.99             | 0.5244  |
| Gemma_3_12B               | 2.539        | 2.001            | 109.35   | 2291.86   | 20.96             | 0.5211  |
| AmazonNovaPremier         | 2.781        | 1.169            | 30.56    | 1611.00   | 52.72             | 0.4761  |
| Gemma_3_4B                | 1.454        | 0.879            | 67.32    | 1868.14   | 27.75             | 0.2777  |
| Gemma_3_1B                | 0.524        | 0.793            | 22.52    | 1921.00   | 85.29             | 0.1944  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Gemini_25_Flash_0520      | 4.000        | 3.951            | 61.85    | 14090.13  | 227.83            | 0.9505  |
| Claude_Sonnet_4           | 4.000        | 3.999            | 74.60    | 7666.38   | 102.77            | 0.9275  |
| Claude_Opus_4_Thinking    | 4.000        | 3.998            | 83.54    | 8146.50   | 97.51             | 0.9256  |
| Grok3mini_beta            | 4.000        | 3.823            | 62.36    | 9035.00   | 144.88            | 0.9179  |
| Claude_Sonnet_4_Thinking  | 4.000        | 3.938            | 95.05    | 8769.75   | 92.27             | 0.9172  |
| Gemini_25_Pro_0506        | 4.000        | 3.899            | 169.92   | 16239.75  | 95.58             | 0.9118  |
| GPT41mini_0414            | 4.000        | 3.873            | 41.27    | 3135.75   | 75.99             | 0.9116  |
| Claude_Sonnet_37_Thinking | 3.944        | 3.939            | 125.64   | 10304.25  | 82.01             | 0.9078  |
| Claude_Sonnet_37          | 3.886        | 3.873            | 66.44    | 5169.75   | 77.81             | 0.8956  |
| Codex_Mini_Latest         | 4.000        | 3.564            | 35.93    | 5345.88   | 148.77            | 0.8941  |
| GPT41_0414                | 4.000        | 3.706            | 53.87    | 2854.88   | 53.00             | 0.8857  |
| Gemini_25_Pro_0605        | 3.880        | 3.723            | 72.91    | 7154.38   | 98.12             | 0.8820  |
| DeepSeekR1_0528           | 4.000        | 3.433            | 26.29    | 3114.50   | 118.47            | 0.8766  |
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
| Phi_4                     | 3.154        | 2.313            | 13.05    | 1037.89   | 79.55             | 0.6619  |
| AmazonNovaPremier         | 3.405        | 2.063            | 24.51    | 1161.50   | 47.38             | 0.6411  |
| Gemma_3_27B               | 2.891        | 2.293            | 31.75    | 1693.25   | 53.33             | 0.6069  |
| Gemma_3_4B                | 2.132        | 1.696            | 59.75    | 1644.22   | 27.52             | 0.4431  |
| Gemma_3_1B                | 1.383        | 0.858            | 18.17    | 1530.89   | 84.25             | 0.2916  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score  |
|---------------------------|--------------|------------------|----------|-----------|-------------------|--------|
| Gemini_25_Flash_0520      | 3.920        | 3.896            | 53.74    | 10235.89  | 190.48            | 0.9380 |
| OpenAi_o3_0416            | 3.997        | 3.738            | 28.42    | 3088.44   | 108.65            | 0.9153 |
| Codex_Mini_Latest         | 3.982        | 3.623            | 27.95    | 4037.11   | 144.46            | 0.9105 |
| Gemini_25_Pro_0506        | 3.988        | 3.693            | 96.79    | 8700.89   | 89.90             | 0.8926 |
| Grok3mini_beta            | 3.891        | 3.512            | 31.73    | 5312.89   | 167.45            | 0.8917 |
| OpenAi_o4_mini_0416       | 3.931        | 3.586            | 34.76    | 3856.33   | 110.93            | 0.8883 |
| Gemini_25_Pro_0605        | 3.929        | 3.489            | 68.36    | 5983.67   | 87.53             | 0.8644 |
| Claude_Sonnet_4_Thinking  | 3.919        | 3.506            | 44.74    | 2940.56   | 65.72             | 0.8631 |
| Claude_Sonnet_37          | 3.788        | 3.629            | 47.84    | 3062.89   | 64.03             | 0.8611 |
| OpenAi_o3_mini_0131       | 3.824        | 3.378            | 25.42    | 2827.56   | 111.21            | 0.8580 |
| Claude_Sonnet_4           | 3.873        | 3.394            | 32.49    | 2363.22   | 72.74             | 0.8513 |
| ChatGPT4o                 | 3.653        | 3.332            | 15.40    | 1615.11   | 104.86            | 0.8441 |
| Claude_Opus_4_Thinking    | 3.572        | 3.458            | 44.15    | 2832.22   | 64.15             | 0.8184 |
| Claude_Sonnet_37_Thinking | 3.724        | 3.320            | 56.33    | 3432.78   | 60.94             | 0.8169 |
| DeepSeekR1_0528           | 3.693        | 3.279            | 51.27    | 4393.11   | 85.69             | 0.8161 |
| GPT41mini_0414            | 3.810        | 3.143            | 40.93    | 2371.33   | 57.94             | 0.8090 |
| Grok3_beta                | 3.626        | 3.236            | 32.77    | 2325.89   | 70.98             | 0.8049 |
| DeepSeekV3_0324           | 3.483        | 3.424            | 38.76    | 1295.00   | 33.41             | 0.7981 |
| GPT41_0414                | 3.547        | 3.226            | 52.29    | 2180.67   | 41.71             | 0.7819 |
| DeepSeekR1                | 3.420        | 3.036            | 25.56    | 1817.11   | 71.09             | 0.7634 |
| GPT41nano_0414            | 3.301        | 2.572            | 9.45     | 1641.44   | 173.70            | 0.7563 |
| OpenAi_o1_1217            | 3.473        | 3.027            | 56.48    | 2921.22   | 51.73             | 0.7532 |
| GPT45_0227                | 3.461        | 3.139            | 183.29   | 1554.89   | 8.48              | 0.7473 |
| Gemma_3_12B               | 3.436        | 3.113            | 92.50    | 1903.67   | 20.58             | 0.7473 |
| Phi_4                     | 3.292        | 2.483            | 14.98    | 1195.11   | 79.78             | 0.7022 |
| AmazonNovaPremier         | 3.198        | 2.589            | 20.33    | 925.22    | 45.51             | 0.6862 |
| Llama_4_Maverick          | 2.897        | 2.486            | 13.09    | 1302.11   | 99.47             | 0.6677 |
| AmazonNovaPro             | 3.101        | 2.273            | 15.37    | 1278.56   | 83.21             | 0.6572 |
| Gemma_3_27B               | 2.942        | 2.194            | 46.78    | 1603.00   | 34.26             | 0.5970 |
| Gemma_3_4B                | 2.734        | 2.301            | 47.13    | 1302.33   | 27.63             | 0.5837 |
| Gemma_3_1B                | 1.177        | 1.658            | 21.09    | 1791.00   | 84.91             | 0.3636 |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                     | Avg Accuracy | Avg Completeness | Score ↓ |
|---------------------------|--------------|------------------|---------|
| Gemini_25_Flash_0520      | 4            | 4                | 1       |
| Codex_Mini_Latest         | 4            | 4                | 1       |
| Gemini_25_Pro_0506        | 4            | 4                | 1       |
| Gemini_25_Pro_0605        | 4            | 4                | 1       |
| Claude_Sonnet_4           | 4            | 4                | 1       |
| Claude_Sonnet_4_Thinking  | 4            | 4                | 1       |
| Claude_Opus_4_Thinking    | 4            | 4                | 1       |
| OpenAi_o3_0416            | 4            | 4                | 1       |
| Claude_Sonnet_37          | 4            | 4                | 1       |
| OpenAi_o4_mini_0416       | 4            | 4                | 1       |
| Claude_Sonnet_37_Thinking | 4            | 4                | 1       |
| GPT41_0414                | 4            | 4                | 1       |
| Grok3_beta                | 4            | 4                | 1       |
| OpenAi_o3_mini_0131       | 4            | 4                | 1       |
| OpenAi_o1_1217            | 4            | 3.75             | 0.96875 |
| Grok3mini_beta            | 3.75         | 4                | 0.96875 |
| ChatGPT4o                 | 3.5          | 4                | 0.9375  |
| GPT41mini_0414            | 3.75         | 3.75             | 0.9375  |
| DeepSeekR1_0528           | 2.25         | 2.25             | 0.90625 |
| GPT45_0227                | 3.5          | 3.75             | 0.90625 |
| DeepSeekV3_0324           | 3.5          | 3.75             | 0.90625 |
| Llama_4_Maverick          | 3.5          | 3.25             | 0.84375 |
| DeepSeekR1                | 3.5          | 2.75             | 0.78125 |
| AmazonNovaPremier         | 2.5          | 2.75             | 0.65625 |
| AmazonNovaPro             | 2.25         | 2.25             | 0.5625  |
| GPT41nano_0414            | 2.5          | 1.25             | 0.46875 |
| Gemma_3_27B               | 2            | 1.5              | 0.43750 |
| Gemma_3_4B                | 0            | 0                | 0       |
| Phi_4                     | 0            | 0                | 0       |
| Gemma_3_1B                | 0            | 0                | 0       |
| Gemma_3_12B               | 0            | 0                | 0       |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal significant insights about current LLM capabilities for software engineering tasks:

**Market Leadership:**

- **Google dominates** with Gemini 2.5 Flash Preview (05-20) (95.99%) leading in all categories while maintaining excellent speed (208.25 tokens/sec) and cost-effectiveness ($1.09 total)
- **Specialized coding models excel**: Codex Mini Latest (93.48%) shows highest accuracy but has refusal behaviors; newer Gemini 2.5 Pro versions show performance regression
- **Claude 4 Sonnet outperforms Thinking mode** (92.19% vs 91.32%), suggesting reasoning mode doesn't always improve coding tasks
- **Speed champions**: GPT-4.1 nano achieves fastest execution (3.84 min), while ChatGPT-4o offers the best efficiency balance

**Key Performance Insights:**

- **Category leaders**: Gemini 2.5 Flash Preview (05-20) dominates code translation (95.09%), generation (95.05%), and documentation (93.80%)
- **Cost-effectiveness winners**: Grok 3 mini beta (91.68% for $0.13), GPT-4.1 nano ($0.02)
- **Perfect LCIF scores**: 14 models achieve 100% in large context instruction following, showing maturity in handling complex tasks
- **Open-source landscape**: Microsoft's Phi-4 (47.83%) shows competitive mid-range performance, while Google's Gemma 3 family offers scalable options from 1B (21.24%) to 27B (55.87%) parameters.
  However, all open-source models struggle with LCIF tasks, indicating limitations in complex instruction following

**Market Implications:**

- **Intense competition drives innovation** across Google, Anthropic, OpenAI, xAI, and Meta
- **Price-performance optimization**: Models like Grok 3 mini beta offer exceptional value, while premium models like Claude 4 Opus provide top-tier capabilities at higher cost
- **Specialized vs general trade-offs**: Thinking modes show mixed results; speed-optimized models often match quality while reducing costs
- **Enterprise options expand**: From ultra-low-cost Llama 4 Maverick to premium Claude 4 Opus, organizations have diverse deployment choices including self-hosted open-source alternatives

The rapid evolution demonstrates that model selection should prioritize specific use cases rather than assuming latest means best—with clear winners emerging in speed (GPT-4.1 nano), value (Grok 3
mini beta), overall performance (Gemini 2.5 Flash Preview (05-20)), and specialized coding (Codex Mini Latest).

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>