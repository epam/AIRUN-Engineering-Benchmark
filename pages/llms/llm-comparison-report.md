# LLM's Evaluation Results

## Introduction

This report presents a comprehensive evaluation of leading Large Language Models (LLMs) across multiple performance categories. Our benchmark compares different LLMs, including models from OpenAI,
Anthropic, Google Deepmind, xAI, Amazon, and open-source alternatives. The evaluation focused on four key areas: code translation, code generation, code documentation, and large context instruction
following (LCIF).

## 📊 Current Rankings

For detailed information about our approach and evaluation methodology, please refer to the following pages:

- [LLMs Benchmark Approach](llm-approach.md)
- [Automated Evaluation with LLMs](automated-evaluation-with-llms.md)

| Model                | Benchmark model ID      | Reasoning  | Execution Date | Code Translation | Code Generation | Code Document | LCIF   | Total Score |
|----------------------|-------------------------|------------|----------------|------------------|-----------------|---------------|--------|-------------|
| GPT51_1113_high      | GPT-5.1 (11-13) (high)  | Yes (high) | 2025-11-14     | 84.71%           | 78.96%          | 80.92%        | 91.25% | 83.96%      |
| GPT51_1113           | GPT-5.1 (11-13)         | No         | 2025-11-14     | 84.17%           | 77.65%          | 80.39%        | 91.25% | 83.36%      |
| Claude_Opus_45       | Claude Opus 4.5         | No         | 2025-11-25     | 82.83%           | 73.96%          | 77.42%        | 98.50% | 83.18%      |
| Claude_Sonnet_45     | Claude Sonnet 4.5       | No         | 2025-09-30     | 77.04%           | 75.92%          | 79.53%        | 96.25% | 82.19%      |
| Claude_Haiku_45      | Claude Haiku 4.5        | No         | 2025-10-16     | 82.63%           | 74.04%          | 80.64%        | 90.00% | 81.83%      |
| Grok4FastReasoning   | Grok 4 Fast             | Yes        | 2025-09-26     | 77.79%           | 80.38%          | 78.39%        | 81.25% | 79.45%      |
| GPT51_Codex          | GPT-5.1 Codex           | Yes (high) | 2025-11-21     | 76.00%           | 79.15%          | 63.47%        | 96.25% | 78.72%      |
| GPT5_Codex           | GPT-5 Codex             | Yes (low)  | 2025-09-26     | 81.67%           | 81.42%          | 59.67%        | 86.25% | 77.25%      |
| Grok4_0709           | Grok 4 (07-09)          | Yes        | 2025-09-11     | 70.63%           | 65.23%          | 64.94%        | 92.50% | 73.33%      |
| Grok_Code_0825       | Grok Code Fast          | Yes        | 2025-09-11     | 71.13%           | 56.50%          | 60.83%        | 98.50% | 71.74%      |
| GPT5_Mini_high       | GPT-5 Mini              | Yes (high) | 2025-10-24     | 80.92%           | 70.58%          | 78.64%        | 55.00% | 71.28%      |
| MiniMaxM2            | MiniMax M2              | Yes        | 2025-11-05     | 81.63%           | 73.92%          | 67.78%        | 61.25% | 71.14%      |
| Gemini_3_Pro_Preview | Gemini 3 Pro Preview    | Yes (high) | 2025-11-19     | 74.42%           | 58.23%          | 52.08%        | 96.25% | 70.25%      |
| Grok41_FastReasoning | Grok 4.1 Fast Reasoning | Yes        | 2025-11-21     | 38.08%           | 71.42%          | 70.83%        | 91.25% | 67.90%      |
| GPT_OSS_120B         | gpt-oss-120b            | Yes (low)  | 2025-09-11     | 76.88%           | 71.54%          | 67.86%        | 32.50% | 62.19%      |
| GPT51_Codex_mini     | GPT-5.1 Codex mini      | Yes (high) | 2025-11-21     | 70.50%           | 53.38%          | 57.42%        | 65.00% | 61.58%      |
| Grok41_Fast          | Grok 4.1 Fast           | No         | 2025-11-21     | 67.17%           | 59.29%          | 57.64%        | 56.25% | 60.09%      |
| GPT5_Nano_high       | GPT-5 Nano              | Yes (high) | 2025-10-24     | 72.08%           | 52.92%          | 66.92%        | 42.50% | 58.61%      |
| AmazonNovaPremier    | Amazon Nova Premier     | No         | 2025-09-11     | 24.54%           | 26.88%          | 22.39%        | 33.75% | 26.89%      |

_Table 1. Results of evaluation LLMs in EPAM's LLMs Benchmark._

## Results by categories

### Code Translation

| Model                | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT51_1113_high      | 0.810        | 0.884            | 310.50   | 24514.67  | 78.95             | 0.8471  |
| GPT51_1113           | 0.808        | 0.876            | 100.42   | 8736.00   | 87.00             | 0.8417  |
| Claude_Opus_45       | 0.822        | 0.835            | 194.05   | 14298.00  | 73.68             | 0.8283  |
| Claude_Haiku_45      | 0.811        | 0.842            | 70.16    | 14007.83  | 199.65            | 0.8263  |
| GPT5_Codex           | 0.778        | 0.856            | 161.51   | 10175.17  | 63.00             | 0.8167  |
| MiniMaxM2            | 0.803        | 0.829            | 183.60   | 10530.50  | 57.36             | 0.8163  |
| GPT5_Mini_high       | 0.772        | 0.847            | 262.90   | 16592.33  | 63.11             | 0.8092  |
| Grok4FastReasoning   | 0.755        | 0.801            | 76.51    | 9506.33   | 124.25            | 0.7779  |
| Claude_Sonnet_45     | 0.763        | 0.778            | 104.68   | 9619.83   | 91.89             | 0.7704  |
| GPT_OSS_120B         | 0.753        | 0.785            | 9.64     | 6600.25   | 684.50            | 0.7688  |
| GPT51_Codex          | 0.742        | 0.778            | 357.05   | 25115.33  | 70.34             | 0.7600  |
| Gemini_3_Pro_Preview | 0.699        | 0.789            | 84.18    | 8472.25   | 100.64            | 0.7442  |
| GPT5_Nano_high       | 0.725        | 0.717            | 253.90   | 22961.83  | 90.44             | 0.7208  |
| Grok_Code_0825       | 0.738        | 0.684            | 27.02    | 5852.08   | 216.62            | 0.7113  |
| Grok4_0709           | 0.667        | 0.746            | 188.24   | 9413.75   | 50.01             | 0.7063  |
| GPT51_Codex_mini     | 0.704        | 0.706            | 156.10   | 21590.92  | 138.31            | 0.7050  |
| Grok41_Fast          | 0.680        | 0.663            | 51.49    | 5469.50   | 106.22            | 0.6717  |
| Grok41_FastReasoning | 0.330        | 0.432            | 119.26   | 2397.58   | 20.10             | 0.3808  |
| AmazonNovaPremier    | 0.303        | 0.188            | 18.65    | 1065.92   | 57.17             | 0.2454  |

_Table 2. Code Translation results of LLMs in EPAM's LLMs Benchmark._

### Code Generation

| Model                | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT5_Codex           | 0.819        | 0.809            | 106.15   | 7123.23   | 67.11             | 0.8142  |
| Grok4FastReasoning   | 0.812        | 0.796            | 53.90    | 7660.62   | 142.13            | 0.8038  |
| GPT51_Codex          | 0.821        | 0.762            | 480.27   | 17801.92  | 37.07             | 0.7915  |
| GPT51_1113_high      | 0.789        | 0.790            | 272.64   | 18210.62  | 66.79             | 0.7896  |
| GPT51_1113           | 0.779        | 0.774            | 90.13    | 7352.23   | 81.58             | 0.7765  |
| Claude_Sonnet_45     | 0.758        | 0.760            | 173.16   | 16989.00  | 98.11             | 0.7592  |
| Claude_Haiku_45      | 0.718        | 0.762            | 88.17    | 18798.62  | 213.22            | 0.7404  |
| Claude_Opus_45       | 0.737        | 0.742            | 252.35   | 19200.15  | 76.08             | 0.7396  |
| MiniMaxM2            | 0.732        | 0.747            | 432.02   | 9330.92   | 21.60             | 0.7392  |
| GPT_OSS_120B         | 0.723        | 0.708            | 8.89     | 4849.08   | 545.55            | 0.7154  |
| Grok41_FastReasoning | 0.737        | 0.692            | 97.55    | 5163.54   | 52.93             | 0.7142  |
| GPT5_Mini_high       | 0.732        | 0.680            | 288.81   | 15851.31  | 54.88             | 0.7058  |
| Grok4_0709           | 0.705        | 0.600            | 83.24    | 3994.92   | 47.99             | 0.6523  |
| Grok41_Fast          | 0.623        | 0.563            | 41.83    | 4341.85   | 103.81            | 0.5929  |
| Gemini_3_Pro_Preview | 0.595        | 0.570            | 62.74    | 5953.62   | 94.90             | 0.5823  |
| Grok_Code_0825       | 0.640        | 0.490            | 21.92    | 3548.92   | 161.89            | 0.5650  |
| GPT51_Codex_mini     | 0.563        | 0.505            | 96.64    | 13013.62  | 134.67            | 0.5338  |
| GPT5_Nano_high       | 0.595        | 0.464            | 210.25   | 19960.23  | 94.94             | 0.5292  |
| AmazonNovaPremier    | 0.324        | 0.214            | 20.18    | 1229.85   | 60.94             | 0.2688  |

_Table 3. Code Generation results of LLMs in EPAM's LLMs Benchmark._

### Code Documentation

| Model                | Avg Accuracy | Avg Completeness | Avg Time | Avg token | Avg Tokens/second | Score ↓ |
|----------------------|--------------|------------------|----------|-----------|-------------------|---------|
| GPT51_1113_high      | 0.792        | 0.827            | 167.69   | 12038.94  | 71.79             | 0.8092  |
| Claude_Haiku_45      | 0.797        | 0.816            | 87.10    | 12775.56  | 146.67            | 0.8064  |
| GPT51_1113           | 0.798        | 0.810            | 96.18    | 6880.94   | 71.54             | 0.8039  |
| Claude_Sonnet_45     | 0.789        | 0.801            | 144.31   | 8927.11   | 61.86             | 0.7953  |
| GPT5_Mini_high       | 0.752        | 0.821            | 254.90   | 13588.78  | 53.31             | 0.7864  |
| Grok4FastReasoning   | 0.742        | 0.826            | 47.47    | 5420.00   | 114.18            | 0.7839  |
| Claude_Opus_45       | 0.739        | 0.809            | 162.00   | 10124.11  | 62.49             | 0.7742  |
| Grok41_FastReasoning | 0.704        | 0.713            | 37.37    | 2592.17   | 69.37             | 0.7083  |
| GPT_OSS_120B         | 0.671        | 0.687            | 9.53     | 4538.89   | 476.33            | 0.6786  |
| MiniMaxM2            | 0.642        | 0.714            | 139.60   | 4420.17   | 31.66             | 0.6778  |
| GPT5_Nano_high       | 0.646        | 0.693            | 179.79   | 13767.06  | 76.57             | 0.6692  |
| Grok4_0709           | 0.671        | 0.628            | 83.55    | 3292.06   | 39.40             | 0.6494  |
| GPT51_Codex          | 0.612        | 0.658            | 73.23    | 3496.17   | 47.74             | 0.6347  |
| Grok_Code_0825       | 0.586        | 0.631            | 25.03    | 3281.06   | 131.09            | 0.6083  |
| GPT5_Codex           | 0.553        | 0.640            | 47.30    | 2754.94   | 58.25             | 0.5967  |
| Grok41_Fast          | 0.552        | 0.601            | 22.38    | 2054.22   | 91.81             | 0.5764  |
| GPT51_Codex_mini     | 0.536        | 0.613            | 22.76    | 2861.39   | 125.71            | 0.5742  |
| Gemini_3_Pro_Preview | 0.496        | 0.546            | 46.29    | 3895.83   | 84.16             | 0.5208  |
| AmazonNovaPremier    | 0.238        | 0.210            | 25.93    | 865.61    | 33.39             | 0.2239  |

_Table 4. Code Documentation results of LLMs in EPAM's LLMs Benchmark._

### LCIF (Large Context Instruction Following)

| Model                | Hard Accuracy | Hard Completeness | Light Accuracy | Light Completeness | Score ↓ |
|----------------------|---------------|-------------------|----------------|--------------------|---------|
| Grok_Code_0825       | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Claude_Opus_45       | 3.8           | 4                 | 4              | 4                  | 0.985   |
| Claude_Sonnet_45     | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Gemini_3_Pro_Preview | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| GPT51_Codex          | 3.5           | 4                 | 4              | 4                  | 0.9625  |
| Grok4_0709           | 3             | 4                 | 4              | 4                  | 0.925   |
| GPT51_1113           | 3             | 4                 | 4              | 3.75               | 0.9125  |
| GPT51_1113_high      | 3             | 4                 | 4              | 3.75               | 0.9125  |
| Grok41_FastReasoning | 3.5           | 4                 | 3              | 4                  | 0.9125  |
| Claude_Haiku_45      | 3             | 4                 | 3.5            | 4                  | 0.9     |
| GPT5_Codex           | 3             | 3.5               | 3.75           | 3.75               | 0.8625  |
| Grok4FastReasoning   | 2.5           | 3                 | 4              | 4                  | 0.8125  |
| GPT51_Codex_mini     | 3             | 2                 | 2.5            | 3                  | 0.65    |
| MiniMaxM2            | 2             | 1.5               | 3.5            | 3.5                | 0.6125  |
| Grok41_Fast          | 2             | 1.5               | 3              | 3                  | 0.5625  |
| GPT5_Mini_high       | 1             | 1                 | 4              | 4                  | 0.55    |
| GPT5_Nano_high       | 0             | 1                 | 3.5            | 3.5                | 0.425   |
| AmazonNovaPremier    | 0             | 1                 | 2.5            | 2.75               | 0.3375  |
| GPT_OSS_120B         | 0             | 0                 | 3.5            | 3                  | 0.325   |

_Table 5. LCIF results of LLMs in EPAM's LLMs Benchmark._

## Conclusion

The benchmark results reveal significant insights about current LLM capabilities for software engineering tasks:

**Market Leadership**
GPT-5.1 (11-13) establishes a new benchmark record with 83.96% total score (high reasoning variant) and 83.36% (regular variant), surpassing all previous models. The high reasoning variant achieves
balanced performance across all categories (code translation: 84.71%, code generation: 78.96%, documentation: 80.92%, LCIF: 91.25%), claiming first place in code documentation. The regular variant
delivers nearly identical performance with significantly better efficiency (68.46 min execution vs. 171.48 min, 78.94 tokens/sec vs. 72.66 tokens/sec, $3.64 cost vs. $7.87), demonstrating that
extended reasoning provides minimal improvement in coding tasks (0.6 percentage points) while substantially increasing cost and execution time. Both variants show solid LCIF performance (91.25%),
though reasoning mode impacts agent-focused tasks negatively compared to other categories.

Claude Opus 4.5 achieves 83.18% total score, securing third place and representing Anthropic's first cross-platform flagship model available on all major cloud providers (Google Vertex AI, Azure, AWS,
Anthropic API). The model delivers strong performance across categories (code translation: 82.83%, code generation: 73.96%, documentation: 77.42%, LCIF: 98.50%), claiming tied first place in LCIF
alongside Grok Code Fast. With execution time of 142.09 min and cost of $17.08, Opus 4.5 positions as Anthropic's premium offering for organizations requiring maximum capability across diverse cloud
platforms. Pricing was reduced from $15/$75 to $5/$25 per MTok, making the flagship model significantly more accessible while maintaining top-tier performance.

Claude Sonnet 4.5 achieves 82.19% total score in fourth position, demonstrating exceptional balanced performance across all categories without requiring reasoning mode. Claude Sonnet 4.5 achieves
second place in code documentation (79.53%), strong code generation (75.92%), and maintains excellent LCIF performance (96.25%).

Claude Haiku 4.5 emerges as a remarkable achievement, securing fifth place with 81.83% total score while representing Anthropic's smaller, cost-effective model tier. The model achieves second place in
code documentation (80.64%), strong code translation (82.63%), and solid code generation (74.04%). With exceptional speed (180.66 T/S) and competitive pricing ($1/$5 per MTok), Claude Haiku 4.5 offers
premium performance at mid-tier cost, making it an excellent choice for high-volume coding applications.

OpenAI maintains strong presence across multiple model tiers. GPT-5.1 provides new benchmark-leading performance with best code translation (84.71% high reasoning, 84.17% regular), while GPT-5.1
Codex (78.72% total score, 7th place) and GPT-5 Codex (77.25%) represent specialized coding-focused models. GPT-5.1 Codex achieves strong code generation (79.15%) and excellent LCIF (96.25%, tied
3rd), but experiences significant operational issues: extremely slow LCIF execution (~90 min vs typical 10 min) causing total execution time of 197.44 min, and frequent tool call errors with repeated
file reads/writes. The model performs better in multimodal tasks (79.94%, 2nd place) where these tool handling limitations are less critical. GPT-5.1 Codex mini (61.58%, 16th place) shows similar tool
handling issues with weaker overall performance (code generation: 53.38%, documentation: 57.42%, LCIF: 65.00%), but interestingly outperforms in multimodal benchmark (77.75%, 4th place). GPT-5 Codex (
77.25%) serves as a more stable specialized agentic coding model that excels in code generation (81.42%) and code translation (81.67%) with better operational reliability. GPT-5 Mini (71.28%)
demonstrates strong code translation (80.92%) and documentation (78.64%) despite weak LCIF performance (55%), while GPT-5 Nano (58.61%) offers ultra-low-cost operations ($0.33) but with significant
performance limitations. GPT-5 Nano's LCIF failure (42.50%) reveals a unique pathology: the model dedicates ~95% of output tokens to reasoning rather than actual output (e.g., 55,000 reasoning tokens
out of 57,000 total), a behavior unique to Nano that demonstrates reasoning inefficiency rather than capability. These models demonstrate OpenAI's comprehensive approach to software engineering AI,
with GPT-5.1 providing benchmark-leading excellence, Codex variants offering specialized capabilities with varying degrees of operational stability, GPT-5 Mini providing mid-tier cost-effective
performance, and GPT-5 Nano serving budget-conscious deployments with limited LCIF capability.

**Anthropic's Model Evolution**
The Claude model family shows remarkable evolution across both flagship and smaller model tiers. Claude Sonnet 4.5 (82.19%) represents a significant leap over Claude 4 Sonnet (75.68%), with
improvements across all coding categories. Claude Haiku 4.5 demonstrates that Anthropic has successfully brought flagship-level capabilities to smaller models, achieving 81.83% score with Sonnet-like
behavior and quality while maintaining exceptional speed and cost-effectiveness. The data reveals that reasoning mode consistently reduces coding performance across the Claude 4 line (base: 75.68% vs.
thinking: 73.73%), while both Claude Sonnet 4.5 and Haiku 4.5 achieve top performance without requiring reasoning mode. This suggests Anthropic has successfully integrated advanced reasoning
capabilities directly into the base architecture across their model lineup, eliminating the performance penalty previously associated with explicit
reasoning modes.

**xAI's Competitive Performance and Efficiency Breakthrough**
xAI demonstrates significant advancement with Grok 4 Fast achieving 79.45% score, positioning it as a strong contender in the coding benchmark. This model delivers exceptional cost-effectiveness
at $0.22 with faster execution time (41.22 min vs. 80.75 min for Grok 4), while maintaining excellent performance across categories. The original Grok 4 (07-09) achieves 73.33% score with solid
performance, while Grok Code Fast delivers 71.74% score with exceptional speed (165.54 tokens/sec) and outstanding cost efficiency ($0.33 total cost). Grok Code Fast particularly excels in LCIF tasks
(98.5% score), making xAI's models excellent choices for budget-conscious organizations requiring fast development cycles.

However, Grok 4.1 models show concerning regression. Grok 4.1 Fast Reasoning (67.90%, 14th place) suffers from a response truncation bug where the model generates reasoning tokens but then abruptly
truncates output after 15-50 tokens with 200 OK status, causing low completeness (0.628) particularly on large contexts with code generation. This bug manifests only on large contexts during code
generation, resulting in critically poor code translation (38.08%) while maintaining acceptable code generation (71.42%), documentation (70.83%), and LCIF (91.25%). Grok 4.1 Fast (60.09%, 17th place)
performs below its predecessor Grok 4 Fast (79.45%) despite version upgrade, requiring multiple LCIF attempts to achieve passing results. Both 4.1 variants demonstrate that newer versions do not
guarantee improvements, with operational issues severely impacting reliability. Grok 4 Fast's 2M token context window and state-of-the-art cost-efficiency make it ideal for large-scale software
engineering projects.

**Google's Mixed Coding Results with Gemini 3**
Gemini 3 Pro Preview achieves 70.25% in coding tasks, showing improvement over earlier Gemini models but reveals severe token generation limitations that critically impact performance. Despite being
allowed 60K token output, the model maxes out at ~12K tokens per response, severely affecting one-shot prompt tasks requiring 20K+ token outputs. This constraint causes weak performance in code
documentation (52.08%) and code generation (58.23%), where large outputs are essential. However, the model excels in code translation (74.42%) and demonstrates exceptional LCIF performance (96.25%,
tied 2nd place) where smaller outputs suffice. The model achieves fast execution (44.32 min, 93.72 T/S) but at higher cost ($3.74), with Google increasing pricing to $
2/$12 for <200K context (up from previous $1.25/$10). Total token generation (249K output, 75K reasoning) remains significantly below Gemini 2.5 Pro's capacity (410K+ output, 150K reasoning), likely
due to preview status restrictions.

The model demonstrates Google's focus on multimodal capabilities, where Gemini 3 Pro Preview achieves 82.54% (top position), significantly outperforming its coding results.

**Open-Source Models**
MiniMax M2 achieves 71.14% as the top-performing open-source model, utilizing an efficient MoE architecture (230B total parameters with 10B active) that excels in code translation (81.63%, 4th place
overall) and agentic tasks with active tool usage. While it demonstrates strong performance in structured coding tasks, the model struggles with LCIF (61.25%) and large content generation, operating
with slower execution (172.20 min, 31.67 T/S) but reasonable cost ($0.49).

gpt-oss-120b achieves 62.19% score with extraordinary speed (555.99 tokens/sec) and ultra-low cost ($0.23), completing all tasks in just 6.71 minutes. While MiniMax M2 offers better quality (+14.4%),
gpt-oss-120b provides faster execution and lower costs, demonstrating that open-source alternatives can deliver competitive performance for organizations seeking cost-effective solutions.

**Key Performance Insights**

- **Speed Champions**: gpt-oss-120b (555.99 T/S), Claude Haiku 4.5 (180.66 T/S), Grok Code Fast (165.54 T/S), Grok 4 Fast (125.84 T/S), Gemini 3 Pro Preview (93.72 T/S)
- **Cost-Effectiveness Leaders**: Grok 4 Fast ($0.22), gpt-oss-120b ($0.23), GPT-5 Nano ($0.33), Grok Code Fast ($0.33), MiniMax M2 ($0.49)
- **LCIF Excellence**: Grok Code Fast (98.5%), Claude Sonnet 4.5 (96.25%), Gemini 3 Pro Preview (96.25%), Grok 4 (92.5%), GPT-5.1 (11-13) (91.25%), Claude Haiku 4.5 (90.0%)
- **Code Translation Leaders**: GPT-5.1 (11-13) (high) (84.71%), GPT-5.1 (11-13) (84.17%), Claude Haiku 4.5 (82.63%), GPT-5 Codex (81.67%), MiniMax M2 (81.63%), GPT-5 Mini (80.92%)
- **Code Generation Leaders**: GPT-5 Codex (81.42%), Grok 4 Fast (80.38%), GPT-5.1 (11-13) (high) (78.96%), GPT-5.1 (11-13) (77.65%), Claude Sonnet 4.5 (75.92%), Claude Haiku 4.5 (74.04%)
- **Code Documentation Leaders**: GPT-5.1 (11-13) (high) (80.92%), Claude Haiku 4.5 (80.64%), GPT-5.1 (11-13) (80.39%), Claude Sonnet 4.5 (79.53%), GPT-5 Mini (78.64%), Grok 4 Fast (78.39%)

**Organizations Recommendations**

- **Maximum Quality**: GPT-5.1 (11-13) for top overall coding performance (83.36% with excellent cost/speed balance at $3.64), Claude Sonnet 4.5 for strong balanced performance (82.19%)
- **High-Performance Budget Option**: Claude Haiku 4.5 for premium performance at mid-tier pricing (81.83%), excellent for high-volume coding applications with second-place code documentation
- **Balanced Performance**: GPT-5.1 (11-13) offers the best balance of quality and capability across all coding categories (83.36%), Claude Sonnet 4.5 for strong balanced performance (82.19%)
- **Cost-Effective Excellence**: Grok 4 Fast for outstanding performance with exceptional cost efficiency ($0.22), GPT-5 Mini ($1.38) for mid-tier cost-effective
- **Speed & Budget**: Grok Code Fast for rapid development cycles with minimal expenses, Claude Haiku 4.5 for speed with quality, gpt-oss-120b for fastest execution
- **Open-Source**: MiniMax M2 for quality-focused applications (71.14%, strong code translation and agentic tasks), gpt-oss-120b for speed-critical and budget-constrained deployments
- **Specialized Coding**: GPT-5 Codex for complex software engineering tasks requiring iterative problem-solving and dynamic thinking adjustment

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    This report is licensed under CC BY-SA 4.0
</p>