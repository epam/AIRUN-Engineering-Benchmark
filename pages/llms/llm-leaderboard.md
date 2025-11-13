# LLMs Leaderboard (Benchmark v3, last update 2025-11-13)

> 📊 **Interactive Leaderboard**: View live results with charts at Our [LLM Leaderboard](https://epam.github.io/AIRUN-Engineering-Benchmark/llm)

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

- Claude Sonnet 4.5 achieves top position with 82.19% total score, demonstrating exceptional balanced performance across all coding categories without requiring reasoning mode
- GPT-5 (08-07) follows closely at 82.13%, achieving the best code translation performance (84.79%) and strong code generation (78.92%)
- Claude Haiku 4.5 secures third place with 81.83% score, representing Anthropic's upgraded smaller model with significantly improved performance, exceptional speed (180.66 tokens/sec), and support
  for extended output (64K tokens)
- Grok 4 Fast achieves 79.45% score, delivering excellent performance with exceptional cost-efficiency ($0.22)
- GPT-5 Codex achieves 77.25% score as a specialized agentic coding model, optimized for complex software engineering tasks with dynamic thinking time adjustment and enhanced iterative capabilities
- GPT-5 Mini achieves 71.28% in coding but excels in multimodal tasks (79.21%, 3rd place), strong code translation (80.92%, 4th) and documentation (78.64%, 4th) despite weak LCIF performance (55%)
- MiniMax M2 achieves 71.14% as the top-performing open-source model, excelling in code translation (81.63%, 4th place) and agentic tasks with active tool usage, though it struggles with LCIF (
  61.25%) and large content generation, with observed issues of generating repetitive content until token limits during testing, while having slower execution (172.20 min, 31.67 T/S) but reasonable
  cost ($0.49)
- GPT-5 Nano scores 58.61% in coding with exceptional cost-efficiency ($0.33 coding, $0.13 multimodal), generating the most tokens of any model but struggling with LCIF (42.50%)
- Claude 4 Sonnet scores 75.68%, outperforming its Thinking mode variant (73.73%), demonstrating that reasoning modes don't always improve coding performance
- Grok 4 (07-09) achieves 73.33% score with balanced capabilities, while Grok Code Fast delivers 71.74% with exceptional speed (165.54 tokens/sec) and outstanding cost efficiency ($0.33)
- Gemini 2.5 Flash Preview (0925) scores 69.37% with improved agentic reasoning and 15% performance leap in long-horizon tasks, plus enhanced cost-efficiency through higher-quality outputs
- gpt-oss-120b represents a breakthrough for open-source models at 62.19% score with extraordinary speed (555.99 tokens/sec) and ultra-low cost ($0.23)
- Amazon Nova Premier struggles significantly in coding tasks (26.89% score), indicating limitations for software engineering applications

**Multimodal Benchmark Leaders:**

- GPT-5 (08-07) maintains leadership with 81.56% score, demonstrating consistent excellence across both coding and multimodal domains
- Gemini 2.5 Flash achieves 80.50% score with impressive speed (127.87 tokens/sec) and cost efficiency ($0.42), making it the top choice for multimodal tasks
- GPT-5 Mini achieves 79.21% score, significantly outperforming its coding results (71.28%), with excellent cost-efficiency ($0.48) and strong balanced performance
- Gemini 2.5 Pro scores 78.83% with strong performance and reasonable cost ($1.85), showing Google's strength in multimodal reasoning
- GPT-5 Codex delivers 73.06% score in multimodal tasks, showing strong cross-domain capabilities with enhanced visual inspection and front-end development strengths
- Gemini 2.5 Flash Preview (0925) achieves 72.97% score with enhanced multimodal capabilities and improved instruction adherence
- Claude Haiku 4.5 achieves 61.13% score in multimodal tasks with ultrafast execution time (4.64 min) and excellent cost-efficiency ($0.91), though significantly behind its strong coding performance (
  81.83%)
- Claude 4 Sonnet (Thinking) improves to 60.69% vs. 56.68% for base model, showing reasoning mode benefits in multimodal contexts
- Grok 4 Fast scores 50.74% in multimodal tasks compared to its strong 79.45% coding performance, while Grok 4 significantly underperforms (43.78% vs. 73.33% in coding), indicating xAI's
  specialization in text-based programming tasks

Performance metrics highlights:

**Coding Benchmark:**

- **Fastest token generation**: gpt-oss-120b (555.99 T/S), Gemini 2.5 Flash Preview (200.57 T/S), Claude Haiku 4.5 (180.66 T/S), Gemini 2.5 Flash (166.51 T/S), Grok Code Fast (165.54 T/S)
- **Shortest execution time**: gpt-oss-120b (6.71 min), Grok Code Fast (17.66 min), Claude Haiku 4.5 (59.27 min)
- **Most tokens generated**: Gemini 2.5 Flash (698,984 tokens), Claude Haiku 4.5 (642,436 tokens), Gemini 2.5 Flash Preview (502,395 tokens), Claude Sonnet 4.5 (496,983 tokens)
- **Best cost-effectiveness**: Grok 4 Fast ($0.22), gpt-oss-120b ($0.23), Grok Code Fast ($0.33), Amazon Nova Premier ($1.12), Gemini 2.5 Flash Preview ($1.37), GPT-5 (08-07) ($3.39), Claude Haiku
  4.5 ($3.61)

**Multimodal Benchmark:**

- **Fastest token generation**: Gemini 2.5 Flash Preview (155.63 T/S), Gemini 2.5 Flash (127.87 T/S), Grok 4 Fast (91.42 T/S), Gemini 2.5 Pro (77.01 T/S), Claude Haiku 4.5 (74.89 T/S)
- **Shortest execution time**: Claude Haiku 4.5 (4.64 min), Claude Sonnet 4.5 (8.46 min), Gemini 2.5 Flash Preview (9.71 min), Claude Sonnet 4 (10.83 min), Gemini 2.5 Flash (11.51 min)
- **Best cost-effectiveness**: Gemini 2.5 Flash ($0.42), Gemini 2.5 Flash Preview ($0.44), Claude Haiku 4.5 ($0.91), GPT-5 Codex ($1.11), GPT-5 ($1.19)

Best results by category:

**Coding Benchmark:**

- **Code Translation**: GPT-5 (08-07) (84.79%), Claude Haiku 4.5 (82.63%), GPT-5 Codex (81.67%), Claude Sonnet 4 (79.08%), Gemini 2.5 Pro (78.38%), Grok 4 Fast (77.79%)
- **Code Generation**: GPT-5 Codex (81.42%), Grok 4 Fast (80.38%), GPT-5 (08-07) (78.92%), Claude Sonnet 4.5 (75.92%), Claude Sonnet 4 (74.65%), Claude Haiku 4.5 (74.04%)
- **Code Documentation**: Claude Haiku 4.5 (80.64%), GPT-5 (08-07) (79.81%), Claude Sonnet 4.5 (79.53%), Grok 4 Fast (78.39%), gpt-oss-120b (67.86%)
- **LCIF**: Grok Code Fast (98.50%), Claude Sonnet 4/4.5 (96.25%), Grok 4 (92.50%), Claude Haiku 4.5 (90.00%), GPT-5 Codex (86.25%)

**Multimodal Benchmark:**

- **Overall Multimodal Performance**: GPT-5 (81.56%), Gemini 2.5 Flash (80.50%), Gemini 2.5 Pro (78.83%), GPT-5 Codex (73.06%), Gemini 2.5 Flash Preview (72.97%)

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
The benchmark v3 results reveal fascinating insights about model specialization and generalization. GPT-5 demonstrates remarkable consistency across both domains, maintaining leadership in coding (
82.13%) and multimodal (81.56%) tasks. This consistency suggests superior general intelligence and robust training across diverse data types.

**OpenAI's Specialized Agentic Coding Model**
GPT-5 Codex emerges as a purpose-built solution for complex software engineering tasks, achieving 77.25% in coding and 73.06% in multimodal benchmarks. This specialized model excels in code
generation (81.42%) and code translation (81.67%), surpassing even the base GPT-5 in these specific areas. Trained on complex, real-world software engineering activities including building full
projects, debugging, and large-scale refactors, GPT-5 Codex features dynamic thinking time adjustment - using 93.7% fewer tokens for simple tasks while investing twice the effort on complex 10% of
tasks. The model's enhanced capabilities in front-end development, visual inspection, and iterative problem-solving make it ideal for comprehensive software engineering workflows.

**Google's Multimodal Advantage and Preview Improvements**
While Google's Gemini models underperform in pure coding tasks (Gemini 2.5 Pro: 65.67%, Flash: 60.46%), they excel in multimodal scenarios (Pro: 78.83%, Flash: 80.50%). Gemini 2.5 Flash emerges as the
top choice for multimodal applications, combining strong performance with exceptional speed and cost efficiency. The new Gemini 2.5 Flash Preview (0925) achieves 69.37% in coding and 72.97% in
multimodal tasks, showing improvements in agentic reasoning capabilities and faster execution times (9.71 min in multimodal, 41.75 min in coding) with enhanced token generation speed (200.57 T/S in
coding, 155.63 T/S in multimodal).

**Anthropic's Latest Achievement and Reasoning Mode Paradox**
Claude Sonnet 4.5 achieves breakthrough performance, claiming the top spot in coding benchmark with 82.19% score, marginally surpassing GPT-5 (82.13%). This latest model demonstrates exceptional
balanced capabilities across all coding categories without requiring reasoning mode, achieving second place in code documentation (79.53%) and solid performance in code generation (75.92%). However,
Claude Sonnet 4.5 shows significant regression in multimodal tasks (54.76%), performing worse than both Claude 4 base (56.68%) and Claude 4 Thinking (60.69%), though it delivers the fastest multimodal
execution time (8.46 min).

Claude Haiku 4.5 emerges as a remarkable smaller model, securing third place in coding benchmark with 81.83% score and achieving first place in code documentation (80.64%). This represents a
significant upgrade from Haiku 3.5, with the new model supporting extended output (64K tokens, up from 8K), reasoning capabilities (though not utilized in these tests to avoid performance
degradation), and improved knowledge cutoff (July 2025). The model exhibits Sonnet-like behavior and quality while maintaining exceptional speed (180.66 T/S in coding, 74.89 T/S in multimodal) and
competitive cost ($3.61 coding, $0.91 multimodal). Claude Haiku 4.5 excels in code translation (82.63%, second only to GPT-5) and achieves ultrafast multimodal execution (4.64 min), though its
multimodal performance (61.13%) lags significantly behind its coding capabilities, mirroring the pattern seen across the Claude family. The model supports multiple tool calling, making it suitable for
complex agentic workflows.

The Claude model family reveals an interesting pattern: reasoning mode consistently hurts coding performance (Claude 4 base: 75.68% vs. thinking: 73.73%) but improves multimodal capabilities (base:
56.68% vs. thinking: 60.69%). This suggests reasoning mode benefits complex visual understanding but may overcomplicate straightforward coding tasks. Claude Sonnet 4.5's strong coding performance
without reasoning mode confirms that Anthropic has successfully integrated advanced reasoning directly into the base model architecture.

**xAI's Domain Specialization and Efficiency Breakthrough**
Grok models show dramatic performance variation across domains but demonstrate significant advancement with Grok 4 Fast. The new model achieves 79.45% in coding tasks, making it a strong third-place
contender with exceptional cost-efficiency at $0.22. Grok 4 Fast features state-of-the-art cost-effectiveness, 2M token context window, and faster execution time (41.22 min) compared to Grok 4 (80.75
min), though it still struggles in multimodal scenarios (50.74% vs. 79.45% coding), confirming xAI's specialization in text-based programming. Grok Code Fast's exceptional LCIF performance (98.50%)
demonstrates superior instruction-following capabilities.

**Open-Source Breakthrough in Coding**
gpt-oss-120b achieves remarkable coding performance (62.19%) with unprecedented speed (555.99 T/S) and minimal cost ($0.23), making it a game-changer for organizations seeking cost-effective coding
assistance. However, this model wasn't evaluated in multimodal tasks, limiting its applicability scope.

**Enterprise Deployment Considerations**
For organizations choosing models, domain requirements significantly impact optimal selection:

- **Pure Coding Tasks**: Claude Sonnet 4.5 for top overall performance, Claude Haiku 4.5 for high-performance budget option with exceptional speed, GPT-5 for best code translation quality, GPT-5 Codex
  for specialized agentic software engineering, Grok 4 Fast for excellent performance with cost efficiency, gpt-oss-120b for open-source
- **Multimodal Applications**: Gemini 2.5 Flash for balanced performance, GPT-5 for high quality, GPT-5 Mini for cost-effective excellence ($0.48), Gemini 2.5 Flash Preview for enhanced agentic
  reasoning, Claude Haiku 4.5 for ultrafast execution
- **Mixed Workloads**: GPT-5 offers the best cross-domain consistency (82.13% coding, 81.59% multimodal), GPT-5 Mini delivers strong multimodal (79.21%) with solid coding (71.28%), while Claude Sonnet
  4.5 excels in coding but underperforms in multimodal scenarios
- **Cost-Optimized Solutions**: Grok 4 Fast leads in cost-efficiency ($0.22) with excellent coding performance, GPT-5 Nano for ultra-low-cost operations ($0.13 multimodal, $0.33 coding), Claude Haiku
  4.5 offers premium performance at mid-tier pricing, Gemini 2.5 Flash Preview offers improved token efficiency for multimodal tasks

### Detailed Results

All categories, except Large Context Instructions Following (LCIF), are evaluated automatically using the Large Language Model<sup>1</sup>.
You can read [llm-comparison-report.md](llm-comparison-report.md) for detailed coding benchmark analysis and [llm-comparison-report-multimodal.md](llm-comparison-report-multimodal.md) for multimodal
benchmark results. These reports include all experiment scores, performance breakdowns by category, and comprehensive analysis.

The tables below provide an overview of both coding and multimodal benchmark experiments. For coding tasks, you can review the average accuracy and completeness across all categories, total execution
time,
generation token speed (token per second), the total number of input and output tokens, the cost of the experiment, and the final score. The multimodal benchmark focuses on visual reasoning and
multimodal instruction following capabilities.

<details>
<summary>Detailed Results and Observations</summary>

### Coding Benchmark Results

| Name                            | Reasoning  | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total Thinking | Total output | Cost $ | Total Score |
|---------------------------------|------------|----------|--------------|------------------|-------------|-------------|----------------|--------------|--------|-------------|
| Claude Sonnet 4.5               | No         | 0.773    | 0.782        | 101.75           | 81.41       | 399735      | -              | 496983       | 8.65   | 82.19%      |
| GPT-5 (08-07)                   | Yes (low)  | 0.800    | 0.818        | 92.53            | 53.94       | 314949      | 28800          | 299430       | 3.39   | 82.13%      |
| Claude Haiku 4.5                | No         | 0.777    | 0.807        | 59.27            | 180.66      | 399778      | -              | 642436       | 3.61   | 81.83%      |
| Grok 4 Fast                     | Yes        | 0.767    | 0.810        | 41.22            | 125.84      | 315508      | 65852          | 311224       | 0.22   | 79.45%      |
| GPT-5 Codex                     | Yes (low)  | 0.696    | 0.751        | 69.49            | 63.39       | 314149      | 61760          | 264293       | 3.04   | 77.25%      |
| Claude Sonnet 4                 | No         | 0.652    | 0.683        | 64.24            | 85.92       | 399848      | -              | 331188       | 6.17   | 75.68%      |
| Claude Sonnet 4 (Thinking)      | Yes        | 0.638    | 0.654        | 64.01            | 82.58       | 401095      | N/A            | 317158       | 5.96   | 73.73%      |
| Grok 4 (07-09)                  | Yes        | 0.680    | 0.652        | 80.75            | 46.27       | 339997      | 57357          | 224156       | 4.38   | 73.33%      |
| Grok Code Fast                  | Yes        | 0.645    | 0.603        | 17.66            | 165.54      | 319314      | 16584          | 175420       | 0.33   | 71.74%      |
| GPT-5 Mini                      | Yes (high) | 0.751    | 0.785        | 191.62           | 56.51       | 314149      | 339968         | 649773       | 1.38   | 71.28%      |
| MiniMax M2                      | Yes        | 0.714    | 0.756        | 172.20           | 31.67       | 320258      | N/A            | 327231       | 0.49   | 71.14%      |
| Gemini 2.5 Flash Preview (0925) | Yes        | 0.633    | 0.642        | 41.75            | 200.57      | 374616      | 281794         | 502395       | 1.37   | 69.37%      |
| Gemini 2.5 Pro                  | Yes        | 0.594    | 0.609        | 63.77            | 107.42      | 374686      | 144617         | 410997       | 4.58   | 65.67%      |
| gpt-oss-120b                    | Yes (low)  | 0.709    | 0.720        | 6.71             | 555.99      | 316966      | N/A            | 223941       | 0.23   | 62.19%      |
| Gemini 2.5 Flash                | Yes        | 0.633    | 0.675        | 69.96            | 166.51      | 339193      | 204426         | 698984       | 2.50   | 60.46%      |
| GPT-5 Nano                      | Yes (high) | 0.652    | 0.630        | 150.27           | 86.83       | 314149      | 541824         | 782832       | 0.33   | 58.61%      |
| Amazon Nova Premier             | No         | 0.282    | 0.205        | 15.88            | 46.56       | 224223      | 0              | 44360        | 1.12   | 26.89%      |

_Table 1. Overview of the coding benchmark results._

### Multimodal Benchmark Results

| Name                            | Reasoning  | Accuracy | Completeness | Total Time (min) | Speed (T/S) | Total input | Total Thinking | Total output | Cost $ | Total Score |
|---------------------------------|------------|----------|--------------|------------------|-------------|-------------|----------------|--------------|--------|-------------|
| GPT-5 (08-07)                   | Yes (low)  | 0.796    | 0.992        | 17.31            | 41.09       | 613046      | 21952          | 42680        | 1.19   | 81.59%      |
| Gemini 2.5 Flash                | Yes        | 0.790    | 0.940        | 11.51            | 127.87      | 718866      | 61545          | 88295        | 0.42   | 80.50%      |
| GPT-5 Mini                      | Yes (high) | 0.769    | 0.997        | 51.23            | 52.28       | 636192      | 124352         | 160700       | 0.48   | 79.21%      |
| Gemini 2.5 Pro                  | Yes        | 0.769    | 0.962        | 20.49            | 77.01       | 718866      | 69631          | 94691        | 1.85   | 78.83%      |
| GPT-5 Codex                     | Yes (low)  | 0.704    | 0.970        | 11.67            | 49.14       | 610301      | 23232          | 34411        | 1.11   | 73.06%      |
| Gemini 2.5 Flash Preview (0925) | Yes        | 0.707    | 0.934        | 9.71             | 155.63      | 718866      | 68793          | 90663        | 0.44   | 72.97%      |
| GPT-5 Nano                      | Yes (high) | 0.627    | 0.994        | 46.74            | 86.49       | 649510      | 208768         | 242562       | 0.13   | 66.34%      |
| Claude Haiku 4.5                | No         | 0.571    | 0.971        | 4.64             | 74.89       | 801240      | -              | 20831        | 0.91   | 61.13%      |
| Claude 4 Sonnet (Thinking)      | Yes        | 0.567    | 0.966        | 18.60            | 43.96       | 802110      | N/A            | 49062        | 3.14   | 60.66%      |
| Claude 4 Sonnet                 | No         | 0.523    | 0.961        | 10.83            | 28.56       | 801240      | -              | 18563        | 2.68   | 56.68%      |
| Claude 4.5 Sonnet               | No         | 0.503    | 0.949        | 8.46             | 37.12       | 801210      | -              | 18843        | 2.69   | 54.76%      |
| Amazon Nova Premier             | No         | 0.489    | 0.928        | 14.85            | 16.78       | 767489      | -              | 14954        | 2.11   | 53.26%      |
| Grok 4 Fast                     | Yes        | 0.455    | 0.982        | 14.22            | 91.42       | 586517      | 32902          | 77976        | 0.16   | 50.74%      |
| Grok 4 (07-09)                  | Yes        | 0.380    | 0.958        | 66.46            | 42.72       | 606242      | 138102         | 170368       | 4.37   | 43.75%      |

_Table 2. Overview of the multimodal benchmark results._

> Additional info:  
> Evaluation of benchmark results were performed automatically with the help of evaluation tools based on the LLMs.
> Please refer to the page [LLMs Benchmark Approach](llm-approach.md) for more details on the evaluation methodology.

</details>

## Models specification

| LLM Name                                                                                                                                                 | API Provider used in benchmark                                                        | Context Window | Cost (Input / Output per MTok)                   | Max Output | Knowledge Cutoff |
|----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|----------------|--------------------------------------------------|------------|------------------|
| [Claude 4.5 Sonnet](https://www.anthropic.com/news/claude-sonnet-4-5)                                                                                    | Google Vertex AI                                                                      | 200K           | $3.00 / $15.00                                   | 64K        | July, 2025       |
| [GPT-5 (08-07)](https://platform.openai.com/docs/models/gpt-5)                                                                                           | OpenAI                                                                                | 400K           | $1.25 / $10.00                                   | 128K       | Sep 30, 2024     |
| [Claude Haiku 4.5](https://www.anthropic.com/news/claude-haiku-4-5)                                                                                      | Google Vertex AI                                                                      | 200K           | $1.00 / $5.00                                    | 64K        | July, 2025       |
| [Grok 4 Fast Reasoning](https://docs.x.ai/docs/models/grok-4-fast-reasoning)                                                                             | xAI                                                                                   | 2M             | $0.20 / $0.50                                    | N/A        | N/A              |
| [GPT-5-codex](https://platform.openai.com/docs/models/gpt-5-codex)                                                                                       | OpenAI                                                                                | 400K           | $1.25 / $10.00                                   | 128K       | Sep 30, 2024     |
| [Claude 4 Sonnet](https://www.anthropic.com/news/claude-4)                                                                                               | Google Vertex AI                                                                      | 200K           | $3.00 / $15.00                                   | 64K        | Mar, 2025        |
| [Grok 4 (07-09)](https://docs.x.ai/docs/models/grok-4-0709)                                                                                              | xAI Console                                                                           | 256K           | $3.00 / $15.00 <= 128K and $6.00 / $30.00 > 128K | N/A        | N/A              |
| [Grok Code Fast](https://x.ai/news/grok-code-fast-1)                                                                                                     | xAI                                                                                   | 256K           | $0.20 / $1.50                                    | N/A        | N/A              |
| [GPT-5 Mini (08-07)](https://platform.openai.com/docs/models/gpt-5-mini)                                                                                 | OpenAI                                                                                | 400K           | $0.25 / $2.00                                    | 128K       | May 31, 2024     |
| [MiniMax M2](https://github.com/MiniMax-AI/MiniMax-M2)                                                                                                   | [Fireworks.ai](https://fireworks.ai/models/fireworks/minimax-m2)                      | 200K           | $0.30 / $1.20                                    | 131K       | N/A              |
| [Gemini 2.5 Flash Preview (0925)](https://ai.google.dev/gemini-api/docs/models#gemini-2.5-flash-preview)                                                 | Google AI Studio                                                                      | 1M             | $0.30 / $2.50                                    | 65K        | Jan, 2025        |
| [Gemini 2.5 Pro](https://ai.google.dev/gemini-api/docs/models#gemini-2.5-pro)                                                                            | Google AI Studio                                                                      | 1M             | $1.25 / $10.00 <= 200K<br>$2.50 / $15.00 > 200K  | 65K        | Jan, 2025        |
| [gpt-oss-120b](https://platform.openai.com/docs/models/gpt-oss-120b)                                                                                     | [Cerebras](https://www.cerebras.ai/blog/openai-gpt-oss-120b-runs-fastest-on-cerebras) | 131K           | $0.25 / $0.69                                    | 33K        | Jun 01, 2024     |
| [Gemini 2.5 Flash](https://ai.google.dev/gemini-api/docs/models#gemini-2.5-flash)                                                                        | Google AI Studio                                                                      | 1M             | $0.15 / $3.50                                    | 65K        | Jan, 2025        |
| [GPT-5 Nano (08-07)](https://platform.openai.com/docs/models/gpt-5-nano)                                                                                 | OpenAI                                                                                | 400K           | $0.05 / $0.40                                    | 128K       | May 31, 2024     |
| [Amazon Nova Premier](https://aws.amazon.com/blogs/aws/amazon-nova-premier-our-most-capable-model-for-complex-tasks-and-teacher-for-model-distillation/) | AWS Bedrock                                                                           | 1M             | $2.5 / $12.5                                     | 10K        | N/A              |

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