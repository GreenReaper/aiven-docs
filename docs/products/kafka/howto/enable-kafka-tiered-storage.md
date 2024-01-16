---
title: Enable tiered storage for Aiven for Apache Kafka®
---

:::important
Aiven for Apache Kafka® tiered storage is an
[early availability feature](/docs/platform/concepts/beta_services). If you\'re interested in trying out this feature, contact
the sales team at [sales@aiven.io](mailto:sales@aiven.io).
:::

Tiered storage significantly improves the storage efficiency of your
Aiven for Apache Kafka® service. You can enable this feature for your
service using either the [Aiven console](https://console.aiven.io/) or
the [Aiven CLI](/docs/tools/cli).

## Prerequisites

-   Aiven account and a project set up in the Aiven Console
-   Aiven for Apache Kafka® service with Apache Kafka version 3.6.
    Tiered storage on Aiven for Apache Kafka is currently not available
    on all plans and regions. View the [plans and pricing
    page](https://aiven.io/pricing?product=kafka) for a comprehensive
    list of supported plans and regions.
-   Aiven CLI

## Enable tiered storage via Aiven Console

Follow these steps to enable tiered storage for your service using the
Aiven Console.

1.  Access the [Aiven console](https://console.aiven.io/), and select
    your project.
2.  Either create a new Aiven for Apache Kafka service or select an
    existing one.
    -   For
        [a new service](/docs/platform/howto/create_new_service):
        a.  On the **Create Apache Kafka® service** page, scroll down to
            the **Tiered storage** section.
        b.  Turn on the **Enable tiered storage** toggle to activate
            tiered storage.
        c.  In the **Service summary**, you can view the pricing for
            tiered storage.
    -   For an existing service:
        a.  Go to the service\'s **Overview** page, select **Service
            settings** from the sidebar.
        b.  In the Service plan section, click **Enable tiered storage**
            to activate it.
3.  Click **Activate tiered storage** to confirm your settings and turn
    on tiered storage for your service.

Following the activation of tiered storage for your service and
[topics](/docs/products/kafka/howto/configure-topic-tiered-storage), you can track usage and costs in the
[Tiered storage overview](/docs/products/kafka/howto/tiered-storage-overview-page) section.

:::note
You can also enable tiered storage by clicking **Tiered storage** in the
sidebar if it\'s not already active for your service.
:::

:::warning
If you power off a service with tiered storage active, you will
permanently lose all remote data. However, you will not be charged for
tiered storage while the service is off.
:::

### Configure default retention policies at service-level

1.  Access [Aiven console](https://console.aiven.io/), select your
    project, and choose your Aiven for Apache Kafka service.
2.  In the service page, select **Service settings** from the sidebar.
3.  On the **Service settings** page, scroll down to the **Advanced
    configuration** section, and click **Configure**.
4.  In the **Advanced configuration** dialog, click **Add configuration
    option**.
5.  To define the retention policy for Aiven for Apache Kafka tiered
    storage, choose either of these options:
    -   Find `kafka.log_local_retention_ms` and set the value to define
        the retention period in milliseconds for time-based retention.
    -   Find `kafka.log_local_retention_bytes` and set the value to
        define the retention limit in bytes for size-based retention.
6.  Click **Save configuration** to apply your changes.

Additionally, you can configure the retention policies from the
[Tiered storage overview](/docs/products/kafka/howto/tiered-storage-overview-page#modify-retention-polices) page.

## (Optional) configure client-side parameter

For optimal performance and reduced risk of broker interruptions when
using tiered storage, it is recommended to update the client-side
parameter `fetch.max.wait.ms` from its default value of 500ms to 5000ms.

## Enable tiered storage via Aiven CLI

Follow these steps to enable tiered storage for your Aiven for Apache
Kafka service using the [Aiven CLI](/docs/tools/cli):

1.  Retrieve the project information using the following command:

    ``` bash
    avn project details
    ```

    If you need details for a specific project, use:

    ``` bash
    avn project details --project <your_project_name>
    ```

2.  Get the name of the Aiven for the Apache Kafka service for which you
    want to enable tiered storage by using the following command:

    ``` bash
    avn service list
    ```

    Make a note of the `SERVICE_NAME` corresponding to your Aiven for
    Apache Kafka service.

3.  Enable tiered storage using the command below:

    ``` bash
    avn service update \
       --project demo-kafka-project \
       demo-kafka-service \
       -c tiered_storage.enabled=true
    ```

In this command:

-   `--project demo-kafka-project`: Replace `demo-kafka-project` with
    your project name.
-   `demo-kafka-service`: Specify the Aiven for Apache Kafka service you
    intend to update.
-   `-c tiered_storage.enabled=true`: Configuration flag that activates
    tiered storage for your Aiven for Apache Kafka service.
