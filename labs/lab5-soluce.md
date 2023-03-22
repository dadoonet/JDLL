# Soluces for Lab 5

Edit the job:

```yml
---
name: "devoxx"
fs:
  url: "/tmp/es"
elasticsearch:
  nodes:
  - url: "https://SERVICE.es.REGION.PROVIDER.cloud.es.io"
  username: "elastic"
  password: "PASSWORD"
workplace_search:
  server: "https://SERVICE.ent.REGION.PROVIDER.cloud.es.io"
```

Restart FSCrawler from scratch:

```sh
docker run -it --rm -v "`pwd`"/config:/root/.fscrawler -v "`pwd`"/files:/tmp/es:ro dadoonet/fscrawler fscrawler devoxx --debug --restart
```
