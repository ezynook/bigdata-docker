To run Hive with postgresql metastore:
    # docker-compose up -d
To deploy in Docker Swarm:
    # docker stack deploy -c docker-compose.yml hive
To run a PrestoDB 0.181 with Hive connector:
    # docker-compose up -d presto-coordinator


Load data into Hive:
  $ docker-compose exec hive-server bash
  # /opt/hive/bin/beeline -u jdbc:hive2://localhost:10000
  > CREATE TABLE pokes (foo INT, bar STRING);
  > LOAD DATA LOCAL INPATH '/opt/hive/examples/files/kv1.txt' OVERWRITE INTO TABLE pokes;