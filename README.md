# EPAM AI/RUN<sup>TM</sup> Engineering Benchmark 🚀

Evaluation of AI-powered solutions in enterprise software development.

[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-BSD3Clause-green.svg)](https://opensource.org/license/bsd-3-clause)

- [What We Solve](#-what-we-solve)
- [Leaderboards](#-leaderboards)
- [Our Approach](#-our-approach)
- [Technologies](#-technologies)
- [Repositories Structure](#-repositories-structure)
- [Contributing](#-contributing)
- [Submission](#-submission)
- [License](#-license)

## 🎯 What We Solve

In the rapidly evolving landscape of LLMs and AI-powered developer tools, we identified a critical need for a comprehensive
benchmark tailored to enterprise software development. Our AI/RUN<sup>TM</sup> Engineering Benchmark addresses this gap by providing:

- Holistic evaluation and comparison of AI Assistants and LLMs
- Focus on real-world enterprise development scenarios
- Comprehensive coverage of software engineering tasks

Before we decided to start working on our benchmark our team explored the ones available on the market. We have realized that are mostly designed around tasks that differ significantly from the everyday challenges faced by developers in enterprise settings. E.g. see more details why the available Code Assistants benchmarks would not show the realistic scores [here](pages/sandbox-test/why-ai-run-benchmark.md).

## 🏆 Leaderboards

Our team runs EPAM AI/RUN<sup>TM</sup> Engineering Benchmark on the most popular Code Assistants and LLMs. The results are updated on the corresponding leaderboards that we update regularly.

View the current rankings and results of LLM's benchmark on our [LLMs Leaderboard](pages/llms/llm-leaderboard.md) and Code Assistants results on [Code Assistants Leaderboard](pages/sandbox-test/code-assistants-agent-leaderboard-2025.md).

## 🔬 Our Approach

We've developed a multi-faceted approach to assess capabilities and performance of AI Assistants and LLMs:

### Code Assistants Benchmark 💻

- Evaluates day-to-day coding tasks
- Covers 11 key categories of software development activities:
    - Non-Proprietary Solution/Component Generation
    - Tests Creation
    - Algorithm Development
    - Data Generation
    - Code Explanation
    - Code Bug Fixing
    - Code Refactoring
    - Solution Documentation
    - Code Optimizations
    - DevOps
    - Solution Migration
- Utilizes both code completion and chat-based scenarios

For more detailed information about our Code Assistants benchmark methodology, please refer to
the following page  [Code Assistants](pages/sandbox-test/code-assistants-benchmark-approach.md).

### LLMs Benchmark 🧠

- Assesses core LLM capabilities in software engineering tasks
- Covers 4 main categories: Code Generation, Code Transformation, Documentation Generation, and Large Context Instructions Following
- A sophisticated scoring system that considers a balanced assessment of the following metrics: Accuracy, Completeness, Generation Rate, Number of Attempts
- Uses LLMs for automated results evaluation based on prepared acceptance criteria

For more detailed information about our benchmark methodology, please refer to
the following page [LLMs](pages/llms/llm-approach.md).

## 🗂 Repositories Structure

### LLM Benchmarking

- [AIRUN LLM Benchmark](https://github.com/epam/AIRUN-LLM-Benchmark): This repository contains scenarios with instructions for LLMs on how to execute different software engineering tasks, evaluation criteria, and utility scripts for automated benchmark execution and evaluation.

- AIRUN LLM Benchmark Results: This repository holds all LLM benchmark run results, criteria for evaluation and reports of LLM evaluations. If you want to see the results of the benchmark, please refer to our team [email address](mailto:SpecialEPM-AIRDAIRUNEngineering@epam.com) 

### LLM Evaluation Framework

- [AIRUN Evaluation Framework](https://github.com/epam/AIRUN-Evaluation-Framework): This repository contains a tool for automatically evaluating and grading Large Language Model (LLM) answers using another LLM as an evaluator.

### AI Code Assistants Benchmarking

- [AIRUN Assistants Benchmark TestInstructions](https://github.com/epam/AIRUN-Assistants-Benchmark-TestInstructions): This repository contains instructions to run tests evaluating AI Code Assistants' performance.

- [AIRUN Assistants Benchmark Codebase](https://github.com/epam/AIRUN-Assistants-Benchmark-CodeBase) and [Codebase Golf Application](https://github.com/PolinaTolkachova/golf-application): These repositories hold different projects with code for common development tasks. These projects are used as playgrounds to run AI development assistant tests.

## 🤝 Contributing

We appreciate all contributions to improve the AI/RUN <sup>TM</sup> Engineering Benchmark. Please see
our [Contribution Guidelines](CONTRIBUTING.md) for more information on how to get involved.

If you have suggestions for new benchmark scenarios or improvements to existing ones, please open an issue or submit a pull request.

## 📝 Submission

The list of LLMs and Code Assistants available on the Leaderboards is built based on the amount of requests from
developers we get. We encourage you to submit your LLM or Code Assistant for our evaluation. Our team will run the
corresponding benchmark tests and add the LLM/Code Assistant to the leaderboard.

To submit your LLM or Code Assistant for evaluation and inclusion in our Leaderboards, please follow these steps:

1. Review the submission requirements:
    - For LLMs: [LLM Submission Guidelines](pages/llms/submissions/llm-benchmark-submission.md)
    - For Code Assistants: [Code Assistant Submission Guidelines](pages/sandbox-test/submissions/assistant-code-submission.md)

2. Create a new branch in this repository.

3. Add a new Markdown (.md) file with information about your model or code assistant. The file should be named according
   to your submission (e.g., `your-model-name.md` or `your-assistant-name.md`) and placed in the appropriate directory
   near instruction file.

4. Fill out the Markdown file following the format and requirements specified in the respective submission guidelines
   linked above. Ensure all required information is included and properly formatted.

5. Create a Pull Request (PR) with your changes and description.

Our team will review your PR, run benchmark tests, and add the LLM or Code Assistant to the
appropriate leaderboard upon approval.

## 📄 License

The code base, documentation including our benchmark approach, test instructions and evaluation criteria are licensed under the [Apache 2.0](/LICENSE).

The leaderboards, detailed reports and analysis are licensed under [CC BY-SA 4.0](/REPORTS-LICENSE)

Our tests use third-party opensource repositories (licensed under MIT, BSD 3-Clause, Apache 2, Eclipse Public License 1.0, Eclipse Public License v2.0, MPL 2.0, ISC). Please refer to the list below for more details [here](third-party-repositories.md).

---

<p align="center">
    © 2024 EPAM Systems, Inc.  All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
    All reports in this repository are licensed under CC BY-SA 4.0
</p>
