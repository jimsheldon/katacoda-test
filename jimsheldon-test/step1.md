Start elasticsearch:
```
docker run -d -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elasticsearch:5.2.1
```{{execute}}

Verify elasticsearch container is running:
```
docker ps
```{{execute}}

Verify elasticsearch is accessible:
```
curl localhost:9200
```{{execute}}

Tail elasticsearch logs:
```
docker logs --tail 20 elasticsearch
```{{execute}}
