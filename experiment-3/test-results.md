# Experiment 3: Structured JSON Output

## 1. Objective

To evaluate the ability of Google Gemini to extract invoice information from unstructured text and return valid JSON following a predefined structure.

The experiment focuses on extracting invoice numbers, customer names, invoice dates and payment amounts while handling missing information correctly.

## 2. Experimental Setup

- **Model:** Gemini 3.8 Flash
- **Platform:** Google AI Studio
- **Task:** Invoice Information Extraction
- **Technique:** Schema-constrained Structured Output
- **Total Test Inputs:** 5
- **Required Output Format:** JSON

## 3. JSON Schema

The JSON schema is defined in the `schema.json` file in this directory.

The output must contain the following four fields:

| Field | Expected Type |
|---|---|
| invoice_number | String or null |
| customer_name | String or null |
| invoice_date | String or null |
| amount | Number or null |

Additional requirements:

- Dates must follow the `YYYY-MM-DD` format.
- Amounts must be numeric values without currency symbols.
- Missing information must be represented using `null`.
- No additional fields are allowed.

## 4. Test Cases and Actual Model Outputs

### Test 1: Normal Invoice

**Input:**

Invoice INV-1025 was issued to Rahul Sharma on 5 November 2026 for ₹4,500.

**Actual Model Output:**

```json
{
  "invoice_number": "INV-1025",
  "customer_name": "Rahul Sharma",
  "invoice_date": "2026-11-05",
  "amount": 4500
}
```

**Result:** Pass

All four fields were extracted correctly.

### Test 2: Different Date and Currency Format

**Input:**

Priya Enterprises received invoice VK-204 on 12/11/2026. Total payable: Rs. 8,750.50.

**Actual Model Output:**

```json
{
  "invoice_number": "VK-204",
  "customer_name": "Priya Enterprises",
  "invoice_date": "2026-11-12",
  "amount": 8750.5
}
```

**Result:** Pass

Gemini correctly interpreted the date as 12 November 2026 and extracted the decimal amount as a numeric value.

### Test 3: Different Wording

**Input:**

Bill number 3098, dated 15 October 2026, issued to Arjun Kumar. Amount due is ₹1,299.

**Actual Model Output:**

```json
{
  "invoice_number": "3098",
  "customer_name": "Arjun Kumar",
  "invoice_date": "2026-10-15",
  "amount": 1299
}
```

**Result:** Pass

Gemini successfully extracted all four fields despite the different wording.

### Test 4: Missing Amount

**Input:**

Invoice INV-778 was generated on 20 November 2026 for customer Meena Raj.

**Actual Model Output:**

```json
{
  "invoice_number": "INV-778",
  "customer_name": "Meena Raj",
  "invoice_date": "2026-11-20",
  "amount": null
}
```

**Result:** Pass

Gemini correctly returned `null` for the missing amount instead of inventing a value.

### Test 5: Missing Date

**Input:**

The invoice amount is ₹6,200. The buyer is Karthik. The invoice reference is INV-990.

**Actual Model Output:**

```json
{
  "invoice_number": "INV-990",
  "customer_name": "Karthik",
  "invoice_date": null,
  "amount": 6200
}
```

**Result:** Pass

Gemini correctly extracted the invoice number, customer name and amount while returning `null` for the missing date.

## 5. Evaluation Criteria

Each output was evaluated using the following criteria:

1. Valid JSON syntax.
2. Presence of all four required keys.
3. Correct data types.
4. Accurate extraction of invoice information.
5. Correct handling of missing information using `null`.

An output was considered successful only if it satisfied all five criteria.

## 6. Evaluation Results

| Test Case | JSON Validity | Extraction Accuracy | Result |
|---|---|---|---|
| T1 | Valid | Correct | Pass |
| T2 | Valid | Correct | Pass |
| T3 | Valid | Correct | Pass |
| T4 | Valid | Correct | Pass |
| T5 | Valid | Correct | Pass |

### Overall Performance

- Total Test Cases: 5
- Successful Outputs: 5
- Failed Outputs: 0

**Success Rate:**

Success Rate = (Successful Outputs / Total Test Cases) × 100

Success Rate = (5 / 5) × 100

**Success Rate = 100%**

## 7. Observations

Google Gemini successfully extracted invoice information across all five test cases.

The model handled different date representations, decimal currency amounts, variations in sentence structure and missing information.

The use of a predefined JSON schema helped constrain the model's responses to the required structure.

An important observation was that Gemini returned `null` for missing invoice fields instead of generating unsupported values.

The experiment demonstrates the usefulness of schema-constrained structured outputs for consistent information extraction from unstructured text.

## 8. Conclusion

The experiment successfully demonstrated schema-constrained structured JSON generation using Google Gemini.

All five test cases produced outputs that matched the configured JSON schema and contained correctly extracted information, resulting in a success rate of 100%.

This experiment highlights the importance of predefined schemas and clear extraction instructions when building reliable LLM-powered information extraction systems.