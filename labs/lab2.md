# Lab 2: Ingest Pipelines

Useful links:

* <https://www.elastic.co/guide/en/elasticsearch/reference/current/ingest.html>
* <https://www.elastic.co/guide/en/elasticsearch/reference/current/processors.html>
* <https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-update-settings.html>
* <https://www.elastic.co/guide/en/elasticsearch/reference/current/index-modules.html#dynamic-index-settings>
* <https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-bulk.html>

## Steps

The source document is:

```json
{
  "content": "Welcome to JDLL|Indexer ses documents bureautique avec la suite Elastic et FSCrawler|4.5"
}
```

Build/simulate a pipeline which transforms it to:

```json
{
  "message": "Welcome to JDLL",
  "session": "Indexer ses documents bureautique avec la suite Elastic et FSCrawler",
  "note": 4.5
}
```

You can start from this:

```json
POST _ingest/pipeline/_simulate
{
  "pipeline": {
    "processors": [
      // Add your processors here
      // {
      // }
    ]
  },
  "docs": [
    {
      "_source": {
        "content": "Welcome to JDLL|Indexer ses documents bureautique avec la suite Elastic et FSCrawler|4.5"
      }
    }
  ]
}
```

Hint: one of the most useful processors for text extraction is `dissect`.

[Next step](lab3.md).
