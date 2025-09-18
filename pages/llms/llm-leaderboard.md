# LLMs Leaderboard (Benchmark v3, last update 2025-09-18)

> 📊 **Interactive Leaderboard**: View live results with charts at Our [LLM Leaderboard](https://epam.github.io/AIRUN-Engineering-Benchmark)

## Coding Leaderboard Rating
![llm-rating.png](/images/llms/coding/llm-score.png)

### Multimodal Leaderboard Rating
![llm-rating.png](/images/llms/multimodal/llm-score.png)

## Introduction to EPAM AI/RUN LLMs Engineering Benchmark

This page presents the results of LLMs engineering benchmark v3 including a leaderboard that compares the effectiveness of Anthropic, Amazon, Google DeepMind, Meta, xAI, OpenAI, and other companies'
LLMs (Large Language Models) and SMLs (Small Language Models) in executing both coding and multimodal tasks, including code translation, code generation, documentation generation, large context
instruction following (LCIF), and multimodal reasoning.

This leaderboard will be updated regularly to reflect the latest developments in the field of large language models.


> Previous results for benchmark v1 were moved to [llm-leaderboard-v1.md](benchmark_v1/llm-leaderboard_v1.md) for reference.<br />
> Benchmark v2 results moved to [llm-leaderboard-v2.md](benchmark_v2/llm-leaderboard_v2.md)

## Benchmark Key Findings

General insights:

**Coding Benchmark Leaders:**
- GPT-5 (08-07) dominates the coding benchmark with 82.13% total score, achieving exceptional code translation performance (84.79%) and strong code generation (78.92%)
- Claude 4 Sonnet secures second place with 75.68% score, outperforming its Thinking mode variant (73.73%), demonstrating that reasoning modes don't always improve coding performance
- Grok 4 (07-09) achieves 73.33% score with balanced capabilities, while Grok Code Fast delivers 71.74% with exceptional speed (165.54 tokens/sec) and outstanding cost efficiency ($0.33)
- gpt-oss-120b represents a breakthrough for open-source models at 62.19% score with extraordinary speed (555.99 tokens/sec) and ultra-low cost ($0.23)
- Amazon Nova Premier struggles significantly in coding tasks (26.89% score), indicating limitations for software engineering applications

**Multimodal Benchmark Leaders:**
- GPT-5 (08-07) maintains leadership with 81.56% score, demonstrating consistent excellence across both coding and multimodal domains
- Gemini 2.5 Flash achieves 80.50% score with impressive speed (127.87 tokens/sec) and cost efficiency ($0.42), making it the top choice for multimodal tasks
- Gemini 2.5 Pro scores 78.83% with strong performance and reasonable cost ($1.85), showing Google's strength in multimodal reasoning
- Claude 4 Sonnet (Thinking) improves to 60.69% vs. 56.68% for base model, showing reasoning mode benefits in multimodal contexts
- Grok 4 significantly underperforms in multimodal tasks (43.78% vs. 73.33% in coding), indicating specialization limitations

Performance metrics highlights:

**Coding Benchmark:**
- **Fastest token generation**: gpt-oss-120b (555.99 T/S), Grok Code Fast (165.54 T/S), Gemini 2.5 Flash (166.51 T/S)
- **Shortest execution time**: gpt-oss-120b (6.71 min), Grok Code Fast (17.66 min), Claude 4 Sonnet (64.24 min)
- **Most tokens generated**: Gemini 2.5 Flash (698,984 tokens), Gemini 2.5 Pro (410,997 tokens), Claude 4 Sonnet (331,188 tokens)
- **Best cost-effectiveness**: gpt-oss-120b ($0.23), Grok Code Fast ($0.33), Amazon Nova Premier ($1.12)

**Multimodal Benchmark:**
- **Fastest token generation**: Gemini 2.5 Flash (127.87 T/S), Gemini 2.5 Pro (77.01 T/S), Claude 4 Sonnet (Thinking) (43.96 T/S)
- **Shortest execution time**: Claude 4 Sonnet (10.83 min), Gemini 2.5 Flash (11.51 min), Amazon Nova Premier (14.85 min)
- **Best cost-effectiveness**: Gemini 2.5 Flash ($0.42), GPT-5 ($1.19), Gemini 2.5 Pro ($1.85)

Best results by category:

**Coding Benchmark:**
- **Code Translation**: GPT-5 (08-07) (84.79%), Claude 4 Sonnet (79.08%), Gemini 2.5 Pro (78.38%)
- **Code Generation**: GPT-5 (08-07) (78.92%), Claude 4 Sonnet (74.65%), Claude 4 Sonnet (Thinking) (72.81%)
- **Code Documentation**: GPT-5 (08-07) (79.81%), gpt-oss-120b (67.86%), Grok 4 (64.94%)
- **LCIF**: Grok Code Fast (98.50%), Claude 4 models (96.25%), Grok 4 (92.50%)

**Multimodal Benchmark:**
- **Overall Multimodal Performance**: GPT-5 (81.56%), Gemini 2.5 Flash (80.50%), Gemini 2.5 Pro (78.83%)

## Additional Views

<details>
<summary>Other metrics from coding leaderboard</summary>

![llm-type.png](/images/llms/coding/llm-reasoning.png)
![llm-type.png](/images/llms/coding/llm-license.png)
![llm-price.png](/images/llms/coding/llm-price.png)
![llm-tokens.png](/images/llms/coding/llm-tokens.png)
![llm-cost.png](/images/llms/coding/llm-cost.png)
![llm-time.png](/images/llms/coding/llm-time.png)
![llm-speed.png](/images/llms/coding/llm-speed.png)

</details>

<details>
<summary>Other metrics from multimodal leaderboard</summary>

![llm-type.png](/images/llms/multimodal/llm-reasoning.png)
![llm-type.png](/images/llms/multimodal/llm-license.png)
![llm-price.png](/images/llms/multimodal/llm-price.png)
![llm-tokens.png](/images/llms/multimodal/llm-tokens.png)
![llm-cost.png](/images/llms/multimodal/llm-cost.png)
![llm-time.png](/images/llms/multimodal/llm-time.png)
![llm-speed.png](/images/llms/multimodal/llm-speed.png)

</details>

### Observations

**Cross-Domain Performance Analysis**
The benchmark v3 results reveal fascinating insights about model specialization and generalization. GPT-5 demonstrates remarkable consistency across both domains, maintaining leadership in coding (82.13%) and multimodal (81.56%) tasks. This consistency suggests superior general intelligence and robust training across diverse data types.

**Google's Multimodal Advantage**
While Google's Gemini models underperform in pure coding tasks (Gemini 2.5 Pro: 65.67%, Flash: 60.46%), they excel in multimodal scenarios (Pro: 78.83%, Flash: 80.50%). Gemini 2.5 Flash emerges as the top choice for multimodal applications, combining strong performance with exceptional speed and cost efficiency.

**Anthropic's Reasoning Mode Paradox**
Claude models reveal an interesting pattern: reasoning mode hurts coding performance (base: 75.68% vs. thinking: 73.73%) but improves multimodal capabilities (base: 56.68% vs. thinking: 60.69%). This suggests reasoning mode benefits complex visual understanding but may overcomplicate straightforward coding tasks.

**xAI's Domain Specialization**
Grok models show dramatic performance variation across domains. Grok 4 performs competitively in coding (73.33%) but struggles significantly in multimodal tasks (43.78%), indicating strong specialization in text-based programming tasks. Grok Code Fast's exceptional LCIF performance (98.50%) demonstrates superior instruction-following capabilities.

**Open-Source Breakthrough in Coding**
gpt-oss-120b achieves remarkable coding performance (62.19%) with unprecedented speed (555.99 T/S) and minimal cost ($0.23), making it a game-changer for organizations seeking cost-effective coding assistance. However, this model wasn't evaluated in multimodal tasks, limiting its applicability scope.

**Enterprise Deployment Considerations**
For organizations choosing models, domain requirements significantly impact optimal selection:
- **Pure Coding Tasks**: GPT-5 for maximum quality, Grok Code Fast for speed/cost, gpt-oss-120b for open-source
- **Multimodal Applications**: Gemini 2.5 Flash for balanced performance, GPT-5 for premium quality
- **Mixed Workloads**: GPT-5 offers the best cross-domain consistency, making it ideal for diverse AI applications

### Detailed Results

All categories, except Large Context Instructions Following (LCIF), are evaluated automatically using the Large Language Model<sup>1</sup>.
You can read [llm-comparison-report.md](llm-comparison-report.md) for detailed coding benchmark analysis and [llm-comparison-report-multimodal.md](llm-comparison-report-multimodal.md) for multimodal benchmark results. These reports include all experiment scores, performance breakdowns by category, and comprehensive analysis.

The tables below provide an overview of both coding and multimodal benchmark experiments. For coding tasks, you can review the average accuracy and completeness across all categories, total execution time,
generation token speed (token per second), the total number of input and output tokens, the cost of the experiment, and the final score. The multimodal benchmark focuses on visual reasoning and multimodal instruction following capabilities.

<details>
<summary>Detailed Results and Observations</summary>

### Coding Benchmark Results

| Name                       | Reasoning | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total output | Cost $ | Total Score |
|----------------------------|-----------|----------|--------------|------------------|-------------|-------------|--------------|--------|-------------|
| GPT-5 (08-07)              | Yes (low) | 0.800    | 0.818        | 92.53            | 53.94       | 314949      | 299430       | 3.39   | 82.13%      |
| Claude 4 Sonnet            | No        | 0.652    | 0.683        | 64.24            | 85.92       | 399848      | 331188       | 6.17   | 75.68%      |
| Claude 4 Sonnet (Thinking) | Yes       | 0.638    | 0.654        | 64.01            | 82.58       | 401095      | 317158       | 5.96   | 73.73%      |
| Grok 4 (07-09)             | Yes       | 0.680    | 0.652        | 80.75            | 46.27       | 339997      | 224156       | 4.38   | 73.33%      |
| Grok Code Fast             | Yes       | 0.645    | 0.603        | 17.66            | 165.54      | 319314      | 175420       | 0.33   | 71.74%      |
| Gemini 2.5 Pro             | Yes       | 0.594    | 0.609        | 63.77            | 107.42      | 374686      | 410997       | 4.58   | 65.67%      |
| gpt-oss-120b               | Yes (low) | 0.709    | 0.720        | 6.71             | 555.99      | 316966      | 223941       | 0.23   | 62.19%      |
| Gemini 2.5 Flash           | Yes       | 0.633    | 0.675        | 69.96            | 166.51      | 339193      | 698984       | 2.50   | 60.46%      |
| Amazon Nova Premier        | No        | 0.282    | 0.205        | 15.88            | 46.56       | 224223      | 44360        | 1.12   | 26.89%      |

_Table 1. Overview of the coding benchmark results._

### Multimodal Benchmark Results

| Name                       | Reasoning | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total output | Cost $ | Total Score |
|----------------------------|-----------|----------|--------------|------------------|-------------|-------------|--------------|--------|-------------|
| GPT-5 (08-07)              | Yes (low) | 0.796    | 0.992        | 17.311           | 41.09       | 613046      | 42680        | 1.19   | 81.56%      |
| Gemini 2.5 Flash           | Yes       | 0.790    | 0.940        | 11.509           | 127.87      | 718866      | 88295        | 0.42   | 80.50%      |
| Gemini 2.5 Pro             | Yes       | 0.769    | 0.962        | 20.494           | 77.01       | 718866      | 94691        | 1.85   | 78.83%      |
| Claude 4 Sonnet (Thinking) | Yes       | 0.567    | 0.966        | 18.602           | 43.96       | 802110      | 49062        | 3.14   | 60.69%      |
| Claude 4 Sonnet            | No        | 0.523    | 0.961        | 10.832           | 28.56       | 801240      | 18563        | 2.68   | 56.68%      |
| Amazon Nova Premier        | No        | 0.489    | 0.928        | 14.849           | 16.78       | 767489      | 14954        | 2.11   | 53.29%      |
| Grok 4 (07-09)             | Yes       | 0.380    | 0.958        | 66.464           | 42.72       | 606242      | 170368       | 4.37   | 43.78%      |

_Table 2. Overview of the multimodal benchmark results._

> Additional info:  
> Evaluation of benchmark results were performed automatically with the help of evaluation tools based on the LLMs.
> Please refer to the page [LLMs Benchmark Approach](llm-approach.md) for more details on the evaluation methodology.

</details>

## Models specification

| LLM Name                                                                                                                                                 | API Provider used in benchmark                                                        | Context Window | Cost (Input / Output per MTok)                   | Max Output         | Knowledge Cutoff |
|----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|----------------|--------------------------------------------------|--------------------|------------------|
| [GPT-5 (08-07)](https://platform.openai.com/docs/models/gpt-5)                                                                                           | OpenAI                                                                                | 400K           | $1.25 / $10.00                                   | 128K               | Sep 30, 2024     |
| [Claude 4 Sonnet](https://www.anthropic.com/news/claude-4)                                                                                               | Google Vertex AI                                                                      | 200K           | $3.00 / $15.00                                   | 64K                | Mar, 2025        |
| [Grok 4 (07-09)](https://docs.x.ai/docs/models/grok-4-0709)                                                                                              | xAI Console                                                                           | 256K           | $3.00 / $15.00 <= 128K and $6.00 / $30.00 > 128K | N/A                | N/A              |
| [Grok Code Fast](https://x.ai/news/grok-code-fast-1)                                                                                                     | xAI                                                                                   | 256K           | $0.20 / $1.50                                    | N/A                | N/A              |
| [Gemini 2.5 Pro](https://ai.google.dev/gemini-api/docs/models#gemini-2.5-pro)                                                                            | Google AI Studio                                                                      | 1M             | $1.25 / $10.00 <= 200K<br>$2.50 / $15.00 > 200K  | 65K                | Jan, 2025        |
| [gpt-oss-120b](https://platform.openai.com/docs/models/gpt-oss-120b)                                                                                     | [Cerebras](https://www.cerebras.ai/blog/openai-gpt-oss-120b-runs-fastest-on-cerebras) | 131K           | $0.25 / $0.69                                    | 33K                | Jun 01, 2024     |
| [Gemini 2.5 Flash](https://ai.google.dev/gemini-api/docs/models#gemini-2.5-flash)                                                                        | Google AI Studio                                                                      | 1M             | $0.15 / $3.50                                    | 65K                | Jan, 2025        |
| [Amazon Nova Premier](https://aws.amazon.com/blogs/aws/amazon-nova-premier-our-most-capable-model-for-complex-tasks-and-teacher-for-model-distillation/) | AWS Bedrock                                                                           | 1M             | $2.5 / $12.5                                     | 10K                | N/A              |

_Table 3. Description of LLMs, their versions, amount of information to process, and the length of the response._

## Notes

- To learn more about our methodology for evaluating LLMs, please read [LLMs Benchmark Approach](llm-approach.md).
- To submit your model for evaluation, please refer to the [Large Language Model Benchmark Submission](submissions/llm-benchmark-submission.md) page.
- Previous charts with ratings and other scores can be found in the [LLMs Charts archive](/images/llms/llm-charts-archive).

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>