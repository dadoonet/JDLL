# Soluces for Lab 5

Launch FSCrawler:

```sh
docker run -it --rm -v "`pwd`"/config:/root/.fscrawler -v "`pwd`"/files:/tmp/es:ro dadoonet/fscrawler fscrawler jdll
```

Edit the job:

```yml
---
name: "jdll"
fs:
  url: "/tmp/es"
elasticsearch:
  nodes:
  - url: "https://SERVICE.es.REGION.PROVIDER.cloud.es.io"
  username: "elastic"
  password: "PASSWORD"
```

Launch FSCrawler in debug mode:

```sh
docker run -it --rm -v "`pwd`"/config:/root/.fscrawler -v "`pwd`"/files:/tmp/es:ro dadoonet/fscrawler fscrawler jdll --debug
```

Restart FSCrawler from scratch:

```sh
docker run -it --rm -v "`pwd`"/config:/root/.fscrawler -v "`pwd`"/files:/tmp/es:ro dadoonet/fscrawler fscrawler jdll --debug --restart
```

In the Dev Console:

```json
# Show created indices
GET /_cat/indices/jdll*?v

# Search for "words".
GET /jdll/_search 
{
  "query": {
    "match": {
      "content": "words"
    }
  }
}
```
