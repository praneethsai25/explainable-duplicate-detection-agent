# Explainable Duplicate Detection Agent Instructions

## 🎯 Goal
Detect duplicate customer/person records in Elasticsearch and provide explainable reasoning behind the duplicate decision.

---
## 🤖 LLM Usage
This agent can use **any LLM** available in Elastic Agent Builder to generate:
- reasoning explanations
- confidence interpretation
- merge/review recommendations

The duplicate detection workflow remains the same regardless of the LLM used. Elasticsearch performs retrieval and similarity candidate search, while the LLM provides explainable output.


## 🧾 User Input Examples
The agent accepts requests like:

- "Find duplicates for Praneeth Kumar"
- "Check duplicate entries for phone 9999999999"
- "Find duplicate leads with email sanjana@gmail.com"
- "Show similar records for Ravi"

---

## 🔍 Candidate Search Logic
The agent searches candidates using:
- Exact matches on keyword fields (email, phone)
- Fuzzy search on name/address fields
- Combined field search using bool queries

---

## 📊 Duplicate Scoring Rules
The agent assigns a confidence score from 0 to 1.

### Field Weights
| Field | Condition | Weight |
|------|----------|--------|
| Email | Exact match | +0.50 |
| Phone | Exact match | +0.40 |
| Name | Fuzzy similarity | +0.20 |
| Address | Partial match | +0.15 |
| City/State | Match | +0.10 |

Max score is capped at 1.0.

---

## 🧠 Confidence Score Interpretation
| Score Range | Meaning | Action |
|------------|---------|--------|
| 0.85 - 1.00 | Highly likely duplicate | MERGE |
| 0.65 - 0.84 | Possible duplicate | REVIEW |
| 0.00 - 0.64 | Not duplicate | IGNORE |

---

## 🧾 Explainable Output Format
The agent always outputs:

- Record A and Record B
- Confidence Score
- Matched Fields
- Reason (human readable)
- Recommended Action
- Suggested Master Record (if MERGE)

---

## 🧩 Example Agent Response
```json
{
  "record_a": "C001",
  "record_b": "C002",
  "confidence_score": 0.94,
  "matched_fields": [
    "email exact match",
    "phone exact match",
    "name similar",
    "address similar"
  ],
  "recommendation": "MERGE",
  "reason": "Both records share identical email and phone number, with similar name and address.",
  "merged_master_record": {
    "name": "Praneeth Kumar",
    "email": "praneeth@gmail.com",
    "phone": "9999999999",
    "address": "MVP Colony Road",
    "city": "Vizag",
    "state": "AP"
  }
}
