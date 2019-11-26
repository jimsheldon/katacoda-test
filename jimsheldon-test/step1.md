Start processes with `docker-compose`:
```
docker-compose up
```{{execute}}

Verify elasticsearch is accessible:
```
curl localhost:9200
```{{execute}}

NOTE: it may take a few seconds for elasticsearch to initialize and respond.

When elasticsearch is ready, it will return something like this:
```
{
  "name" : "OonT-mj",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "5DCK4x9hQfCFL2utK1ggyg",
  "version" : {
    "number" : "5.2.1",
    "build_hash" : "db0d481",
    "build_date" : "2017-02-09T22:05:32.386Z",
    "build_snapshot" : false,
    "lucene_version" : "6.4.1"
  },
  "tagline" : "You Know, for Search"
}
```
