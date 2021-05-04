# elk-course

How to run log generator tool (found in logs folder)

`java -jar log-generator-1.0.jar -l 200 -d 500`

where -l option is amount of logs to generate and -d is delay after each log


## Possibe Issues

### Read-only Mode
When the available disk space is under 5%, elastic enters into a read-only state, to disable it run:

`curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_cluster/settings -d '{ "transient": { "cluster.routing.allocation.disk.threshold_enabled": false } }'`

`curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_all/_settings -d '{"index.blocks.read_only_allow_delete": null}'`