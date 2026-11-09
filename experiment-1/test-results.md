# Experiment 1: Zero-shot vs Few-shot Prompting

## 1. Objective

To compare zero-shot and few-shot prompting techniques using Google Gemini for customer sentiment classification.

The experiment evaluates whether providing labeled examples in a prompt improves classification accuracy and consistency.

## 2. Experimental Setup

- **Model:** Google Gemini
- **Platform:** Google AI Studio
- **Task:** Customer Sentiment Classification
- **Dataset Size:** 10 customer reviews
- **Sentiment Categories:** Positive, Negative, Neutral
- **Techniques:** Zero-shot Prompting and Few-shot Prompting

## 3. Dataset

The same ten customer reviews were used in both experiments to ensure a fair comparison.

| Review ID | Customer Review | Expected Sentiment |
|---|---|---|
| R1 | I absolutely love this product. It works perfectly and exceeded my expectations. | Positive |
| R2 | The delivery was quick and the product quality is excellent. | Positive |
| R3 | Very easy to use. The setup took only five minutes. | Positive |
| R4 | Great value for money. I would definitely recommend it. | Positive |
| R5 | The product stopped working after just two days. Very disappointed. | Negative |
| R6 | The package arrived damaged and customer support was unhelpful. | Negative |
| R7 | Overpriced product with poor battery life. Not worth buying. | Negative |
| R8 | The product was delivered on Tuesday morning. | Neutral |
| R9 | The device has three USB ports and comes with a two-metre cable. | Neutral |
| R10 | The package contains a device, charger and user manual. | Neutral |

## 4. Experiment A: Zero-shot Prompting

In zero-shot prompting, the model was asked to classify customer reviews without receiving any labeled examples.

The prompt contained classification instructions and the ten customer reviews.

**Actual Model Output:**

```text
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
```

**Evaluation:**

- Total Reviews: 10
- Correct Predictions: 10
- Incorrect Predictions: 0
- Accuracy: 100%

## 5. Experiment B: Few-shot Prompting

In few-shot prompting, the model was provided with three labeled examples before being asked to classify the same ten customer reviews.

The examples demonstrated positive, negative and neutral sentiment classifications.

**Actual Model Output:**

```text
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
```

**Evaluation:**

- Total Reviews: 10
- Correct Predictions: 10
- Incorrect Predictions: 0
- Accuracy: 100%

## 6. Comparative Analysis

| Evaluation Metric | Zero-shot | Few-shot |
|---|---:|---:|
| Total Reviews | 10 | 10 |
| Correct Predictions | 10 | 10 |
| Incorrect Predictions | 0 | 0 |
| Accuracy | 100% | 100% |
| Labeled Examples Provided | 0 | 3 |

### Accuracy Calculation

Accuracy = (Correct Predictions / Total Predictions) × 100

**Zero-shot:**

Accuracy = (10 / 10) × 100 = 100%

**Few-shot:**

Accuracy = (10 / 10) × 100 = 100%

## 7. Observations

Both zero-shot and few-shot prompting correctly classified all ten customer reviews.

Zero-shot prompting performed successfully without requiring any labeled examples. This demonstrates that clear task instructions can be sufficient for straightforward sentiment classification.

Few-shot prompting also achieved 100% accuracy after receiving three labeled examples. However, it did not improve the accuracy compared with zero-shot prompting because the initial performance was already perfect.

The results indicate that few-shot prompting does not necessarily improve accuracy for every task. Its usefulness may become more apparent with ambiguous reviews, complex classification rules or unfamiliar output patterns.

## 8. Conclusion

The experiment successfully demonstrated and compared zero-shot and few-shot prompting using Google Gemini.

Both techniques achieved 100% accuracy on the selected dataset of ten customer reviews.

Zero-shot prompting achieved the same accuracy without examples, while few-shot prompting provided additional classification examples to guide the model.

Therefore, no measurable accuracy improvement was observed from few-shot prompting in this particular experiment.

Further testing with larger and more ambiguous datasets would help evaluate the differences between these techniques more thoroughly.