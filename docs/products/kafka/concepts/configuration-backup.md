---
title: Configuration backups for Apache Kafka®
---

Aiven for Apache Kafka® includes **configuration backups** that
automatically back up key Apache Kafka® service configurations for you
without any additional costs.

Suppose the Apache Kafka® service is powered off/on or an incident
causes the Apache Kafka cluster to stop functioning. In that case, the
configuration backup enables the restoration of your Apache Kafka®
service to its previous state.

## Whats included in configuration backups

The following data are backed up in the configuration backups:

-   Apache Kafka® topic-related configurations.
-   Everything related to Schema Registry (schemas, ids, subjects,
    compatibility levels).
-   Apache Kafka® Connect configurations.

## Benefits of configuration backups

Some of the key benefits of configuration backups include the following:

-   Configuration backups are automatically enabled and stored in the
    Cloud storage.

-   Configurations are backed up in 3 hours intervals.

-   It helps with speedy disaster recovery in certain situations.

    :::note
    In a rare scenario where all the nodes are lost, the configurations
    are lost and not accessible anymore.
    :::

-   It helps application users with a quick re-creation of Apache Kafka®
    services, allowing them to focus on development tasks rather than
    re-configuring the platform.

## Limitations

Configuration backups do not back up the actual data stored in topics,
consumer groups, and their offsets. Only the Apache Kafka® cluster
configurations are backed up.

For additional support with configuration backups for your Aiven for
Apache Kafka® services, contact [support@aiven.io](mailto:support@aiven.io).
