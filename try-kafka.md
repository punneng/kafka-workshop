# Try kafka
## SHELL 1

install jre
> $ brew tap caskroom/versions

> $ brew cask install java8

create directory
> $ mkdir ~/workshop/

> $ cd ~/workshop/

download kafka
> $ curl -O http://www-eu.apache.org/dist/kafka/1.1.0/kafka_2.12-1.1.0.tgz

> $ tar xzf kafka_2.12-1.1.0.tgz

checkout workshop resource
> $ git clone https://github.com/punneng/kafka-workshop.git

> $ cd kafka-workshop

---------------------------------------------
## SHELL 2
NEW SHELL(command + t)
> $ cd ~/workshop/kafka_2.12-1.1.0/

test command
> $ bin/kafka-topics.sh

start zookeeper
> $ bin/zookeeper-server-start.sh config/zookeeper.properties

----------------------------------------------
## SHELL 3
NEW SHELL(command + t)

start kafka
> $ bin/kafka-server-start.sh config/server.properties

---------------------------------------------
## SHELL 4
NEW SHELL(command + t)

create a topic
> $ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 3 --topic test

list topics
> $ bin/kafka-topics.sh --list --zookeeper localhost:2181

describe topic
> $ bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic test

send a message
> $ bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test

---------------------------------------------
## SHELL 5
NEW SHELL(command + t)

consume
> $ bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning

---------------------------------------------
## SHELL 6
NEW SHELL(command + t)

try without [--replication-factor 1 --partitions 3]
> $ bin/kafka-topics.sh --create --zookeeper localhost:2181 --topic test2

try with [--replication-factor 3]
> $ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 3 --partitions 3 --topic test2

try with [--topic test]
> $ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 3 --topic test

---------------------------------------------
go back to consumer shell(4) and ctrl+c
go back to producer shell(5) and ctrl+c

delete a topic
> $ bin/kafka-topics.sh --delete --zookeeper localhost:2181 --topic test

access zookeeper
> $ bin/zookeeper-shell.sh localhost:2181

get a topic info
> $ get /brokers/topics/test

delete a topic
> rmr /brokers/topics/test
