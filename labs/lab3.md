# Lab 3: Ingest Attachment Processor

Useful links:

* <https://www.elastic.co/guide/en/elasticsearch/reference/current/attachment.html>

## Steps

Simulate a new pipeline which now extracts text from base64 encoded binary file.
You can start from:

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
        "content": "V2VsY29tZSB0byBEZXZveHggRnJhbmNlIDIwMTMuCg=="
      }
    }
  ]
}
```

[Next step](lab4.md).
