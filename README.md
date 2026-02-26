# Explainable Duplicate Detection Agent for Data Quality


## 📌 Overview
This project is an **Explainable Duplicate Detection Agent** designed to improve **data quality** by detecting duplicate customer/person records stored in **Elasticsearch**.

Instead of only giving a similarity score, the agent provides:
- Field-level match explanation
- Confidence score
- Recommended action (MERGE / REVIEW / IGNORE)

This makes duplicate detection **transparent, auditable, and easy for business teams**.

---
## Goal
 **Problem**
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
5. If merge recommended, agent generates a master merged record

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

