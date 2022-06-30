<h1><strong>วิธีใช้</strong></h1>
< /hr>
To run Hive with postgresql metastore: <br>
    # docker-compose up -d<br>
To deploy in Docker Swarm:<br>
    # docker stack deploy -c docker-compose.yml hive<br>
To run a PrestoDB 0.181 with Hive connector:<br>
    # docker-compose up -d presto-coordinator<br>
   < /hr>
  Load data into Hive:<br>
  $ docker-compose exec hive-server bash<br>
  $ /opt/hive/bin/beeline -u jdbc:hive2://localhost:10000<br>
    > CREATE TABLE pokes (foo INT, bar STRING);<br>
    > LOAD DATA LOCAL INPATH '/opt/hive/examples/files/kv1.txt' OVERWRITE INTO TABLE pokes;<br>
