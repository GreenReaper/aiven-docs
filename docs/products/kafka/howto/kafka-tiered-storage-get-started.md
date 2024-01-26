---
title: Get started with tiered storage for Aiven for Apache Kafka®
---

Aiven for Apache Kafka®'s tiered storage optimizes resources by keeping
recent data---typically the most accessed---on faster local disks. As
data becomes less active, it's transferred to more economical, slower
storage, balancing performance with cost efficiency.

:::important
Aiven for Apache Kafka® tiered storage is an
[early availability feature](/docs/platform/concepts/beta_services).

To use this feature, contact [our sales team](mailto:sales@aiven.io) to activate tiered storage for your account.

After activation, you must enable the feature from the
[feature preview page](/docs/platform/howto/feature-preview) in your user profile to start using tiered storage.

For further details, see [Enable tiered storage for Aiven for Apache Kafka](/docs/products/kafka/howto/enable-kafka-tiered-storage).
:::

For an in-depth understanding of tiered storage, how it works, and its
benefits, see
[Tiered storage in Aiven for Apache Kafka®](/docs/products/kafka/concepts/kafka-tiered-storage).

## Enable tiered storage for service

To use tiered storage, you need to first
[enable](/docs/products/kafka/howto/enable-kafka-tiered-storage) it for your Aiven for Apache Kafka service® service. This
foundational step ensures that the necessary infrastructure is in place.

:::note
Tiered storage for Aiven for Apache Kafka® is supported starting from
Apache Kafka® version 3.6 and is not available for startup-2 plans.
:::

## Configure tiered storage per topic

Once the tiered storage is enabled at the service level, you can
configure it for individual topics. In the Aiven for Apache Kafka Topics
page, topics using tiered storage will display **Active** in the
**Tiered storage** column.

For detailed instructions, see
[Configuring tiered storage for topics](/docs/products/kafka/howto/configure-topic-tiered-storage).

## Tiered storage usage overview

Gain insights into tiered storage usage from the **Tiered Storage
Overview** page in your Aiven for Apache Kafka service. This includes
details on billing, settings, and specific storage aspects.

For more information, see
[Tiered Storage Overview in Aiven Console](/docs/products/kafka/howto/tiered-storage-overview-page).
