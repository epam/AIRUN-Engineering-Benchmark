# LLMs Leaderboard (Benchmark v2, last update 2025-04-14)

## Introduction

This page compares the effectiveness of Anthropic, Amazon, Google DeepMind, Meta, xAI, OpenAI, and other companies' LLMs in executing software engineering tasks, including code translation, code
generation,
documentation generation, and large context instruction following (LCIF).

Our latest research and evaluations have revealed significant shifts in large language model performance. Leading our rankings is Gemini 2.5 Pro Experimental with an exceptional 93.3% total score,
showcasing Google's rapid advancement in LLM capabilities. Making a strong debut is xAI's Grok 3 mini beta in second place with an impressive 92.3% total score.

It's worth noting that Grok 3 mini beta achieved its high ranking largely due to its very fast token generation speed (152.47 tokens/second). In our methodology, we calculate speed by dividing the
total output tokens (including completion and reasoning tokens) by execution time. While Grok 3 mini generates tokens at a high rate, its total execution time of 24.05 minutes is nearly four times
longer than ChatGPT-4o's 6.53 minutes. This indicates that Grok 3 mini produces significantly more reasoning tokens during its process, trading raw execution speed for thoroughness in its approach.

An interesting and significant finding from our benchmark is that Grok 3 mini beta, which is a reasoning model, substantially outperformed the standard Grok 3 beta model (92.3% vs 89.4%), despite
being a "mini" version. This clearly demonstrates the substantial benefits of reasoning capabilities for software engineering tasks. The difference is particularly pronounced in code generation where
Grok 3 mini beta scored 92.95% compared to Grok 3 beta's 87.49%. This suggests that models with explicit reasoning mechanisms are better equipped to handle complex coding challenges.

Following closely is Claude 3.7 Sonnet with 91.4% total score, and OpenAI's o3-mini model with 90.8%. These models demonstrate exceptional capabilities in software engineering tasks while maintaining
efficient processing times and reasonable costs.

The fifth position is held by Gemini 2.0 Pro Experimental (0205) at 90.7%, demonstrating strong performance across evaluation categories. Following closely is Claude 3.7 Sonnet (Thinking) with 90.2%,
showcasing the benefits of Anthropic's thinking mode feature. xAI's flagship Grok 3 beta model achieves an impressive 89.4% total score, securing the seventh position. The eighth place is secured by
ChatGPT-4o at 87.8%, which offers an excellent balance of performance and speed.

OpenAI o1 (1217) at 84.5% and Gemini 2.0 Flash Thinking Experimental (0121) at 84.4% show similar performance, with Gemini Flash Thinking offering significantly faster execution time. DeepSeek's
open-source models have shown good capabilities, with the new V3 version (83.9%) outperforming R1 (77.1%). These models are particularly noteworthy as they can be self-hosted within organizations
seeking privacy, control, and cost optimization. This represents a significant advancement in the open-source LLM space.

Meta's Llama 4 Maverick achieves a competitive 74.5% total score. This model uses a sophisticated mixture-of-experts architecture with 400B total parameters but
only 17B active parameters at any given time (using 128 experts). This architecture reduces inference latency while maintaining computational efficiency, allowing it to deliver solid performance with
exceptional speed (103.2 tokens/sec) and very low cost ($0.05/$0.22 per MTok) at Fireworks.ai provider. This positions it as one of the most cost-effective options in our benchmark.

OpenAI's GPT-4.5 preview shows only middle-range results (77.6%). It generates a very small amount of tokens (37,894) while having the highest cost ($75/$150) among all tested models. This makes it
currently less efficient than other models in our benchmark.

Amazon Nova Pro, while scoring 61.8%, shows promise for enterprise applications. Given that it's a smaller model, its performance is noteworthy, and we anticipate significant improvements with the
upcoming Amazon Nova Premier model.

We have also evaluated OpenAI's newest o1-Pro model (released in March 2025). While this model shows promising capabilities, its extremely high cost ($150/$600 per 1M tokens) and extended processing
times make it impractical for standard benchmarking. Our initial tests revealed good accuracy but did not justify including it in our main leaderboard at this time. For detailed results of our o1-Pro
evaluation, please see our [dedicated report](llm-detailed-result/o1-pro-2025-03-25.md).

The current top of Large Language Models based on research, in order of Total Score, are:

1. Gemini 2.5 Pro Experimental (0325) - 93.3%
2. Grok 3 mini beta - 92.3%
3. Claude 3.7 Sonnet - 91.4%
4. OpenAI o3-mini (0131) - 90.8%
5. Gemini 2.0 Pro Experimental (0205) - 90.7%

For cost-effective options, Grok 3 mini beta (92.3% at $0.30/$0.50 per MTok) offers exceptional value with high speed, low cost, and strong performance specifically for software development tasks.
While Llama 4 Maverick (74.5% at $0.05/$0.22 per MTok) has lower costs, its strengths lie more in social networking applications rather than software development tasks.

We are looking forward to evaluating several upcoming models in the near future:

- Google's Gemma 3 27B (waiting for extended rate limits)
- OpenAI's o4-mini and o3 models
- Meta Llama 4 Behemoth
- Other models...

This leaderboard will be updated regularly to reflect the latest developments in the field of large language models.

You can read [llm-comparison-report.md](llm-comparison-report.md) for a detailed comparison of the models. The report includes all experiment scores, the performance of each model in different
categories, and the final scores.

> Previous benchmark v1 results were moved to [llm-leaderboard-v1.md](benchmark_v1/llm-leaderboard_v1.md) for reference.

## Final scores in EPAM's LLMs Benchmark

All categories, except Large Context Instructions Following (LCIF), are evaluated automatically using the Large Language Model<sup>1</sup>
You can read detailed reports on concrete model performance and the areas where each model excels in [llm-detailed-result](llm-detailed-result).

The table below provides an overview of the experiment, encompassing three categories. Here, you can review the average accuracy and completeness across all categories, total execution time,
generation token speed (token per second), the total number of input and output tokens (for OpenAI o-series models, output tokens include reasoning tokens), the cost of the experiment, and finally,
the total score. The total score comprises the average score across all categories **including** LCIF experiment score.

| Model                                          | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total output | Cost ($)         | Total Score |
|------------------------------------------------|----------|--------------|------------------|-------------|-------------|--------------|------------------|-------------|
| Gemini 2.5 Pro Experimental (03-25)            | 3.894    | 3.892        | 30.26            | 93.91       | 92791       | 170522       | 0.00<sup>1</sup> | 93.3%       |
| Grok 3 mini beta                               | 3.891    | 3.690        | 24.05            | 152.47      | 80100       | 220054       | 0.13             | 92.3%       |
| Claude 3.7 Sonnet                              | 3.819    | 3.756        | 24.60            | 76.31       | 100002      | 112605       | 1.99             | 91.4%       |
| OpenAI o3-mini (01-31)                         | 3.818    | 3.488        | 13.13            | 117.30      | 80551       | 92403        | 0.50             | 90.8%       |
| Gemini 2.0 Pro Experimental (02-05)            | 3.828    | 3.794        | 30.78            | 64.89       | 92798       | 119842       | 0.00<sup>1</sup> | 90.7%       |
| Claude 3.7 Sonnet (Thinking)                   | 3.778    | 3.683        | 42.16            | 79.27       | 100711      | 200502       | 3.31             | 90.2%       |
| Grok 3 beta                                    | 3.763    | 3.456        | 13.85            | 81.24       | 80076       | 67531        | 1.25             | 89.4%       |
| ChatGPT-4o                                     | 3.647    | 3.290        | 6.53             | 123.85      | 80575       | 48506        | 1.13             | 87.8%       |
| OpenAI o1 (1217)                               | 3.706    | 3.187        | 27.09            | 54.32       | 80551       | 88289        | 6.51             | 84.5%       |
| Gemini 2.0 Flash Thinking Experimental (01-21) | 3.365    | 3.321        | 10.65            | 188.16      | 92785       | 120261       | 0.00<sup>1</sup> | 84.4%       |
| DeepSeek V3 (03-24)                            | 3.619    | 3.440        | 28.65            | 35.38       | 82977       | 60811        | 0.17             | 83.9%       |
| GPT-4.5 preview                                | 3.613    | 2.873        | 73.49            | 8.59        | 80575       | 37894        | 11.73            | 77.6%       |
| DeepSeek R1                                    | 3.473    | 3.041        | 21.32            | 68.63       | 82977       | 87785        | 0.95             | 77.1%       |
| Llama 4 Maverick                               | 3.165    | 2.494        | 6.48             | 103.21      | 80493       | 40144        | 0.05             | 74.5%       |
| Amazon Nova Pro                                | 2.998    | 2.165        | 7.77             | 81.32       | 88588       | 37918        | 0.19             | 61.8%       |

_Table 1. Overview of the experiment results._

> Additional info:  
> Evaluation and grading of benchmark results were performed automatically with the help of evaluation tools based on the OpenAI o3-mini and Claude Sonnet 3.7 models.
> Please refer to the page [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) to learn about the evaluation tool.  
> <sup>1</sup> - Experimental models are not charged

We have visualized some of the information for your review.

![llm-rating.png](/images/llms/llm-rating.png)
![llm-price.png](/images/llms/llm-price.png)
![llm-tokens.png](/images/llms/llm-tokens.png)
![llm-cost.png](/images/llms/llm-cost.png)
![llm-time.png](/images/llms/llm-time.png)
![llm-speed.png](/images/llms/llm-speed.png)

## Models specification

| LLM Name                                                                                                                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Context Window | Cost (Input / Output per MTok) | Max Output         | Training Data  |
|---------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------|--------------------------------|--------------------|----------------|
| [Gemini 2.5 Pro Experimental (03-25)](https://blog.google/technology/google-deepmind/gemini-model-thinking-updates-march-2025/) | "Gemini 2.5 is a thinking model, designed to tackle increasingly complex problems. Our first 2.5 model, Gemini 2.5 Pro Experimental, leads common benchmarks by meaningful margins and showcases strong reasoning and code capabilities."<br>API Provider: Google AI Studio                                                                                                                                                                                                                                                                                                                                                                                     | 1M             | $0.00 / $0.00                  | 65K                | Jan, 2025      |
| [Claude 3.7 Sonnet](https://www.anthropic.com/news/claude-3-7-sonnet)                                                           | Claude 3.7 Sonnet is the most recent model by Anthropic. It is the most intelligent model to date by Anthropic and the first hybrid reasoning model on the market. Claude 3.7 Sonnet shows particularly strong improvements in coding and front-end web development.<br>API Provider: Google Vertex AI, also available on Anthropic Platform and AWS Bedrock                                                                                                                                                                                                                                                                                                    | 200K           | $3.00 / $15.00                 | 8K                 | Nov, 2024      |
| [Grok 3 mini beta](https://docs.x.ai/docs/models)                                                                               | A lightweight model that thinks before responding. Fast, smart, and great for logic-based tasks that do not require deep domain knowledge. The raw thinking traces are accessible.<br>API Provider: xAI Console                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 131K           | $0.30 / $0.50                  | 131K               | 17th Nov, 2024 |
| OpenAI o3-mini                                                                                                                  | OpenAI o3-mini is first OpenAI small reasoning model that supports highly requested developer features including function calling, Structured Outputs, and developer messages, making it production-ready out of the gate.<br>API Provider: OpenAI, Azure                                                                                                                                                                                                                                                                                                                                                                                                       | 200K           | $1.10 / $4.40                  | 100K               | Up to Oct 2023 |
| [Gemini 2.0 Pro Experimental (0205)](https://ai.google.dev/gemini-api/docs/models/experimental-models)                          | New version of Gemini Pro series model by Google Deepmind<br>API Provider: Google AI Studio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | 2M             | $0.00 / $0.00                  | 8K                 | Aug, 2024      |
| [Claude 3.7 Sonnet (Thinking mode)](https://www.anthropic.com/news/claude-3-7-sonnet)                                           | Claude 3.7 Sonnet with enabled thinking mode with 20K output tokens and 8K budget for thinking.<br>API Provider: Google Vertex AI, also available on Anthropic Platform and AWS Bedrock                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | 200K           | $3.00 / $15.00                 | 64K (128K in beta) | Nov, 2024      |
| [Grok 3 beta](https://docs.x.ai/docs/models)                                                                                    | xAI's flagship model that excels at enterprise use cases like data extraction, coding, and text summarization. Possesses deep domain knowledge in finance, healthcare, law, and science.<br>API Provider: xAI Console                                                                                                                                                                                                                                                                                                                                                                                                                                           | 131K           | $3.00 / $15.00                 | 131K               | 17th Nov, 2024 |
| ChatGPT-4o (Latest, 2025-03-26)                                                                                                 | Dynamic model continuously updated to the current version of GPT-4o in ChatGPT. Intended for research and evaluation. We are releasing this model for developers and researchers to explore OpenAI's latest research. For production use, OpenAI recommends using dated GPT models, which are optimized for API usage.<br>Parameters: Unknown<br>API Provider: OpenAI, Azure                                                                                                                                                                                                                                                                                    | 128K           | $5.00 / $15.00                 | 16K                | Up to Oct 2023 |
| OpenAI o1 (1217)                                                                                                                | OpenAI released stable version of o1 model in the end of 2024. Now it has larger context and larger output token size. The latest o1 model supports tools calling, both text and image inputs, and produces text outputs (including Structured Outputs).                                                                                                                                                                                                                                                                                                                                                                                                        | 200K           | $15.00 / $60.00                | 100K               | Up to Oct 2023 |
| [Gemini 2.0 Flash Thinking Experimental (0121)](https://ai.google.dev/gemini-api/docs/models/experimental-models)               | Latest (2.0) experimental Fast (Flash) Reasoning (Thinking) model by Google Deepmind<br>API Provider: Google AI Studio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | 1M             | $0.00 / $0.00                  | 64K                | Aug, 2024      |                 
| [DeepSeek V3 (03-24)](https://api-docs.deepseek.com/news/news250325)                                                            | Updated V3 model by DeepSeek: "Major boost in reasoning performance, stronger front-end development skills, smarter tool-use capabilities"<br>API Provider: [Fireworks AI](https://fireworks.ai/models/fireworks/deepseek-v3-0324)                                                                                                                                                                                                                                                                                                                                                                                                                              | 64K            | $1.20 / $1.20                  | 8K                 | Up to Oct 2023 |
| [DeepSeek R1](https://fireworks.ai/models/fireworks/deepseek-r1)                                                                | DeepSeek released R1, a reasoning model trained with initial supervised data followed by reinforcement learning. It matches OpenAI-o1's performance on math, code, and reasoning tasks. The models are open-sourced, with their 32B distilled version setting new records by outperforming OpenAI-o1-mini. <br>API Provider: DeepSeek platform (currently unavailable), Fireworks (used in benchmark), other providers                                                                                                                                                                                                                                          | 64K            | $3.00 / $8.00                  | 8K                 | Up to Oct 2023 |
| [GPT-4.5 Preview](https://openai.com/index/introducing-gpt-4-5/)                                                                | Most expensive OpenAI model to date. "Early testing shows that interacting with GPT‑4.5 feels more natural. Its broader knowledge base, improved ability to follow user intent, and greater "EQ" make it useful for tasks like improving writing, programming, and solving practical problems. We also expect it to hallucinate less"<br>API Provider: OpenAI, Azure                                                                                                                                                                                                                                                                                            | 128K           | $75.00 / $150.00               | 16K                | Up to Oct 2023 |
| [OpenAI o1-Pro](https://platform.openai.com/docs/models/o1-pro)                                                                 | A version of o1 with more compute for better responses<br>API Provider: OpenAI                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | 200K           | $150.00 / $600.00              | 100K               | Up to Oct 2023 |
| [Llama 4 Maverick](https://ai.meta.com/blog/llama-4-multimodal-intelligence)                                                    | One of new generation Llama models by Meta: "Llama 4 Maverick, a 17 billion active parameter model with 128 experts, is the best multimodal model in its class, beating GPT-4o and Gemini 2.0 Flash across a broad range of widely reported benchmarks, while achieving comparable results to the new DeepSeek v3 on reasoning and coding—at less than half the active parameters. Llama 4 Maverick offers a best-in-class performance to cost ratio with an experimental chat version scoring ELO of 1417 on LMArena"<br/>Parameters: 400B total (17B active)<br/>API Provider: Fireworks (used in benchmark)                                                  | 1M             | $0.05 / $0.22                  | 131K               | Aug, 2024      |
| [Amazon Nova Pro](https://aws.amazon.com/ai/generative-ai/nova/)                                                                | Amazon Nova Pro is a highly capable multimodal model with the best combination of accuracy, speed, and cost for a wide range of tasks.  Amazon Nova Pro’s capabilities, coupled with its industry-leading speed and cost efficiency, makes it a compelling model for almost any task, including video summarization, Q&A, mathematical reasoning, software development, and AI agents that can execute multi-step workflows. Amazon Nova Pro excels at instruction following and agentic workflows as measured by Comprehensive RAG Benchmark (CRAG), the Berkeley Function Calling Leaderboard, and Mind2Web.<br/>Parameters: Unknown<br/>API Provider: Amazon | 300K           | $0.80 / $3.20                  | 5K                 | October, 2023  |

_Table 2. Description of LLMs, their versions, amount of information to process, and the length of the response._

## Notes

- To learn more about our methodology for evaluating LLMs, please read [LLMs Benchmark Approach](llm-approach.md).
- To submit your model for evaluation, please refer to the [Large Language Model Benchmark Submission](submissions/llm-benchmark-submission.md) page.

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>