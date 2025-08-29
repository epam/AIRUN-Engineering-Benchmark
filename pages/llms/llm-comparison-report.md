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
| GPT-5 (08-07)                    | GPT5_0807                 | 2025-08-11     | v2        | 100.00%          | 99.22%          | 98.61%        | 100.00% | 99.46%      |
| Gemini 2.5 Flash Preview (05-20) | Gemini_25_Flash_0520      | 2025-05-22     | v2        | 99.45%           | 99.39%          | 97.69%        | 100.00% | 99.13%      |
| Grok_Code_0825                   | Grok Code Fast            | 2025-08-28     | v2        | 97.45%           | 98.55%          | 96.57%        | 100.00% | 98.14%      |
| Gemini 2.5 Pro Preview (05-06)   | Gemini_25_Pro_0506        | 2025-05-14     | v2        | 97.66%           | 98.73%          | 96.01%        | 100.00% | 98.10%      |
| Grok 4 (07-09)                   | Grok4_0709                | 2025-07-11     | v2        | 96.70%           | 97.00%          | 95.86%        | 100.00% | 97.39%      |
| Codex Mini Latest                | Codex_Mini_Latest         | 2025-06-09     | v2        | 99.75%           | 94.55%          | 95.07%        | 100.00% | 97.34%      |
| Claude 4 Sonnet                  | Claude_Sonnet_4           | 2025-05-23     | v2        | 97.25%           | 99.98%          | 90.85%        | 100.00% | 97.02%      |
| Claude 4.1 Opus                  | Claude_Opus_41            | 2025-08-11     | v2        | 94.80%           | 99.28%          | 93.32%        | 100.00% | 96.85%      |
| Claude 4 Sonnet (Thinking)       | Claude_Sonnet_4_Thinking  | 2025-05-23     | v2        | 93.70%           | 99.22%          | 92.81%        | 100.00% | 96.43%      |
| Gemini 2.5 Pro Preview (06-05)   | Gemini_25_Pro_0605        | 2025-06-09     | v2        | 96.71%           | 95.03%          | 92.72%        | 100.00% | 96.12%      |
| Claude 3.7 Sonnet                | Claude_Sonnet_37          | 2025-03-20     | v2        | 94.59%           | 96.98%          | 92.71%        | 100.00% | 96.07%      |
| Claude 4 Opus (Thinking)         | Claude_Opus_4_Thinking    | 2025-05-26     | v2        | 95.95%           | 99.97%          | 87.88%        | 100.00% | 95.95%      |
| gpt-oss-120b                     | GPT_OSS_120B              | 2025-08-11     | v2        | 94.96%           | 97.63%          | 96.90%        | 93.75%  | 95.81%      |
| OpenAI o3-pro (high) (06-10)     | OpenAi_o3_pro_0610        | 2025-06-16     | v2        | 94.77%           | 94.41%          | 93.90%        | 100.00% | 95.77%      |
| OpenAI o3 (high) (04-16)         | OpenAi_o3_0416            | 2025-04-16     | v2        | 92.96%           | 93.13%          | 96.68%        | 100.00% | 95.69%      |
| Grok 3 mini beta (high)          | Grok3mini_beta            | 2025-04-13     | v2        | 94.20%           | 97.78%          | 92.54%        | 96.88%  | 95.35%      |
| Claude 3.7 Sonnet (Thinking)     | Claude_Sonnet_37_Thinking | 2025-03-20     | v2        | 93.93%           | 98.53%          | 88.06%        | 100.00% | 95.13%      |
| OpenAI o4-mini (high) (04-16)    | OpenAi_o4_mini_0416       | 2025-04-16     | v2        | 92.04%           | 93.83%          | 93.96%        | 100.00% | 94.96%      |
| GPT-4.1 mini (04-14)             | GPT41mini_0414            | 2025-04-15     | v2        | 97.25%           | 98.41%          | 86.92%        | 93.75%  | 94.08%      |
| OpenAI o3-mini (medium) (01-31)  | OpenAi_o3_mini_0131       | 2025-03-20     | v2        | 92.02%           | 92.19%          | 90.03%        | 100.00% | 93.56%      |
| GPT-4.1 (04-14)                  | GPT41_0414                | 2025-04-15     | v2        | 93.07%           | 96.33%          | 84.65%        | 100.00% | 93.51%      |
| Grok 3 Beta                      | Grok3_beta                | 2025-04-11     | v2        | 93.68%           | 92.27%          | 85.76%        | 100.00% | 92.93%      |
| OpenAI o1 (medium) (12-17)       | OpenAi_o1_1217            | 2025-03-20     | v2        | 90.36%           | 88.03%          | 81.25%        | 96.88%  | 89.13%      |
| DeepSeek V3 (03-24)              | DeepSeekV3_0324           | 2025-03-27     | v2        | 89.64%           | 89.14%          | 86.35%        | 90.63%  | 88.94%      |
| gpt-oss-20b                      | GPT_OSS_20B               | 2025-08-21     | v2        | 86.71%           | 93.31%          | 92.14%        | 81.25%  | 88.35%      |
| ChatGPT-4o                       | ChatGPT4o                 | 2025-03-20     | v2        | 86.61%           | 86.11%          | 87.32%        | 93.75%  | 88.45%      |
| DeepSeek R1 (05-28)              | DeepSeekR1_0528           | 2025-05-30     | v2        | 81.00%           | 92.91%          | 87.15%        | 90.63%  | 87.92%      |
| GPT-4.5 preview                  | GPT45_0227                | 2025-03-20     | v2        | 73.25%           | 86.28%          | 82.50%        | 90.63%  | 83.16%      |
| DeepSeek R1                      | DeepSeekR1                | 2025-03-20     | v2        | 79.30%           | 84.09%          | 80.69%        | 78.13%  | 80.55%      |
| Llama 4 Maverick                 | Llama_4_Maverick          | 2025-04-07     | v2        | 69.20%           | 75.98%          | 67.28%        | 84.38%  | 74.21%      |
| GPT-4.1 nano (04-14)             | GPT41nano_0414            | 2025-04-25     | v2        | 81.57%           | 83.61%          | 73.42%        | 46.88%  | 71.37%      |
| Amazon Nova Premier              | AmazonNovaPremier         | 2025-05-16     | v2        | 49.38%           | 68.34%          | 72.33%        | 65.63%  | 63.92%      |
| Amazon Nova Pro                  | AmazonNovaPro             | 2025-03-28     | v2        | 53.43%           | 71.30%          | 67.18%        | 56.25%  | 62.04%      |
| Gemma 3 27B                      | Gemma_3_27B               | 2025-06-09     | v2        | 63.20%           | 64.80%          | 64.21%        | 43.75%  | 58.99%      |
| Gemma 3 12B Q4                   | Gemma_3_12B               | 2025-04-25     | v2        | 56.75%           | 73.94%          | 81.86%        | 0.00%   | 53.14%      |
| Phi 4 14.7B                      | Phi_4                     | 2025-06-09     | v2        | 55.79%           | 68.35%          | 72.19%        | 0.00%   | 49.08%      |
| Gemma 3 4B                       | Gemma_3_4B                | 2025-04-25     | v2        | 29.16%           | 47.85%          | 62.94%        | 0.00%   | 34.99%      |
| Gemma 3 1B                       | Gemma_3_1B                | 2025-04-25     | v2        | 16.46%           | 28.01%          | 35.43%        | 0.00%   | 19.98%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT5_0807                 | 4.000        | 4.000            | 146.64   | 6102.00   | 41.61             | 1.0000  |
| Codex_Mini_Latest         | 4.000        | 3.980            | 96.83    | 12858.29  | 132.80            | 0.9975  |
| Gemini_25_Flash_0520      | 3.956        | 4.000            | 70.52    | 14528.43  | 206.03            | 0.9945  |
| Gemini_25_Pro_0506        | 3.813        | 4.000            | 178.93   | 17993.14  | 100.56            | 0.9766  |
| Grok_Code_0825            | 3.827        | 3.969            | 30.26    | 6956.86   | 229.87            | 0.9745  |
| Claude_Sonnet_4           | 3.780        | 4.000            | 62.45    | 6487.43   | 103.88            | 0.9725  |
| GPT41mini_0414            | 4.000        | 3.780            | 79.04    | 4289.14   | 54.27             | 0.9725  |
| Gemini_25_Pro_0605        | 3.877        | 3.860            | 91.17    | 9343.57   | 102.49            | 0.9671  |
| Grok4_0709                | 3.736        | 4.000            | 210.23   | 8793.29   | 41.83             | 0.9670  |
| Claude_Opus_4_Thinking    | 3.747        | 3.929            | 62.26    | 6234.14   | 100.13            | 0.9595  |
| GPT_OSS_120B              | 3.851        | 3.746            | 4.11     | 5208.57   | 1267.29           | 0.9496  |
| Claude_Opus_41            | 3.796        | 3.789            | 123.40   | 7164.14   | 58.06             | 0.9480  |
| OpenAi_o3_pro_0610        | 3.930        | 3.651            | 318.91   | 4996.14   | 15.67             | 0.9477  |
| Claude_Sonnet_37          | 3.781        | 3.786            | 73.37    | 6240.14   | 85.05             | 0.9459  |
| Grok3mini_beta            | 3.767        | 3.769            | 94.12    | 14279.71  | 151.72            | 0.9420  |
| Claude_Sonnet_37_Thinking | 3.657        | 3.857            | 145.33   | 12453.29  | 85.69             | 0.9393  |
| Claude_Sonnet_4_Thinking  | 3.804        | 3.691            | 77.92    | 7311.00   | 93.83             | 0.9370  |
| Grok3_beta                | 3.829        | 3.666            | 41.70    | 3807.71   | 91.30             | 0.9368  |
| GPT41_0414                | 3.780        | 3.666            | 80.39    | 4010.86   | 49.89             | 0.9307  |
| OpenAi_o3_0416            | 3.850        | 3.587            | 34.39    | 5222.71   | 151.85            | 0.9296  |
| OpenAi_o4_mini_0416       | 3.853        | 3.510            | 104.89   | 9954.29   | 94.90             | 0.9204  |
| OpenAi_o3_mini_0131       | 3.674        | 3.687            | 47.52    | 5598.00   | 117.80            | 0.9202  |
| OpenAi_o1_1217            | 3.670        | 3.559            | 89.62    | 5107.86   | 56.99             | 0.9036  |
| DeepSeekV3_0324           | 3.491        | 3.680            | 123.30   | 4374.71   | 35.48             | 0.8964  |
| GPT_OSS_20B               | 3.891        | 3.046            | 165.05   | 3838.14   | 23.25             | 0.8671  |
| ChatGPT4o                 | 3.449        | 3.480            | 19.00    | 2738.00   | 144.11            | 0.8661  |
| GPT41nano_0414            | 3.347        | 3.179            | 12.00    | 2607.57   | 217.32            | 0.8157  |
| DeepSeekR1_0528           | 3.137        | 3.343            | 74.66    | 9626.57   | 128.94            | 0.8100  |
| DeepSeekR1                | 3.356        | 2.989            | 65.33    | 4757.00   | 72.82             | 0.7930  |
| GPT45_0227                | 3.364        | 2.496            | 183.17   | 1757.86   | 9.60              | 0.7325  |
| Llama_4_Maverick          | 3.116        | 2.420            | 22.70    | 2379.86   | 104.82            | 0.6920  |
| Gemma_3_27B               | 2.894        | 2.161            | 47.94    | 2564.57   | 53.50             | 0.6320  |
| Gemma_3_12B               | 2.539        | 2.001            | 109.35   | 2291.86   | 20.96             | 0.5675  |
| Phi_4                     | 2.787        | 1.676            | 21.28    | 1730.86   | 81.34             | 0.5579  |
| AmazonNovaPro             | 2.551        | 1.723            | 24.82    | 2084.57   | 83.99             | 0.5343  |
| AmazonNovaPremier         | 2.781        | 1.169            | 30.56    | 1611.00   | 52.72             | 0.4938  |
| Gemma_3_4B                | 1.454        | 0.879            | 67.32    | 1868.14   | 27.75             | 0.2916  |
| Gemma_3_1B                | 0.524        | 0.793            | 22.52    | 1921.00   | 85.29             | 0.1646  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| Claude_Sonnet_4           | 4.000        | 3.999            | 74.60    | 7666.38   | 102.77            | 0.9998  |
| Claude_Opus_4_Thinking    | 4.000        | 3.998            | 83.54    | 8146.50   | 97.51             | 0.9997  |
| Gemini_25_Flash_0520      | 4.000        | 3.951            | 61.85    | 14090.13  | 227.83            | 0.9939  |
| Claude_Opus_41            | 4.000        | 3.943            | 147.37   | 8706.63   | 59.08             | 0.9928  |
| Claude_Sonnet_4_Thinking  | 4.000        | 3.938            | 95.05    | 8769.75   | 92.27             | 0.9922  |
| GPT5_0807                 | 4.000        | 3.938            | 146.57   | 5349.50   | 36.50             | 0.9922  |
| Gemini_25_Pro_0506        | 4.000        | 3.899            | 169.92   | 16239.75  | 95.58             | 0.9873  |
| Grok_Code_0825            | 4.000        | 3.884            | 15.56    | 3464.13   | 222.65            | 0.9855  |
| Claude_Sonnet_37_Thinking | 3.944        | 3.939            | 125.64   | 10304.25  | 82.01             | 0.9853  |
| GPT41mini_0414            | 4.000        | 3.873            | 41.27    | 3135.75   | 75.99             | 0.9841  |
| Grok3mini_beta            | 4.000        | 3.823            | 62.36    | 9035.00   | 144.88            | 0.9778  |
| GPT_OSS_120B              | 3.873        | 3.938            | 3.64     | 4122.63   | 1133.37           | 0.9763  |
| Grok4_0709                | 4.000        | 3.760            | 100.87   | 4025.00   | 39.90             | 0.9700  |
| Claude_Sonnet_37          | 3.886        | 3.873            | 66.44    | 5169.75   | 77.81             | 0.9698  |
| GPT41_0414                | 4.000        | 3.706            | 53.87    | 2854.88   | 53.00             | 0.9633  |
| Gemini_25_Pro_0605        | 3.880        | 3.723            | 72.91    | 7154.38   | 98.12             | 0.9503  |
| Codex_Mini_Latest         | 4.000        | 3.564            | 35.93    | 5345.88   | 148.77            | 0.9455  |
| OpenAi_o3_pro_0610        | 3.985        | 3.568            | 291.89   | 4044.00   | 13.85             | 0.9441  |
| OpenAi_o4_mini_0416       | 3.874        | 3.633            | 62.88    | 7136.38   | 113.49            | 0.9383  |
| GPT_OSS_20B               | 4.000        | 3.465            | 142.89   | 2735.00   | 19.14             | 0.9331  |
| OpenAi_o3_0416            | 4.000        | 3.450            | 35.84    | 4502.13   | 125.61            | 0.9313  |
| DeepSeekR1_0528           | 4.000        | 3.433            | 26.29    | 3114.50   | 118.47            | 0.9291  |
| Grok3_beta                | 3.861        | 3.520            | 30.55    | 2493.00   | 81.61             | 0.9227  |
| OpenAi_o3_mini_0131       | 3.938        | 3.438            | 28.29    | 3471.13   | 122.70            | 0.9219  |
| DeepSeekV3_0324           | 3.883        | 3.249            | 63.38    | 2316.63   | 36.55             | 0.8914  |
| OpenAi_o1_1217            | 4.000        | 3.043            | 61.21    | 3280.38   | 53.59             | 0.8803  |
| GPT45_0227                | 4.000        | 2.903            | 184.73   | 1449.38   | 7.85              | 0.8628  |
| ChatGPT4o                 | 3.813        | 3.076            | 15.01    | 1850.50   | 123.33            | 0.8611  |
| DeepSeekR1                | 3.634        | 3.094            | 73.97    | 4766.50   | 64.44             | 0.8409  |
| GPT41nano_0414            | 3.806        | 2.883            | 7.67     | 1752.13   | 228.59            | 0.8361  |
| Llama_4_Maverick          | 3.511        | 2.568            | 14.03    | 1470.75   | 104.86            | 0.7598  |
| Gemma_3_12B               | 3.426        | 2.490            | 93.15    | 1890.89   | 20.30             | 0.7394  |
| AmazonNovaPro             | 3.273        | 2.431            | 19.28    | 1477.38   | 76.63             | 0.7130  |
| Phi_4                     | 3.154        | 2.313            | 13.05    | 1037.89   | 79.55             | 0.6835  |
| AmazonNovaPremier         | 3.405        | 2.063            | 24.51    | 1161.50   | 47.38             | 0.6834  |
| Gemma_3_27B               | 2.891        | 2.293            | 31.75    | 1693.25   | 53.33             | 0.6480  |
| Gemma_3_4B                | 2.132        | 1.696            | 59.75    | 1644.22   | 27.52             | 0.4785  |
| Gemma_3_1B                | 1.383        | 0.858            | 18.17    | 1530.89   | 84.25             | 0.2801  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                     | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|---------------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT5_0807                 | 4.000        | 3.889            | 94.21    | 4474.22   | 47.49             | 0.9861  |
| Gemini_25_Flash_0520      | 3.920        | 3.896            | 53.74    | 10235.89  | 190.48            | 0.9769  |
| GPT_OSS_120B              | 4.000        | 3.752            | 3.78     | 3966.33   | 1049.60           | 0.9690  |
| OpenAi_o3_0416            | 3.997        | 3.738            | 28.42    | 3088.44   | 108.65            | 0.9668  |
| Grok_Code_0825            | 3.938        | 3.788            | 19.89    | 3178.89   | 159.80            | 0.9657  |
| Gemini_25_Pro_0506        | 3.988        | 3.693            | 96.79    | 8700.89   | 89.90             | 0.9601  |
| Grok4_0709                | 3.987        | 3.682            | 68.95    | 3121.89   | 45.28             | 0.9586  |
| Codex_Mini_Latest         | 3.982        | 3.623            | 27.95    | 4037.11   | 144.46            | 0.9507  |
| OpenAi_o4_mini_0416       | 3.931        | 3.586            | 34.76    | 3856.33   | 110.93            | 0.9396  |
| OpenAi_o3_pro_0610        | 3.891        | 3.621            | 228.07   | 2747.11   | 12.04             | 0.9390  |
| Claude_Opus_41            | 3.876        | 3.590            | 58.48    | 2535.33   | 43.35             | 0.9332  |
| Claude_Sonnet_4_Thinking  | 3.919        | 3.506            | 44.74    | 2940.56   | 65.72             | 0.9281  |
| Gemini_25_Pro_0605        | 3.929        | 3.489            | 68.36    | 5983.67   | 87.53             | 0.9272  |
| Claude_Sonnet_37          | 3.788        | 3.629            | 47.84    | 3062.89   | 64.03             | 0.9271  |
| Grok3mini_beta            | 3.891        | 3.512            | 31.73    | 5312.89   | 167.45            | 0.9254  |
| GPT_OSS_20B               | 3.869        | 3.502            | 94.35    | 2259.78   | 23.95             | 0.9214  |
| Claude_Sonnet_4           | 3.873        | 3.394            | 32.49    | 2363.22   | 72.74             | 0.9085  |
| OpenAi_o3_mini_0131       | 3.824        | 3.378            | 25.42    | 2827.56   | 111.21            | 0.9003  |
| Claude_Sonnet_37_Thinking | 3.724        | 3.320            | 56.33    | 3432.78   | 60.94             | 0.8806  |
| Claude_Opus_4_Thinking    | 3.572        | 3.458            | 44.15    | 2832.22   | 64.15             | 0.8788  |
| ChatGPT4o                 | 3.653        | 3.332            | 15.40    | 1615.11   | 104.86            | 0.8732  |
| DeepSeekR1_0528           | 3.693        | 3.279            | 51.27    | 4393.11   | 85.69             | 0.8715  |
| GPT41mini_0414            | 3.810        | 3.143            | 40.93    | 2371.33   | 57.94             | 0.8692  |
| DeepSeekV3_0324           | 3.483        | 3.424            | 38.76    | 1295.00   | 33.41             | 0.8635  |
| Grok3_beta                | 3.626        | 3.236            | 32.77    | 2325.89   | 70.98             | 0.8576  |
| GPT41_0414                | 3.547        | 3.226            | 52.29    | 2180.67   | 41.71             | 0.8465  |
| GPT45_0227                | 3.461        | 3.139            | 183.29   | 1554.89   | 8.48              | 0.8250  |
| Gemma_3_12B               | 3.436        | 3.113            | 92.50    | 1903.67   | 20.58             | 0.8186  |
| OpenAi_o1_1217            | 3.473        | 3.027            | 56.48    | 2921.22   | 51.73             | 0.8125  |
| DeepSeekR1                | 3.420        | 3.036            | 25.56    | 1817.11   | 71.09             | 0.8069  |
| GPT41nano_0414            | 3.301        | 2.572            | 9.45     | 1641.44   | 173.70            | 0.7342  |
| AmazonNovaPremier         | 3.198        | 2.589            | 20.33    | 925.22    | 45.51             | 0.7233  |
| Phi_4                     | 3.292        | 2.483            | 14.98    | 1195.11   | 79.78             | 0.7219  |
| Llama_4_Maverick          | 2.897        | 2.486            | 13.09    | 1302.11   | 99.47             | 0.6728  |
| AmazonNovaPro             | 3.101        | 2.273            | 15.37    | 1278.56   | 83.21             | 0.6718  |
| Gemma_3_27B               | 2.942        | 2.194            | 46.78    | 1603.00   | 34.26             | 0.6421  |
| Gemma_3_4B                | 2.734        | 2.301            | 47.13    | 1302.33   | 27.63             | 0.6294  |
| Gemma_3_1B                | 1.177        | 1.658            | 21.09    | 1791.00   | 84.91             | 0.3543  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                     | Avg Accuracy | Avg Completeness | Score ↓ |
|---------------------------|--------------|------------------|---------|
| GPT5_0807                 | 4            | 4                | 1       |
| Gemini_25_Flash_0520      | 4            | 4                | 1       |
| Grok_Code_0825            | 4            | 4                | 1       |
| Codex_Mini_Latest         | 4            | 4                | 1       |
| Gemini_25_Pro_0506        | 4            | 4                | 1       |
| Gemini_25_Pro_0605        | 4            | 4                | 1       |
| Claude_Sonnet_4           | 4            | 4                | 1       |
| Claude_Opus_41            | 4            | 4                | 1       |
| Claude_Sonnet_4_Thinking  | 4            | 4                | 1       |
| Claude_Opus_4_Thinking    | 4            | 4                | 1       |
| OpenAi_o3_pro_0610        | 4            | 4                | 1       |
| OpenAi_o3_0416            | 4            | 4                | 1       |
| Claude_Sonnet_37          | 4            | 4                | 1       |
| OpenAi_o4_mini_0416       | 4            | 4                | 1       |
| Claude_Sonnet_37_Thinking | 4            | 4                | 1       |
| GPT41_0414                | 4            | 4                | 1       |
| Grok4_0709                | 4            | 4                | 1       |
| Grok3_beta                | 4            | 4                | 1       |
| OpenAi_o3_mini_0131       | 4            | 4                | 1       |
| OpenAi_o1_1217            | 4            | 3.75             | 0.96875 |
| Grok3mini_beta            | 3.75         | 4                | 0.96875 |
| GPT_OSS_120B              | 4            | 3.5              | 0.9375  |
| ChatGPT4o                 | 3.5          | 4                | 0.9375  |
| GPT41mini_0414            | 3.75         | 3.75             | 0.9375  |
| DeepSeekR1_0528           | 2.25         | 2.25             | 0.90625 |
| GPT45_0227                | 3.5          | 3.75             | 0.90625 |
| DeepSeekV3_0324           | 3.5          | 3.75             | 0.90625 |
| Llama_4_Maverick          | 3.5          | 3.25             | 0.84375 |
| GPT_OSS_20B               | 3.5          | 3.0              | 0.8125  |
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

- **OpenAI dominates** with GPT-5 (08-07) (99.46%) leading the benchmark with perfect 100% code translation score and excellent overall performance ($1.36 total cost)
- **Google maintains strong second position** with Gemini 2.5 Flash Preview (05-20) (99.13%) offering exceptional speed (208.25 tokens/sec) and cost-effectiveness ($1.09 total)
- **xAI demonstrates strong model portfolio** with Grok Code Fast achieving third place (98.14%) through exceptional speed (203.78 tokens/sec) and outstanding cost efficiency ($0.17), while Grok 4
  provides higher-end performance (97.39%) with balanced capabilities though slower generation speed (42.03 tokens/sec) limits interactive use
- **Specialized coding models excel**: Codex Mini Latest (97.34%) shows highest accuracy (3.993) but has refusal behaviors; newer Gemini 2.5 Pro versions show performance regression
- **Claude 4 Sonnet outperforms Thinking mode** (97.02% vs 96.43%), suggesting reasoning mode doesn't always improve coding tasks
- **Speed champions**: gpt-oss-120b achieves fastest generation (1,144.30 tokens/sec) and execution (1.53 min)

**Key Performance Insights:**

- **Category leaders**: GPT-5 (08-07) leads code translation (100.00%) and documentation (98.61%), Claude 4 Sonnet dominates generation (99.98%)
- **Cost-effectiveness winners**: Grok Code Fast (98.14% for $0.17), Grok 3 mini beta (95.35% for $0.13), GPT-4.1 nano (71.37% for $0.02)
- **Perfect LCIF scores**: 14 models achieve 100% in large context instruction following, showing maturity in handling complex tasks
- **Speed vs capability trade-offs**: OpenAI o3-pro (95.77%) demonstrates strong capabilities but at impractical speeds (13.90 tokens/sec, 110.34 min execution) and high cost ($8.97), similar to
  GPT-4.5's performance profile, making it unsuitable for interactive coding workflows despite its technical merits
- **Open-source breakthrough**: gpt-oss-20b (88.35%) represents a significant milestone as the first open-source model under 30B parameters to exceed 85%, demonstrating that smaller models can deliver
  competitive performance for local deployment while maintaining cost efficiency and privacy benefits
- **Open-source landscape**: Microsoft's Phi-4 (49.08%) shows competitive mid-range performance, while Google's Gemma 3 family offers scalable options from 1B (19.98%) to 27B (58.99%) parameters.
  However, most open-source models struggle with LCIF tasks, indicating limitations in complex instruction following

**Market Implications:**

- **Intense competition drives innovation** across Google, Anthropic, OpenAI, xAI, and Meta
- **Price-performance optimization**: Models like Grok 3 mini beta offer exceptional value, while premium models like Claude 4 Opus provide top-tier capabilities at higher cost
- **Specialized vs general trade-offs**: Thinking modes show mixed results; speed-optimized models often match quality while reducing costs
- **Enterprise options expand**: From ultra-low-cost Llama 4 Maverick to premium Claude 4 Opus, organizations have diverse deployment choices including self-hosted open-source alternatives

The rapid evolution demonstrates that model selection should prioritize specific use cases rather than assuming latest means best—with clear winners emerging in speed (gpt-oss-120b), value (Grok 3
mini beta), overall performance (GPT-5), specialized coding (Codex Mini Latest), and **local deployment breakthrough** (gpt-oss-20b).

**Notable Achievement: gpt-oss-20b** stands out as a landmark achievement in the open-source landscape, being the first model under 30B parameters to cross the 85% threshold with its 88.35% score. Its
balanced performance across categories (86.71% code translation, 93.31% code generation, 92.14% code documentation) demonstrates remarkable capability for a model of its size. Tested locally on a
MacBook Pro M4 Pro, it achieved practical speeds (21.95 tokens/sec average, 55 tokens/sec peak), proving that high-quality software engineering assistance can be deployed entirely within
organizational infrastructure—offering unprecedented privacy, control, and cost optimization for enterprises seeking to maintain sensitive code and data on-premises.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>