# Soluces for Lab 2

```json
# Simulate the pipeline for our document
POST _ingest/pipeline/_simulate
{
  "pipeline": {
    "processors": [
      {
        "dissect": {
          "field": "content",
          "pattern": "%{message}|%{session}|%{note}"
        }
      },
      {
        "remove": {
          "field": "content"
        }
      },
      {
        "convert": {
          "field": "note",
          "type": "float"
        }
      }
    ]
  },
  "docs": [
    {
      "_source": {
        "content": "Welcome to JDLL|Indexer ses documents bureautique avec la suite Elastic et FSCrawler|2023-04-02|4.5"
      }
    }
  ]
}
```
