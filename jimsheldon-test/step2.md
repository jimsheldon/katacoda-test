Install elastalert:
```
pip2 install elastalert==0.1.36
```{{execute}}

ElastAlert saves information and metadata about its queries and its alerts back to Elasticsearch. This is useful for auditing, debugging, and it allows ElastAlert to restart and resume exactly where it left off.

Create an index with `elastalert-create-index`:
```
elastalert-create-index --index=elastalert_status --config config.yml
```{{execute}}

Check elasticsearch logs:
```
docker logs elasticsearch | grep "creating index"
```{{execute}}
