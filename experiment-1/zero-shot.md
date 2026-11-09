# Experiment 1A: Zero-shot Prompting

## 1. Objective

To evaluate the ability of an LLM to classify customer reviews into sentiment categories without providing any labeled examples.

## 2. Experimental Setup

- Model: Google Gemini (verify exact model version)
- Platform: Google AI Studio
- Task: Customer Sentiment Classification
- Dataset Size: 10 customer reviews
- Prompting Technique: Zero-shot Prompting

## 3. Prompt Used

You are a customer review sentiment classification system.

Classify each review into exactly one of the following categories:

- Positive
- Negative
- Neutral

Guidelines:

- Positive: The review expresses satisfaction or a favorable opinion.
- Negative: The review expresses dissatisfaction or an unfavorable opinion.
- Neutral: The review contains factual information without a clear positive or negative opinion.

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

Return only the review ID and its sentiment.

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

Gemini correctly classified all ten customer reviews without receiving any labeled examples.

The model successfully identified positive opinions, negative experiences and neutral factual descriptions.

This indicates that the model was able to understand the classification instructions and apply them to the given dataset without additional examples.

## 7. Conclusion

Zero-shot prompting achieved 100% accuracy on the given dataset.

This experiment demonstrates that an LLM can perform a straightforward sentiment classification task using only clear instructions, without requiring example-based guidance.