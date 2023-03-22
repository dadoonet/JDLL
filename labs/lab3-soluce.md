# Soluces for Lab 3

```json
# Simulate a new pipeline which now extracts text from base64 encoded binary file.
POST _ingest/pipeline/_simulate
{
  "pipeline": {
    "processors": [
      {
        "attachment": {
          "field": "content",
          "remove_binary": true
        }
      }
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
