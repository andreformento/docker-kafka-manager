# Kafka Manager

Docker build for [Kafka-Manager](https://github.com/yahoo/kafka-manager), a tool for managing Apache Kafka. Get it at Docker Hub: [andreformento/kafka-manager](https://hub.docker.com/r/andreformento/kafka-manager/)

## example

Build: `make`

Run:

```shell
docker run --rm -p 9000:9000 andreformento/kafka-manager -Dkafka-manager.zkhosts=localhost:2181
```

Run with basic auth and bump up the default timeouts

```shell
docker run --rm -p 9000:9000 \
  andreformento/kafka-manager \
    -Dkafka-manager.zkhosts=localhost:2181 \
    -Dkafka-manager.api-timeout-millis=10000 \
    -Dkafka-manager.cluster-actors-ask-timeout-millis=10000 \
    -Dkafka-manager.partition-offset-cache-timeout-secs=30 \
    -Dkafka-manager.broker-view-thread-pool-size=10 \
    -Dkafka-manager.broker-view-max-queue-size=1000 \
    -Dkafka-manager.broker-view-update-seconds=10 \
    -DbasicAuthentication.enabled=true \
    -DbasicAuthentication.username=foo \
    -DbasicAuthentication.password=bar
```
