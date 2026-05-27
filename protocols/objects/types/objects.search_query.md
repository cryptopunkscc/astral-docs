# objects.search_query

A parsed search query: bare words form the free-text `Query`, while `tag:value` style tokens become `Tags`. Text encoding round-trips through `MarshalText`/`UnmarshalText`.

## Fields

* Query (string16) – Free-text portion of the query (whitespace-joined, lowercased).
* Tags ([]objects.query_tag) – Parsed tag clauses, in original order.

## Example

```json
{
  "Type": "objects.search_query",
  "Object": {
    "Query": "hello world",
    "Tags": [
      {"Name": "mime", "Mod": "", "Value": "text/plain"},
      {"Name": "private", "Mod": "EXCLUDE", "Value": "true"}
    ]
  }
}
```
