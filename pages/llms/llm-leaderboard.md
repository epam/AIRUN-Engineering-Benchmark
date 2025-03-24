# LLMs Leaderboard (Benchmark v2, last update 2025-03-21)

## Introduction

This page compares the effectiveness of Anthropic, Amazon, Google DeepMind, xAI, OpenAI, and other companies LLMs in executing software engineering tasks, including code translation, code
generation, documentation generation and large context instruction following (LCIF).

Our latest research and evaluations have revealed significant shifts in large language model performance. Leading our rankings is Claude 3.7 Sonnet with an impressive 91.9% total score, followed by
OpenAI's o3-mini model with 91.8%. These models demonstrate exceptional capabilities in software engineering tasks while maintaining efficient processing times and reasonable costs.

The third position is held by Gemini 2.0 Pro Experimental (0205) at 91.1%, demonstrating strong performance across evaluation categories. Following closely is Claude 3.7 Sonnet (Thinking) with 90.6%,
showcasing the benefits of Anthropic's thinking mode feature. The fifth place is secured by Gemini 2.0 Flash Thinking Experimental (0121) at 85.6%, which maintains competitive performance due to
offering very fast execution time.

OpenAI's GPT-4.5 preview shows only middle-range results (77.8%). It generates a very small amount of tokens (37,894) while having the highest cost ($75/$150) among all tested models. This makes it
currently less efficient than other models in our benchmark.

The current top of Large Language Models based on research, in order of Total Score, are:

1. Claude 3.7 Sonnet - 91.9%
2. OpenAI o3-mini (0131) - 91.8%
3. Gemini 2.0 Pro Experimental (0205) - 91.1%
4. Claude 3.7 Sonnet (Thinking) - 90.6%
5. Gemini 2.0 Flash Thinking Experimental (0121) - 85.6%

We are looking forward to evaluate new models such as OpenAI o1-Pro, Grok 3, Gemma 2 27B and others in the future.

You can read [llm-comparison-report.md](llm-comparison-report.md) for a detailed comparison of the models. The report includes all experiment scores, the performance of each model in different
categories, and the final scores.

## Final scores in EPAM's LLMs Benchmark

All categories, except Large Context Instructions Following (LCIF), are evaluated automatically using the Large Language Model<sup>1</sup>
You can read detailed reports on concrete model performance and the areas where each model excels
in [llm-detailed-result](llm-detailed-result).

The table below provides an overview of the experiment, encompassing three categories. Here, you can review the average accuracy and completeness across all categories, total execution time,
generation token speed (token per second), the total number of input and output tokens (for OpenAI o-series models, output tokens include reasoning tokens), the cost of the experiment, and finally,
the total score. The total score comprises the average score across all categories **including** LCIF experiment score.

| Model                                         | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total output | Cost ($) | Total Score |
|-----------------------------------------------|----------|--------------|------------------|-------------|-------------|--------------|----------|-------------|
| Claude 3.7 Sonnet                             | 3.819    | 3.756        | 24.60            | 76.31       | 100002      | 112605       | 1.99     | **91.9%**   |
| OpenAI o3-mini (0131)                         | 3.818    | 3.488        | 13.13            | 117.30      | 80551       | 92403        | 0.50     | 91.8%       |
| Gemini 2.0 Pro Experimental (0205)            | 3.828    | 3.794        | 30.78            | 64.89       | 92798       | 119842       | 0.00     | 91.1%       |
| Claude 3.7 Sonnet (Thinking)                  | 3.778    | 3.683        | 42.16            | 79.27       | 100711      | 200502       | 3.31     | 90.6%       |
| Gemini 2.0 Flash Thinking Experimental (0121) | 3.365    | 3.321        | 10.65            | 188.16      | 92785       | 120261       | 0.00     | 85.6%       |
| DeepSeek R1                                   | 3.473    | 3.041        | 21.32            | 68.63       | 82977       | 87785        | 0.95     | 77.9%       |
| GPT-4.5 preview                               | 3.613    | 2.873        | 73.49            | 8.59        | 80575       | 37894        | 11.73    | 77.8%       |

_Table 1. Overview of the experiment results._

> Additional info:  
> Evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the OpenAI o3-mini and Claude Sonnet 3.7 models.
> Please refer the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.


We have visualized some of the information for your review.

![llm-rating.png](/images/llms/llm-rating.png)
![llm-price.png](/images/llms/llm-price.png)
![llm-tokens.png](/images/llms/llm-tokens.png)
![llm-cost.png](/images/llms/llm-cost.png)
![llm-time.png](/images/llms/llm-time.png)
![llm-speed.png](/images/llms/llm-speed.png)

## Models specification

| LLM Name                                                                                                          | Description                                                                                                                                                                                                                                                                                                                                                                                                            | Context Window | Cost (Input / Output per MTok) | Max Output         | Training Data  |
|-------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------|--------------------------------|--------------------|----------------|
| [Claude 3.7 Sonnet](https://www.anthropic.com/news/claude-3-7-sonnet)                                             | Claude 3.7 Sonnet is the most recent model by Anthropic. It is the most intelligent model to date by Anthropic and the first hybrid reasoning model on the market. Claude 3.7 Sonnet shows particularly strong improvements in coding and front-end web development.<br>API Provider: Google Vertex AI, also available on Anthropic Platform and AWS Bedrock                                                           | 200K           | $3.00 / $15.00                 | 8K                 | Nov, 2024      |
| OpenAI o3-mini                                                                                                    | OpenAI o3-mini is first OpenAI small reasoning model that supports highly requested developer features including function calling, Structured Outputs, and developer messages, making it production-ready out of the gate.<br>API Provider: OpenAI, Azure                                                                                                                                                              | 200K           | $1.10 / $4.40                  | 100K               | Up to Oct 2023 |
| [Gemini 2.0 Pro Experimental (0205)](https://ai.google.dev/gemini-api/docs/models/experimental-models)            | New version of Gemini Pro series model by Google Deepmind<br>API Provider: Google AI Studio                                                                                                                                                                                                                                                                                                                            | 2M             | $0.00 / $0.00                  | 8K                 | Aug, 2024      |
| [Claude 3.7 Sonnet (Thinking mode)](https://www.anthropic.com/news/claude-3-7-sonnet)                             | Claude 3.7 Sonnet with enabled thinking mode with 20K output tokens and 8K budget for thinking.<br>API Provider: Google Vertex AI, also available on Anthropic Platform and AWS Bedrock                                                                                                                                                                                                                                | 200K           | $3.00 / $15.00                 | 64K (128K in beta) | Nov, 2024      |
| [Gemini 2.0 Flash Thinking Experimental (0121)](https://ai.google.dev/gemini-api/docs/models/experimental-models) | Latest (2.0) experimental Fast (Flash) Reasoning (Thinking) model by Google Deepmind<br>API Provider: Google AI Studio                                                                                                                                                                                                                                                                                                 | 1M             | $0.00 / $0.00                  | 64K                | Aug, 2024      |                 
| [DeepSeek R1](https://fireworks.ai/models/fireworks/deepseek-r1)                                                  | DeepSeek released R1, a reasoning model trained with initial supervised data followed by reinforcement learning. It matches OpenAI-o1's performance on math, code, and reasoning tasks. The models are open-sourced, with their 32B distilled version setting new records by outperforming OpenAI-o1-mini. <br>API Provider: DeepSeek platform (currently unavailable), Fireworks (used in benchmark), other providers | 64K            | $3.00 / $8.00                  | 8K                 | Up to Oct 2023 |
| [GPT-4.5 Preview](https://openai.com/index/introducing-gpt-4-5/)                                                  | Most expensive OpenAI model to date. "Early testing shows that interacting with GPT‑4.5 feels more natural. Its broader knowledge base, improved ability to follow user intent, and greater "EQ" make it useful for tasks like improving writing, programming, and solving practical problems. We also expect it to hallucinate less"<br>API Provider: OpenAI, Azure                                                   | 128K           | $75.00 / $150.00               | 16K                | Up to Oct 2023 |

_Table 2. Description of LLMs, their versions, amount of information to process, and the length of the response._

## Notes

- To learn more about our methodology for evaluating LLMs, please read [LLMs Benchmark Approach](llm-approach.md).
- To submit your model for evaluation, please refer to the [Large Language Model Benchmark Submission](submissions/llm-benchmark-submission.md) page.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>