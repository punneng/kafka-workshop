# Try nodejs

> $ cd ~/workshop/

> $ docker-compose up

-------------------------------------
NEW SHELL
> $ cd ~/workshop/kafka-workshop

pull code from submodule
> $ git submodule update --init

checkout https://github.com/edenhill/librdkafka/blob/0.11.1.x/CONFIGURATION.md

> $ cd nodejs-kafka-exmaple

> $ npm install

create .env
```
TOPICS=nodejs-test
BOOTSTRAP_SERVERS=127.0.0.1:9092
```

create topic
NEW SHELL to create a topic
> $ cd ~/workshop/kafka_2.12-1.1.0/

> $ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 3 --topic nodejs-test

produce
> $ node producer.js

comsume
> $ node consumer.js