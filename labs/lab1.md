# Lab 1: Indexing JSON documents

Useful links:

* <https://www.elastic.co/guide/en/elasticsearch/reference/current/docs.html>
* <https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-get-mapping.html>
* <https://www.elastic.co/guide/en/elasticsearch/reference/current/search-your-data.html>
* <https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-bool-query.html>

## Steps

* Open Kibana Dev Console
* Index a first document in the `jdll` index:

```json
{
  "message": "Welcome to JDLL"
}
```

* Check that the document has been correctly indexed
* Update the document:

```json
{
  "message": "Welcome to JDLL",
  "session": "2023-04-02"
}
```

* Check that the document has been correctly updated

* Remove the document

* Check that the document has been correctly removed

* Create a new document

```json
{
  "message": "Welcome to JDLL",
  "session": "Indexer ses documents bureautique avec la suite Elastic et FSCrawler"
}
```

* Get the mapping

* Change the mapping to use `text` for both `message` and `session` fields
* Reindex doc 1
* Then doc 2

* Search for documents where `message` has `"JDLL"`.
* Search for documents where `message` has `"JDLL"` or `session` has `fscrawler`, the more terms, the better.

[Next step](lab2.md).
