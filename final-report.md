# AI-2: Prompt Engineering
## Final Experiment Report

**Organization:** Valentius Kryptix  
**Model:** Google Gemini  
**Platform:** Google AI Studio

---

## 1. Introduction

The objective of this task was to explore different prompt engineering techniques and evaluate their impact on the accuracy, consistency and structure of Large Language Model (LLM) responses.

Three experiments were conducted using Google Gemini.

---

## 2. Experiment 1: Zero-shot vs Few-shot Prompting

**Objective:** Compare sentiment classification performance with and without labeled examples.

**Dataset:** 10 customer reviews.

| Metric | Zero-shot | Few-shot |
|---|---:|---:|
| Correct Predictions | 10/10 | 10/10 |
| Accuracy | 100% | 100% |

**Observation:**

Both techniques achieved the same accuracy. Few-shot prompting provided labeled examples, but did not improve accuracy on this dataset.

**Detailed Experiment Files:**

- [Zero-shot Prompting](./experiment-1/zero-shot.md)
- [Few-shot Prompting](./experiment-1/few-shot.md)

---

## 3. Experiment 2: Direct vs Step-by-Step Prompting

**Objective:** Compare two prompting approaches for solving a multi-step mathematical problem.

**Task:** Profit and Loss Calculation.

| Evaluation | Direct Prompting | Step-by-Step Prompting |
|---|---|---|
| Mathematical Accuracy | Correct | Correct |
| Total Cost Price | ₹1,000 | ₹1,000 |
| Total Selling Price | ₹1,250 | ₹1,250 |
| Profit | ₹250 | ₹250 |
| Profit Percentage | 25% | 25% |

**Observation:**

Both techniques produced correct mathematical results. Step-by-step prompting encouraged a more explicitly organized explanation.

**Detailed Experiment Files:**

- [Direct Prompting](./experiment-2/direct-prompt.md)
- [Step-by-Step Prompting](./experiment-2/chain-of-thought.md)

---

## 4. Experiment 3: Structured JSON Output

**Objective:** Extract invoice information from unstructured text and generate JSON using a predefined schema.

**Dataset:** 5 invoice descriptions.

| Metric | Initial Schema | Improved Schema |
|---|---:|---:|
| Successful Cases | 3/5 | 5/5 |
| Failed Cases | 2/5 | 0/5 |
| Success Rate | 60% | 100% |

**Improvements Applied:**

- Introduced nullable fields to handle missing information.
- Added explicit date-format instructions.
- Used structured output configuration to maintain consistent JSON fields.

**Observation:**

The improved schema successfully handled missing invoice information using null values in all tested cases.

**Detailed Experiment Files:**

- [Structured Output Experiment](./experiment-3/structured-output.md)
- [JSON Schema](./experiment-3/schema.json)

---

## 5. Overall Learnings

- Understood zero-shot and few-shot prompting techniques.
- Explored how examples influence LLM classification.
- Compared direct and step-by-step prompting.
- Learned to configure structured JSON outputs.
- Understood the importance of nullable fields when handling missing information.
- Improved prompt reliability through testing and iterative refinement.

---

## 6. Tools and Technologies

- Google Gemini
- Google AI Studio
- Prompt Engineering
- JSON and JSON Schema
- Visual Studio Code
- Git and GitHub
- Markdown

---

## 7. Conclusion

The experiments provided practical experience with different prompt engineering techniques.

They demonstrated how prompt instructions, examples and schema configuration influence LLM responses. The results also highlighted the importance of evaluating actual outputs, identifying limitations and refining prompts based on experimental observations.

**Task:** AI-2 Prompt Engineering  
**Organization:** Valentius Kryptix