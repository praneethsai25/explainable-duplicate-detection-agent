# json

{
  "tool_id": "find_duplicates",
  "description": "Searches for potential duplicate customer records using fuzzy matching on name, email, and phone",
  "index": "customers_dupe",
  "query_type": "elasticsearch_search"
}
## custom isntructions
Perform a fuzzy multi_match search on name, email, and phone fields with fuzziness: AUTO.
Boost name and email relevance higher than phone.
Normalize phone numbers by ignoring formatting differences.
Exclude the input record itself from results.
Limit results to top 3 highest _score matches.
Return _score, name, email, phone, address, and _id.
Do not provide explanations or decisions. Retrieval only.
