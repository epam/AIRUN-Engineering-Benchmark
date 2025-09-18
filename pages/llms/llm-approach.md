# LLMs Benchmark Approach

## Table of Contents

1. [Vocabulary](#vocabulary)
2. [Methodology](#methodology)
3. [Experiment Categories and Scenarios](#experiment-categories-and-scenarios)
    - [Code Generation](#code-generation)
    - [Code Translation](#code-translation)
    - [Code Documentation Generation](#code-documentation-generation)
    - [Large Context Instructions Following](#large-context-instructions-following)
4. [Research Questions](#research-questions)
5. [Data Collection and Preparation](#data-collection-and-preparation)
    - [JavaScript Dataset](#javascript-dataset)
        - [Normalization and Categorization](#normalization-and-categorization)
        - [Final set of tests](#final-set-of-tests)
6. [Results Evaluation](#results-evaluation)
    - [Quality metrics](#quality-metrics)
    - [Final score formula](#final-score-formula)
    - [On Completeness and Accuracy](#on-completeness-and-accuracy)
    - [Automatic Evaluation](#automatic-evaluation)

## Vocabulary

LLM
: Large Language Model

Prompt
: A specific instruction or query given to a Large Language Model to elicit a desired response or output, such as
generating code, translating between programming languages, or providing explanations for software engineering tasks.

Dataset
: A collection of code samples or repositories used as input for testing scenarios, typically categorized by complexity
and size, to evaluate the performance of LLM across various software engineering tasks.

Template
: A pre-defined structure or format used to create consistent prompts or scenarios for testing Large Language Models,
ensuring standardized input across different tests and models.

Category
: A group of related experiments or tasks designed to evaluate specific aspects of LLM's performance in software
engineering, such as code generation, code translation, documentation generation, or instructions following.

Scenario
: A specific software engineering task described in the form of a template and datasets applicable to this task. It is
designed to evaluate the performance of LLM in areas such as code generation, translation, documentation, or instructions following.

Test
: An individual execution of a scenario using a specific dataset and Large Language Model, designed to assess the
model's performance in a particular software engineering task and generate measurable results for analysis.

Evaluation Criteria
: Specific statements used to assess accuracy or completeness of the generated code or solution.

CI (Cyclomatic complexity index)
: Measures the number of linearly independent paths through a program's source code.

LoC (Lines of Code)
: A metric used to measure the size of a software program or code sample by counting the number of lines in its source
code, often used as one factor in assessing code complexity.

GCI (General Complexity Index)
: Represents a composite metric, synthesized from the individual metrics, serving as an aggregate measure to evaluate
the complexity of code samples.

## Methodology

This study adopts an empirical research methodology to systematically analyze and compare the performance of Large
Language Models (LLMs) in software engineering tasks, namely code translation, code generation, and documentation
generation. The empirical framework is centered around the quantitative analysis of source code metrics and evaluating
model outputs against predefined complexity benchmarks.

Our main repository: https://github.com/epam/AIRUN-LLM-Benchmark

- **Dataset**: Used to store repositories that are used in tests
- **Utils**: Contain all the necessary scripts for automation
- **Scenarios**: Contains all scenarios and templates for running tests

In our internal research repository, we store comprehensive evaluation results organized by LLM, criteria files for result evaluation, and final evaluation outcomes for detailed analysis.

## Experiment Categories and Scenarios

### Code Generation

Generate code snippets, functions, or entire modules based on provided specifications, requirements, or natural language descriptions.

1. Generate React base components and applications
2. Modify existing React applications
3. Create collaborative editors and data visualization dashboards
4. Generate form builder components
5. Write unit tests for both legacy and modern code
6. Create project configurations and templates
7. Generate enterprise application templates
8. Create monorepo templates

### Code Translation

Translate code between programming languages or paradigms.

1. Update React applications to newer versions
2. Update AngularJS applications to newer Angular versions
3. Translate AngularJS code to React
4. Translate React code to Angular
5. Translate vanilla JavaScript to React
6. Translate jQuery code to React

### Code Documentation Generation

Generate and maintain code documentation, including comments, inline documentation, and high-level documentation such as
README files and user manuals.

1. Describe current implementation in the form of technical documentation
2. Evaluate the quality of the given source code
3. Describe business functionality implemented by the provided source code

### Large Context Instructions Following

This experiment evaluates the model's capability to run continuous dialog to perform a complex task in a sequence of
steps. The model must rely on and efficiently use all provided and generated data during the conversation to produce
final results.

This is a critical experiment that demonstrates how models work in multi-step scenarios with large context and how correctly they invoke tools. The experiment uses 5 specialized tools:

1. **list_files** - List all files in the legacy directory
2. **read_file** - Read the content of files from the legacy application
3. **file_structure** - Return the new file structure of the translated application
4. **write_file** - Write converted code to files in the new application
5. **end_task** - End the translation task when complete

Scenarios:

1. Upgrade the React application to the newest version
2. Migrate AngularJS to React application
3. Upgrade Extended React application to React 19

> Note: Experiment categories 1-3 utilize a single-shot approach for interaction with the models. However, the 4th
> experiment category involves a dialogue with the models.

## Research Questions

Our study aims to answer the following questions:

### Code Translation

- How well do LLMs translate code snippets between programming languages?
- Which model provides more accurate and contextually relevant translations?

### Code Generation

- Can LLMs generate high-quality code snippets from natural language prompts?
- How do they handle complex programming constructs and idiomatic expressions?

### Code Documentation Generation

- How well could the models spot and document the issues within the code by LLMs?
- How accurate and complete is the documentation derived from the codebase?

### Large Context Instructions Following

- How well do the models follow the conversation for solving the complex task, which requires multiple steps to
  complete?

## Data Collection and Preparation

Our study utilized datasets compiled from publicly available code repositories, focusing on both front-end and back-end
technologies. Each source code sample underwent rigorous analysis to extract relevant metrics, including Cyclomatic
Complexity, Lines of Code (LOC), and other pertinent factors. To facilitate a holistic assessment of code sample
complexity, we devised a General Complexity Index (GCI). The GCI represents a composite metric, synthesized from
individual metrics, serving as an aggregate measure to evaluate the complexity of code samples.

### JavaScript Dataset

This dataset focuses on three prominent front-end technologies: JavaScript, Angular, and React. It includes a variety of
components and applications, ranging from simple UI elements to more complex interactive systems.

Link to dataset in Repository - https://github.com/epam/AIRUN-LLM-Benchmark/tree/main/Dataset/JS

| Name                     | Description                                                                                                                                                      | CI  | LoC  | GCI    |
|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|------|--------|
| ReactAlgorithmVisualizer | The code is written in a slightly outdated version of React, implementing dashboard with visual representation of different algorithms.                          | 631 | 3055 | 0.21   |
| ReactSelect              | The code is written in a recent version of React, it is a Select component with the ability to multi-select and search for values and has accessibility support. | 439 | 2246 | 0.1955 |
| AngularMeteo             | The code is written in a recent version of Angular, rendering dashboard with historical weather data.                                                            | 113 | 624  | 0.18   |
| ToDoApp_ReactJS          | The code is written using class components on an outdated version of React, an interaction with local storage is used.                                           | 83  | 473  | 0.1755 |
| ReactSignUp              | The code is written using class components on an outdated version of React, has form validations, and connects with redux.                                       | 31  | 177  | 0.1751 |
| AngularCalendar          | Demo project of using FullCalendar library in AngularJS                                                                                                          | 119 | 696  | 0.1710 |
| ToDoApp_jQuery           | The code is written in jQuery; it has the CRUD functionality of todos, and todos are stored inside the app.                                                      | 44  | 263  | 0.1673 |
| ReactFetchAPI            | The code is written in a recent React version, it fetches data and shows it in a list                                                                          | 6   | 39   | 0.1538 |
| AngularCosmoPage         | Part of the Cosmo CMS system responsible for building pages                                                                                                      | 82  | 570  | 0.1439 |
| ReactPodcastItem         | The code is written using class components on an outdated version of React, has form validations, and connects with redux.                                       | 29  | 200  | 0.1422 |
| AngularCosmoMenu         | Part of the Cosmo CMS system responsible for creating menu                                                                                                       | 38  | 276  | 0.1377 |
| ToDoApp_AngularJS        | The code is written using outdated version of AngularJS, using local storage to store data                                                                       | 37  | 277  | 0.1336 |
| ReactSearchJob           | Code is written in an outdated version of React that uses an API to get vacancies from aggregator, has 3 routes (main page, list of vacancies and vacancy detail)    | 137 | 992  | 0.14   |
| Piano_NativeJS           | The code is written using Native JS. User can play on piano via clicking by mouse or using keyboard                                                              | 15  | 135  | 0.1111 |
| ReactBookmarks           | The code is written using class components on an outdated version of React, has redux and functionality to bookmark podcasts                                     | 57  | 515  | 0.1107 |
| AngularCosmoAdmin        | Part of the Cosmo CMS system responsible for managing pages                                                                                                      | 17  | 205  | 0.0829 |
| ReactNavbar              | The code is written using class components on an outdated version of React                                                                                       | 8   | 150  | 0.0533 |

Sources of some applications:

- https://github.com/CosmoCMS/Cosmo
- https://github.com/danjac/podbaby
- https://github.com/tastejs/todomvc/tree/master/examples/typescript-react/js
- https://github.com/tastejs/todomvc/tree/master/examples/typescript-angular/js
- https://github.com/tastejs/todomvc/tree/master/examples/jquery

#### Normalization and Categorization

To ensure comparability across diverse code samples, the collected metrics were normalized and scaled within the range
of (0,1]. Subsequently, the code samples were stratified into three complexity categories—low, average, and high—based
on their Cyclomatic Complexity and LOC. The classification thresholds were established as follows: for LOC, low
complexity was defined as fewer than 200 lines, average complexity as more than 200 but fewer than 500 lines, and high
complexity as more than 500 lines. Cyclomatic Complexity was categorized as low for values up to 0.11, average for
values greater than 0.11 but less than 0.17, and high for values exceeding 0.17.

| Complexity/Size | Low                                                                                                    | Avg                                                                          | High                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|---------------------------------------------|
| Low             | • ReactNavbar<br>• Piano_NativeJS<br>• AngularCosmoAdmin                                               | • ReactBookmarks                                                             |                                             |
| Avg             | • ReactPodcastItem<br>• ReactFetchAPI<br>• AngularCosmoMenu<br>• ToDoApp_AngularJS<br>• ReactSearchJob | • AngularCosmoPage                                                           |                                             |
| High            | • ReactSignUp                                                                                          | • ToDoApp_ReactJS<br>• ToDoApp_jQuery<br>• AngularCalendar<br>• AngularMeteo | • ReactSelect<br>• ReactAlgorithmVisualizer |

#### Final set of tests

During the execution of our tests, we observed that the quality of results was more significantly influenced by the size
of the initial dataset rather than its complexity. In light of this finding, we refined our selection process to
identify the most suitable dataset for our experiments.

This refined dataset ensures a more accurate evaluation of LLM performance across various software engineering tasks,
with a particular focus on the impact of code size on model outputs. By standardizing our test suite in this manner, we
aim to provide more consistent and meaningful results in our assessment of LLM capabilities in code generation,
translation, and documentation tasks.

Our final test suite was curated as follows:

| Category                                 | Scenario                                 | Datasets                                                                                               |
|------------------------------------------|------------------------------------------|--------------------------------------------------------------------------------------------------------|
| **Code Generation**                      |                                          |                                                                                                        |
| component generation                     | Generate Base Component                  | Not needed                                                                                             |
|                                          | Generate React App                       | Not needed                                                                                             |
|                                          | Generate Collaborative Editor            | Not needed                                                                                             |
|                                          | Generate Data Visualization Dashboard    | Not needed                                                                                             |
|                                          | Generate Form Builder Component          | Not needed                                                                                             |
|                                          | Modify React App                         | ReactFetchAPI                                                                                          |
| test generation                          | Write Tests For Actual Code              | ReactSelect                                                                                            |
|                                          | Write Tests For Legacy Code              | AngularCosmoPage, ReactSignUp, ToDoApp_ReactJS                                                         |
| solution template generation             | Generate Project Configuration           | Not needed                                                                                             |
|                                          | Generate Enterprise Application Template | Not needed                                                                                             |
|                                          | Generate Monorepo Template               | Not needed                                                                                             |
| **Code Translation**                     |                                          |                                                                                                        |
| solution migration                       | Update Angular                           | ToDoApp_AngularJS                                                                                      |
|                                          | React To Angular                         | ToDoApp_ReactJS, ReactSignUp, ReactAlgorithmVisualizer, ReactSearchJob                                 |
|                                          | Update React                             | ToDoApp_ReactJS, ReactAlgorithmVisualizer, ReactSearchJob                                              |
|                                          | Angular To React                         | AngularCosmoPage, AngularMeteo                                                                         |
|                                          | Vanilla To React                         | Piano_NativeJS                                                                                         |
|                                          | jQuery To React                          | ToDoApp_jQuery                                                                                         |
| **Code Documentation**                   |                                          |                                                                                                        |
| code explanation                         | Describe Technical Implementation        | AngularCosmoPage, ReactSignUp, ToDoApp_ReactJS, AngularMeteo, ReactAlgorithmVisualizer, ReactSearchJob |
| solution documentation                   | Business Functionality                   | AngularCosmoPage, ReactSignUp, ToDoApp_ReactJS, AngularMeteo, ReactAlgorithmVisualizer, ReactSearchJob |
| code analysis                            | Evaluate Code Quality                    | AngularCosmoPage, ReactSignUp, ToDoApp_ReactJS, AngularMeteo, ReactAlgorithmVisualizer, ReactSearchJob |
| **Large Context Instructions Following** |                                          |                                                                                                        |
| contextual experiment                    | Upgrade React Application                | ToDoApp_ReactJS                                                                                        |
|                                          | Migrate AngularJS to React               | ToDoApp_AngularJS                                                                                      |
|                                          | Upgrade Extended React to React 19       | Extended React Application                                                                             |

## Results Evaluation

The core of our methodological approach was evaluating LLM performance across the specified software engineering tasks.
The accuracy of code translation by LLMs from one programming language to another necessitated a multi-faceted
evaluation criterion that included syntax correctness, semantic integrity, and the preservation of logical structures.
This was quantitatively represented through a numeric correctness scale. Additionally, the experiments aimed to assess
the improvement and efficiency of LLM-generated outputs relative to the original code samples. This involved comparing
the GCI of both the input and the LLM-transformed code, thereby concluding enhancements or regressions in inherent code
complexity. This methodological framework underpins our analysis, enabling a structured evaluation of LLM capabilities
in the context of software engineering efficiency optimization.

### Quality metrics

Our evaluation approach uses two distinct methodologies:

**LLM-as-a-Judge Evaluation (Primary Method)**
For code generation, translation, and documentation scenarios, we employ an automated evaluation system using three state-of-the-art models as judges: GPT-5, Claude 4 Sonnet, and Gemini 2.5 Pro. Each
judge evaluates model outputs against predefined criteria files containing specific accuracy and completeness requirements.

The evaluation process works as follows:

1. Each scenario has a corresponding YAML criteria file with weighted evaluation steps
2. Judges assess how well the model output satisfies each criterion
3. Results are converted to percentages (e.g., 9 out of 10 criteria met = 90%)
4. Three judge scores are averaged for final accuracy and completeness metrics

**Human Evaluation (LCIF Only)**
For Large Context Instructions Following scenarios, human evaluators assess results on a 0-4 scale for both accuracy and completeness due to the complex, multi-step nature of these tasks.

The LCIF evaluation uses weighted scoring based on task complexity:
- Tasks 1 and 2 each carry 20% weight (40% combined)
- Task 3 carries 60% weight due to higher complexity

Weighted calculation:
```
LCIF_Accuracy = ((Task1_Accuracy + Task2_Accuracy) / 2) × 0.4 + Task3_Accuracy × 0.6
LCIF_Completeness = ((Task1_Completeness + Task2_Completeness) / 2) × 0.4 + Task3_Completeness × 0.6
```

**Final Score Calculation**
The overall benchmark score combines results from all four experiment categories:

```
Final Score = ((translate_accuracy + translate_completeness) / 2 +
               (generate_accuracy + generate_completeness) / 2 +
               (document_accuracy + document_completeness) / 2 +
               (LCIF_accuracy / 4 + LCIF_completeness / 4) / 2) / 4
```

Note: Generation rate and attempt number metrics are no longer used in the final evaluation.

For evaluating the correctness of code generation, documentation, and translation performed by Large Language Models (
LLMs) from one programming language to another, the scale must account for syntax correctness, semantic integrity, and
the preservation of logical structures.

1. **Accuracy**

This metric shows that this response conforms to the following criteria:

- code is compiled
- code is translated or generated following the instructions provided to the model
- code doesn't contain incorrect implementation
- code corresponds to the best programming practices (no hard coding, dependency injection is used, no bad patterns like
  singletons)

Below is a numeric representation of accuracy:

- Not Accurate (1): Tasks were not solved at all.
- Partially Accurate (2): The output gets some parts of the code right, making it work in a few cases. However, it
  misses the mark on more complex parts, like understanding the main points but not the whole story.
- Almost Accurate (3): The code is pretty good and works in most situations.
- Accurate (4): The output is spot-on, keeping the code working perfectly in the new language just like it did in the
  original for code translation scenarios, or the LLM output correctly follows all the task instructions for other
  experiment categories.

2. **Completeness**

This metric shows that code solves the problem manifested for component generation, test creation, AGO, refactoring, bug
fixing, optimization, dev ops, and migration.

Below is a numeric representation of completeness:

- None (1): The code does not solve the problem manifested at all, lacking any meaningful contribution to addressing the
  task requirements.
- Partially Complete (2): The code partially solves the problem manifested, addressing some aspects while missing key
  components or functionalities.
- Almost Complete (3): The code adequately solves the problem manifested, with only minor gaps or oversights in handling
  certain aspects of the task.
- Completely (4): The code fully addresses the problem manifested for a specific task or scenario, covering all aspects
  and requirements.

Note: Generation rate and attempt number metrics were used in previous versions but are no longer part of the evaluation methodology.

### Final score formula

We calculated the total score for each experiment category for each model.

Score calculation varies by evaluation method:

**LLM-as-a-Judge Scenarios (Generation, Translation, Documentation):**

- Accuracy and Completeness scores are calculated as percentages based on criteria satisfaction
- Category Score = (Accuracy + Completeness) / 2

**LCIF Scenarios:**

- Human evaluators score on 0-4 scale
- Normalized_Accuracy = Average<Accuracy>/4
- Normalized_Completeness = Average<Completeness>/4
- LCIF Score = (Normalized_Accuracy + Normalized_Completeness) / 2

### On Completeness and Accuracy

For our automatic evaluation process it is necessary to establish a more distinct separation between completeness and
accuracy quality metrics.

Completeness is a measure of the extent to which the produced code fulfills functional requirements. In scenarios where
code is generated, these requirements are directly stated in the task prompt. In code translation scenarios, LLM must
deduce these requirements from the original code.

Accuracy is determined by how the code meets non-functional requirements like performance, and complies with
constraints, such as using designated libraries and the requested programming language.

If the code fails to correctly implement the function, it lacks completeness. This won't impact accuracy unless a
constraint is violated - for instance, leaving a TODO message rather than implementing the function or making a syntax
error, leading to incorrect function implementation.

In some cases, the code may meet all non-functional requirements and constraints, but not implement the required
functions. This would result in high accuracy but low completeness.

### Automatic Evaluation

Our recent reports introduce a new approach to evaluating test results - an automated method that doesn't rely on
existing evaluation frameworks. This custom approach involves two key stages: evaluation and scoring.

1. **Evaluation Stage**: We use pre-established criteria to analyze test results and generate a detailed evaluation
   report. This stage focuses on assessing two main metrics: Accuracy and Completeness.

2. **Scoring Stage**: The evaluation results are converted to percentages by dividing the number of satisfied criteria by the total number of criteria. For example, if 9 out of 10 criteria are met,
   the score is 90%. This percentage-based approach provides clear, objective scoring without subjective grading.

**Example Criteria Structure:**

```yaml
evaluation_steps:
  accuracy:
    - criteria: Verify package.json contains React 18+ dependencies
      weight: 1.0
    - criteria: Confirm TypeScript interface exists for sound mapping
      weight: 1.0
  completeness:
    - criteria: Verify JSX renders an h1 element containing "Virtual Piano"
      weight: 1.0
    - criteria: Confirm JSX includes "Notes" and "Letters" toggle buttons
      weight: 1.0
```

Read more about automatic evaluation with LLMs on
our [Automated Evaluation with LLMs](automated-evaluation-with-llms.md) page.

<p align="center">
    © 2024 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
</p>