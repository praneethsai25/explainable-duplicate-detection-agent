# find_duplicates Tool

## Overview

The `find_duplicates` tool is a retrieval-only Elasticsearch search tool used by the
Explainable Duplicate Detection Agent. Its purpose is to identify potential duplicate
customer records based on fuzzy similarity across key identity fields.

This tool **does not make decisions** and **does not explain results**.
It strictly retrieves the most relevant candidate records for downstream reasoning
by the agent.

---

## Tool Definition (JSON)

```json
{
  "tool_id": "find_duplicates",
  "description": "Searches for potential duplicate customer records using fuzzy matching on name, email, and phone",
  "index": "customers_dupe",
  "query_type": "elasticsearch_search"
}
