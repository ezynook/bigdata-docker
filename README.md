<p class="has-line-data" data-line-start="0" data-line-end="6">To run Hive with postgresql metastore:<br>
# docker-compose up -d<br>
To deploy in Docker Swarm:<br>
# docker stack deploy -c docker-compose.yml hive<br>
To run a PrestoDB 0.181 with Hive connector:<br>
# docker-compose up -d presto-coordinator</p>
<p class="has-line-data" data-line-start="8" data-line-end="13">Load data into Hive:<br>
$ docker-compose exec hive-server bash<br>
$ /opt/hive/bin/beeline -u jdbc:hive2://localhost:10000<br>
&gt; CREATE TABLE pokes (foo INT, bar STRING);<br>
&gt; LOAD DATA LOCAL INPATH ‘/opt/hive/examples/files/kv1.txt’ OVERWRITE INTO TABLE pokes;</p>
