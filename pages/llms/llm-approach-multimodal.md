This document outlines details specific to multimodal testing.

## Multimodal Test Overview

Multimodal test evaluate the capabilities of LLM's to recognize elements on screenshots, correlate them with code components, and reason about their behavior and interactions. This benchmark is
designed to measure the model's proficiency in connecting visual representation, application code, and runtime behavior, which is critical for tasks like debugging, performance optimization, and
feature development.

1. Visual Attribute Recognition - model is presented with a screenshot and asked to identify visual attributes of a marked element, such as width, height, color, font size, padding, or border
   properties.
2. Component Mapping - model is tasked with explaining which application component renders the marked element on the screenshot, providing details like filenames, class names, function names, or
   specific lines of code.
3. Data Endpoint Identification - model is asked to determine the data endpoint triggered when the marked element is clicked, including API URLs, request methods, and associated backend logic.
4. Browser Dev Tool Analysis - model is given information from browser developer tools (e.g., selected elements, console errors, HTTP errors) and asked to relate these observations to the
   corresponding application code.
5. Performance Diagnostics - model analyzes issues visible on the browser dev tool performance tab (e.g., slow rendering, high memory usage) and suggests potential problem areas in the code, such as
   inefficient loops, blocking operations, or excessive re-renders.
6. Screenshot Context Understanding - model is tested on its general comprehension of the screenshot's content, including identifying the purpose of the application, the functionality of specific
   elements, and the overall user interface structure.
7. Dynamic Behavior Assessment - model is asked to determine all the changes happening on the webpage when a specific element or area is clicked, such as DOM updates, style changes, triggered events,
   and network requests.

Link to tasks in Repository - https://github.com/epam/AIRUN-LLM-Benchmark/tree/main/Scenarios/Tasks/JS/multimodal

## Multimodal Dataset

This dataset focuses on two front-end technologies: Angular and React.

Link to Angular dataset in Repository - https://github.com/epam/AIRUN-LLM-Benchmark/tree/main/Dataset/JS/AngularMeteo

Link to React dataset in Repository - https://github.com/epam/AIRUN-LLM-Benchmark/tree/main/Dataset/JS/ReactAlgorithmVisualizer

| Name                     | Description                                                                                                                             | CI  | LoC  | GCI  |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|-----|------|------|
| AngularMeteo             | The code is written in a recent version of Angular, rendering dashboard with historical weather data.                                   | 113 | 624  | 0.18 |
| ReactAlgorithmVisualizer | The code is written is a slightly outdated version of React, implementing dashboard with visual representation of different algorithms. | 631 | 3055 | 0.21 |

## Results Evaluation

The multimodal benchmark uses the same LLM-as-a-Judge evaluation methodology as described in the [main benchmark approach](llm-approach.md#quality-metrics). Three state-of-the-art models (GPT-5, Claude 4 Sonnet, and Gemini 2.5 Pro) evaluate outputs against predefined criteria files, assessing two key metrics:

1. **Accuracy** - Primary metric, evaluates whether the model provided accurate answers for the given questions based on visual and code analysis.
2. **Completeness** - Secondary metric with lower weight, assesses whether the model provided comprehensive explanations for the given questions.

For detailed information about the evaluation methodology, criteria structure, and scoring process, please refer to the [Quality Metrics section](llm-approach.md#quality-metrics) in the main approach document.

## Score formula

Score = 0.9 * Accuracy + 0.1 * Completeness

<p align="center">
    © 2025 EPAM Systems, Inc. All Rights Reserved.<br/>
    EPAM, EPAM AI/RUN <sup>TM</sup> and the EPAM logo are registered trademarks of EPAM Systems, Inc.<br>
</p>