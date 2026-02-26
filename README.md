# 🧠 Explainable Duplicate Detection Agent for Data Quality


We built an AI-powered agent on Elasticsearch that doesn’t just detect duplicates —  
it explains decisions, recommends actions, and automates data quality workflows.

---

## 📌 Overview

This project is an **Explainable Duplicate Detection Agent** designed to improve enterprise **data quality** by detecting duplicate customer/person records stored in **Elasticsearch**.

Unlike traditional dedupe systems that only return similarity scores, this agent provides:

- ✅ Field-level match explanation  
- ✅ Confidence score (0–1)  
- ✅ Clear recommended action (AUTO-MERGE / MERGE / REVIEW / IGNORE)  
- ✅ Suggested master record (if merge applicable)  

The result is a system that is **transparent, auditable, and business-friendly**.

---

## 🔍 The Real Problem

Today’s dedupe systems:

- Silently merge or flag records  
- Provide no reasoning  
- Create audit and compliance issues  
- Cause operational confusion  
- Increase rollback risks  

Most systems say:

> “Duplicate Found.”

But never explain **why**.

Business users, QA teams, compliance officers, and auditors need transparency.

---

## 🚀 Key Features

✅ Intelligent duplicate detection using Elasticsearch  
✅ Explainable AI-driven reasoning  
✅ Field-weighted confidence scoring system  
✅ Fuzzy + exact match logic  
✅ ES|QL + DSL query integration  
✅ Automated action recommendation  
✅ Master record preview generation  
✅ Enterprise-ready data quality workflow  

---

## 🧠 How the Agent Works

### Step-by-Step Workflow

1. User submits a natural language or structured query  
2. Agent calls Elasticsearch to retrieve candidate records  
3. Agent compares identity fields:
   - Name similarity (fuzzy + phonetic)
   - Email exact match
   - Phone exact match
   - Address similarity
   - Additional identity signals (if available)
4. Agent calculates confidence score (0–1)
5. Agent generates:
   - Field-level explanation
   - Confidence interpretation
   - Recommended action
6. If merge is recommended → Agent generates a master record preview

---

## 🧾 Example Reasoning Output

**User Query:**  
Why were these two customer records marked as duplicates?

**Agent Response:**

- 94% phonetic similarity on name  
- Exact match on PAN hash  
- Address similarity across 3 components  
- Appeared within the same ingestion window  
- Similarity threshold exceeded (0.88 > 0.85)

**Confidence Score:** 0.94  
**Recommended Action:** MERGE  

✔ Transparent  
✔ Auditable  
✔ Trustworthy  

---

## 🤖 LLM Support (LLM-Agnostic Architecture)

This agent is fully **LLM-agnostic** and works with any model supported by Elastic Agent Builder.

Examples:

- OpenAI GPT models  
- Azure OpenAI  
- Anthropic Claude  
- Local / self-hosted LLMs  

Elasticsearch handles fast candidate retrieval.  
The LLM generates explainable reasoning and final decisions.

---

## 🛠 Tech Stack

- Elasticsearch  
- ES|QL  
- DSL Query Search  
- Bulk API (data ingestion)  
- Elastic Agent Builder (workflow orchestration)  
- Vector search (optional for semantic similarity)  

Built and optimized by **Praneeth (Elastic Certified Engineer)**.

---

## 🏢 Business Impact

### 🎯 Business Task Automated:
Duplicate record detection + explanation

### 👥 Target Users:
- Data Quality Teams  
- CRM Teams  
- Banking & KYC Operations  
- Sales Operations  
- Support Systems  
- Compliance & Audit Teams  

---

## 🔄 Before vs After

### ❌ Before Agent
- Manual search queries  
- Manual field comparison  
- No clear explanation  
- Time-consuming review  
- High risk of incorrect merges  

### ✅ After Agent
- One command  
- Automated duplicate detection  
- Clear explanation  
- Confidence scoring  
- Action recommendation  
- Master record suggestion  

**Result:**
- Reduced manual review time  
- Improved productivity  
- Higher audit confidence  
- Better data governance  

---

## 📈 Why This Matters

This solution directly addresses:

- Data inconsistency  
- Compliance risk  
- Customer profile fragmentation  
- Operational inefficiencies  

It automates messy internal work and transforms it into an explainable, AI-assisted workflow.

---

## 🔐 Design Principles

- Explainability over black-box scoring  
- Deterministic confidence logic  
- Human-in-the-loop option (REVIEW stage)  
- Audit-friendly output format  
- Enterprise scalability  

---

## 📜 License

This project is licensed under the Apache License 2.0.

---

## 👨‍💻 Author

**Praneeth**  
Elastic Certified Engineer  
Specializing in Elasticsearch, ES|QL, AI-driven search, and data quality automation.

---

⭐ Built to automate messy internal work  
⭐ Designed for enterprise-grade data quality  
⭐ Explainable AI + Elasticsearch done right
