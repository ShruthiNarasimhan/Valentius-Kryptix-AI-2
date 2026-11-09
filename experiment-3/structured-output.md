# Experiment 3: Structured JSON Output

## 1. Objective

To evaluate the ability of an LLM to extract structured information from unstructured invoice descriptions and generate valid JSON according to a predefined schema.

The experiment also examines how schema modifications improve the handling of missing information.

## 2. Experimental Setup

- Model: Google Gemini (verify exact model version)
- Platform: Google AI Studio
- Task: Invoice Information Extraction
- Dataset Size: 5 invoice descriptions
- Output Format: JSON
- Technique: Structured Outputs using JSON Schema

## 3. Required JSON Structure

The model was instructed to extract the following fields:

- `invoice_number`
- `customer_name`
- `invoice_date`
- `amount`

The output was expected to contain all four fields.

## 4. Test Dataset

**Test Case 1**

Invoice INV-1025 was issued to Rahul Sharma on 5 November 2026 for ₹4,500.

**Test Case 2**

Priya Enterprises received invoice VK-204 on 12/11/2026. Total payable: Rs. 8,750.50.

Date interpretation: DD/MM/YYYY.

**Test Case 3**

Bill number 3098, dated 15 October 2026, issued to Arjun Kumar. Amount due is ₹1,299.

**Test Case 4**

Invoice INV-778 was generated on 20 November 2026 for customer Meena Raj.

Missing information: Amount.

**Test Case 5**

The invoice amount is ₹6,200. The buyer is Karthik. The invoice reference is INV-990.

Missing information: Invoice date.

## 5. Initial Schema Experiment

The initial schema used non-nullable fields.

### Initial Results

| Test Case | Result | Observation |
|---|---|---|
| T1 | Successful after date-format correction | Date initially returned in natural-language format |
| T2 | Successful | All required information extracted |
| T3 | Successful | All required information extracted |
| T4 | Failed | Missing amount returned as 0 |
| T5 | Failed | Missing date returned as an empty string |

**Initial Success Rate:**

3 / 5 × 100 = 60%

### Initial Experiment Analysis

The initial schema handled complete invoice descriptions correctly.

However, it did not handle missing information as expected. For T4, the model returned 0 instead of null. For T5, it returned an empty string instead of null.

This showed that the initial schema needed better missing-value handling.

## 6. Improved Schema Experiment

The schema was modified to allow nullable values for all four fields.

The prompt was also updated to specify that invoice dates must use the `YYYY-MM-DD` format.

### Improved Results

| Test Case | Expected Behaviour | Result |
|---|---|---|
| T1 | Extract all fields with ISO date | Successful |
| T2 | Extract all fields with ISO date | Successful |
| T3 | Extract all fields with ISO date | Successful |
| T4 | Return null for missing amount | Successful |
| T5 | Return null for missing date | Successful |

### Actual JSON Outputs for Missing-Value Cases

**Test Case 4: Missing Amount**

```json
{
  "invoice_number": "INV-778",
  "customer_name": "Meena Raj",
  "invoice_date": "2026-11-20",
  "amount": null
}
```

**Test Case 5: Missing Invoice Date**

```json
{
  "invoice_number": "INV-990",
  "customer_name": "Karthik",
  "invoice_date": null,
  "amount": 6200
}
```

**Improved Success Rate:**

5 / 5 × 100 = 100%

## 7. Comparison of Results

| Metric | Initial Schema | Improved Schema |
|---|---:|---:|
| Total Test Cases | 5 | 5 |
| Successful Cases | 3 | 5 |
| Failed Cases | 2 | 0 |
| Success Rate | 60% | 100% |

## 8. Techniques That Improved Reliability

The following changes improved the results:

1. **Nullable Fields:** Allowed missing invoice information to be represented using null instead of an incorrect default value.
2. **Explicit Date Formatting:** Specifying YYYY-MM-DD improved date consistency.
3. **Structured Output Schema:** Defined the expected fields and data types to maintain a consistent JSON structure.

## 9. Observations

- Structured outputs helped maintain a consistent JSON format.
- Non-nullable fields caused problems when invoice information was missing.
- Nullable fields improved missing-value handling in the tested cases.
- Explicit date-format instructions improved consistency.
- The improved configuration successfully handled all five test cases.

## 10. Conclusion

The initial schema achieved a 60% success rate, while the improved nullable schema achieved 100% on the same five test cases.

This experiment demonstrated the importance of appropriate schema design and clear prompt instructions when extracting structured information using LLMs.

The results also highlighted how iterative testing and schema improvements can increase output reliability.