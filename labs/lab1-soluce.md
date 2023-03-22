# Soluces for Lab 1

```json
# Index a first document
PUT /jdll/_doc/1
{
  "message": "Welcome to JDLL"
}
# Check that the document has been correctly indexed
GET /jdll/_doc/1

# Update the document
PUT /jdll/_doc/1
{
  "message": "Welcome to JDLL",
  "session": "2023-04-02"
}
# Check that the document has been correctly updated
GET /jdll/_doc/1

# Remove the document
DELETE /jdll/_doc/1
# Check that the document has been correctly removed
GET /jdll/_doc/1

# Create a new document
PUT /jdll/_doc/2
{
  "message": "Welcome to JDLL",
  "session": "Un moteur de recherche de documents d'entreprise"
}

# Get the mapping
GET /jdll/_mapping

# Change the mapping to use `text` for both `message` and `session` fields
DELETE /jdll
PUT /jdll
{
  "mappings": {
    "properties": {
      "message": {
        "type": "text"
      },
      "session": {
        "type": "text"
      }
    }
  }
}

# Reindex doc 1
PUT /jdll/_doc/1
{
  "message": "Welcome to JDLL",
  "session": "2023-04-12"
}
# Then doc 2
PUT /jdll/_doc/2
{
  "message": "Welcome to JDLL",
  "session": "Un moteur de recherche de documents d'entreprise"
}

# Search for documents where `message` has `"JDLL"`.
GET /jdll/_search
{
  "query": {
    "match": {
      "message": "JDLL"
    }
  }
}

# Search for documents where `message` has `"JDLL"` or `session` has `fscrawler`, the more terms, the better.
GET /jdll/_search
{
  "query": {
    "bool": {
      "should": [
        {
          "match": {
            "message": "JDLL"
          }
        },        {
          "match": {
            "session": "fscrawler"
          }
        }
      ]
    }
  }
}
```
