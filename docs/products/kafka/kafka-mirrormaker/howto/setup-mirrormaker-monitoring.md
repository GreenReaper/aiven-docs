---
title: Setup Apache Kafka® MirrorMaker 2 monitoring
---

The metrics for the replication flow in Aiven for Apache Kafka®
MirrorMaker 2 are collected and can be exported via metric integration.

## Setup a metric integration to an Aiven for InfluxDB® service

To set up an integration to push Aiven for Apache Kafka MirrorMaker 2
metrics to an existing Aiven for InfluxDB® service, you can use either
the [Aiven console](https://console.aiven.io/) or the
[Aiven CLI](/docs/tools/cli/service/integration#avn_service_integration_create).

The following example demonstrates how to push the metrics of an Aiven
for Apache Kafka MirrorMaker 2 service named `mirrormaker-demo` into an
Aiven for InfluxDB service named `influxdb-demo` via the
[Aiven CLI](/docs/tools/cli/service/integration#avn_service_integration_create).

``` 
avn service integration-create      \
        -t influxdb-demo            \
        -s mirrormaker-demo         \
        -d influxdb
```

Once the integration is created the Apache Kafka MirrorMaker 2 metrics
will flow into the Aiven for InfluxDB service in the measurement named
`kafka_mirrormaker_summary` and can, for example, be visualized using
[Aiven for Grafana®](/docs/products/grafana)

![Grafana® Dashboard showing MirrorMaker 2 replica lag per topic](/images/products/kafka/kafka-mirrormaker/grafana-mirrormaker2-lag.png)

## Other methods to monitor the replication

-   [JMX](/docs/platform/howto/integrations/access-jmx-metrics-jolokia) metric `jmx.kafka.connect.mirror.record_count` shows
    number of records replicated.

-   

    Monitor the latest messages from all partitions.

    :   An example using `kt` and `jq`:

``` 
kt consume -auth ./kafka.conf -brokers service-project.aivencloud.com:24949 \
-topic topicname -offsets all=newest:newest | \
jq -c -s 'sort_by(.partition) | .[] | \
{partition: .partition, value: .value, timestamp: .timestamp}'
```
