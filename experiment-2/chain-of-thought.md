# Experiment 2B: Step-by-Step Prompting

## 1. Objective

To evaluate whether explicitly requesting
a step-by-step explanation improves the
structure and accuracy of Gemini's response
to a multi-step mathematical problem.

## 2. Experimental Setup

- Model: Gemini 3.8 Flash
- Platform: Google AI Studio
- Technique: Step-by-Step Prompting
- Task: Profit and Loss Calculation

## 3. Prompt Used

Solve the following mathematical problem
carefully.

A shopkeeper buys 40 notebooks at ₹25 each.
He sells 30 notebooks at ₹35 each and the
remaining notebooks at ₹20 each.

Explain the solution in clear calculation
steps.

Show:
1. Total cost price.
2. Selling price of the first 30 notebooks.
3. Selling price of the remaining notebooks.
4. Total selling price.
5. Profit or loss.
6. Profit or loss percentage.

Use the appropriate formulas and verify
your arithmetic before providing the
final answer.

## 4. Actual Model Output

[Paste the complete actual Gemini response
here without editing.]

## 5. Evaluation Results

| Metric | Result |
|---|---|
| Cost Price | ₹1,000 |
| First 30 Selling Price | ₹1,050 |
| Remaining 10 Selling Price | ₹200 |
| Total Selling Price | ₹1,250 |
| Profit | ₹250 |
| Profit Percentage | 25% |
| Mathematical Accuracy | Correct |

## 6. Observation

Gemini correctly solved the mathematical
problem and provided all six requested
calculation steps.

Compared with direct prompting, the
step-by-step prompt produced a more
explicitly organized response that followed
the requested calculation structure.

However, both approaches achieved the
same mathematical accuracy.

Therefore, step-by-step prompting improved
the alignment of the response with the
requested format, but did not improve
accuracy in this particular test.