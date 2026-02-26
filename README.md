# Explainable Duplicate Detection Agent for Data Quality
**We built an AI agent on Elasticsearch that doesn’t just detect duplicates—it explains decisions, recommends actions, and automates data quality workflows**

## 📌 Overview Goal
This project is an **Explainable Duplicate Detection Agent** designed to improve **data quality** by detecting duplicate customer/person records stored in **Elasticsearch**.

Instead of only giving a similarity score, the agent provides:
- Field-level match explanation
- Confidence score
- Recommended action (MERGE / REVIEW / IGNORE)

This makes duplicate detection **transparent, auditable, and easy for business teams**.

--- 
## 🔍 The Real Problem
Today:
Dedupe systems silently merge or flag records
Ops teams don’t know why
Audits, complaints, and rollbacks happen late
Most dedupe systems:
Say “duplicate found”
But NEVER say why

Business users, QA teams, and auditors hate that.

## 🚀 Key Features
✅ Detect duplicate customer records  
✅ Explainable output (why records are duplicates)  
✅ Confidence scoring system  
✅ Uses Elastic ES|QL + DSL queries  
✅ Suggests MERGE / REVIEW / IGNORE actions  
✅ Generates merged master record preview  
✅ Helps improve enterprise data quality workflows  

---

## 🧠 How the Agent Works
### Step-by-step flow:
1. User asks query (natural language or field-based)
2. Agent fetches candidate records from Elasticsearch
3. Agent compares fields:
   - name similarity
   - email match
   - phone match
   - address similarity
4. Agent generates:
   - confidence score
   - explanation of matched fields
   - action recommendation
5. If merge recommended, agent generates a master record

   **Agent Reasoning Example**
User:
Why were these two customer records marked as duplicates?

**Agent Response:**

94% phonetic match on name 
Same PAN hash
Address similarity across 3 components
Appeared in same ingestion window
Similarity threshold exceeded (0.88 > 0.85)

✅ Transparent
✅ Auditable
✅ Trustworthy

---
## 🤖 LLM Support
This agent is **LLM-agnostic** and can work with any supported Large Language Model (LLM) integrated into Elastic Agent Builder.

Examples:
- OpenAI GPT models
- Azure OpenAI
- Anthropic Claude
- Local/self-hosted LLMs (if connected)

The LLM is used to generate human-readable explanations and final recommendations, while Elasticsearch handles fast retrieval and candidate search.
-----

## 🛠 Tech Stack
- Elasticsearch
- ES|QL
- DSL Query Search
- Bulk API (data loading)/grounded in elastic data
- Elastic Agent Builder (workflow orchestration)

---
## Automation of a clear business task ✅
The business task:

Automating duplicate record review and decision explanation

Real‑world relevance:

CRM systems
Banking KYC
Support systems
Sales ops

Before agent:

Manual querying
Manual comparison
No explanations

After agent:

One command → duplicate check → explanation → recommendation

✅ Clear productivity improvement.



 Automates a clear business task

Must automate a real‑world task or improve productivity.

Your business task is clear and strong: ✅

Task: Duplicate record detection + explanation
Users: Data quality teams, KYC, CRM, Ops
Value:

Reduces manual review
Prevents wrong merges
Improves auditability
Saves time

 ## License
This project is licensed under the Apache License 2.0.


✅ This fits “Automate messy internal work” perfectly
