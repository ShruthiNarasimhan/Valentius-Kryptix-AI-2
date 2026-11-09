# Experiment 1B: Few-shot Prompting

## 1. Objective

To evaluate whether providing a small number of labeled examples in a prompt improves the performance and consistency of an LLM in customer sentiment classification.

## 2. Experimental Setup

- Model: Google Gemini (verify exact model version)
- Platform: Google AI Studio
- Task: Customer Sentiment Classification
- Dataset Size: 10 customer reviews
- Number of Examples: 3
- Prompting Technique: Few-shot Prompting

## 3. Prompt Used

You are a customer review sentiment classification system.

Classify each review into exactly one category: Positive, Negative, or Neutral.

Here are some examples:

**Example 1:**

Review: "The quality is amazing. I am extremely happy with this purchase."

Sentiment: Positive

**Example 2:**

Review: "The product broke within a week. I regret buying it."

Sentiment: Negative

**Example 3:**

Review: "The box contains a charger, a cable and a user manual."

Sentiment: Neutral

Follow the classification patterns above.

Guidelines:

- Positive: Satisfaction or favorable opinion.
- Negative: Dissatisfaction or unfavorable opinion.
- Neutral: Factual information without a clear positive or negative opinion.

Classify these ten customer reviews:

R1: I absolutely love this product. It works perfectly and exceeded my expectations.

R2: The delivery was quick and the product quality is excellent.

R3: Very easy to use. The setup took only five minutes.

R4: Great value for money. I would definitely recommend it.

R5: The product stopped working after just two days. Very disappointed.

R6: The package arrived damaged and customer support was unhelpful.

R7: Overpriced product with poor battery life. Not worth buying.

R8: The product was delivered on Tuesday morning.

R9: The device has three USB ports and comes with a two-metre cable.

R10: The package contains a device, charger and user manual.

Return only the review ID and sentiment.

Output format:

R1: Positive
R2: Negative
...

## 4. Actual Model Output

R1: Positive  
R2: Positive  
R3: Positive  
R4: Positive  
R5: Negative  
R6: Negative  
R7: Negative  
R8: Neutral  
R9: Neutral  
R10: Neutral

## 5. Evaluation Results

| Metric | Result |
|---|---:|
| Total Reviews | 10 |
| Correct Predictions | 10 |
| Incorrect Predictions | 0 |
| Accuracy | 100% |

**Accuracy = (Correct Predictions / Total Reviews) × 100**

**Accuracy = (10 / 10) × 100 = 100%**

## 6. Observation

Gemini correctly classified all ten customer reviews after receiving three labeled examples.

The examples demonstrated how positive, negative and neutral sentiments should be identified.

Few-shot prompting achieved the same accuracy as zero-shot prompting on this dataset. Since zero-shot prompting had already achieved 100% accuracy, no accuracy improvement was observed.

Further testing with more challenging and ambiguous reviews would help determine whether few-shot examples improve classification performance.

## 7. Conclusion

Few-shot prompting successfully classified all ten reviews with 100% accuracy.

This experiment demonstrated how providing labeled examples can guide an LLM's responses. However, the results also showed that adding examples does not necessarily improve accuracy when the original task is already straightforward.