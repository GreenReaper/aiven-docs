---
title: Get started with Aiven for Redis®*
---

The first step in using Aiven for Redis®\* is to create a service. You
can do so either using the [Aiven Web
Console](https://console.aiven.io/) or the [Aiven
CLI](https://github.com/aiven/aiven-client).

## Create a Redis®\* service using the Aiven Console

1.  Log in to the [Aiven Console](https://console.aiven.io/).
2.  Follow
    [these instructions](/docs/platform/howto/create_new_service) to create a new Redis service.

Once the service is ready, the status changes to *Running*. Depending on
your selected cloud provider and region, this generally takes a couple
of minutes.

## Create a Redis®\* service using the Aiven CLI

[Aiven CLI](https://github.com/aiven/aiven-client) provides a simple and
efficient way to create an Aiven for Redis®\* service. If you prefer
launching a new service from the CLI, follow these steps:

1.  Determine the service plan, cloud provider, and region you want to
    use for your Redis®\* service.

2.  Run the following command to create a Redis®\* service named
    demo-Redis:

    ``` 
    avn service create demo-Redis       \
       --service-type redis             \
       --cloud CLOUD_AND_REGION         \
       --plan PLAN                      \
       --project PROJECT_NAME 
    ```

:::note
There are additional options available to you, which you can view by
running the following commands:

-   For a full list of default flags: `avn service create -h`
-   For type-specific options: `avn service types -v`
:::

## Connect to Aiven for Redis

Learn how to connect to Aiven for Redis using different programming
languages or through `redis-cli`:

-   [redis-cli](howto/connect-redis-cli)
-   [Go](howto/connect-go)
-   [Node](howto/connect-node)
-   [PHP](howto/connect-php)
-   [Python](howto/connect-python)

## Explore other resources for Aiven for Redis

-   [High availability in Aiven for Redis](concepts/high-availability-redis).

    Learn about how Aiven for Redis supports high availability.

-   [Manage SSL connectivity](howto/manage-ssl-connectivity).

    Check how Aiven for Redis supports SSL connections and how can be
    configured.

-   [Memory usage, on-disk persistence and replication in Aiven for Redis](concepts/memory-usage).

    See how Aiven for Redis solves the challenges related to high memory
    usage and high change rate.

-   [Estimate maximum number of connections in Aiven for Redis](howto/estimate-max-number-of-connections).

    Learn how estimate the max number of simultaneous connections in
    Aiven for Redis service.

-   [Lua scripts with Aiven for Redis](concepts/lua-scripts-redis).

    Learn about inbuilt support for running Lua scripts in Aiven for
    Redis service.

-   [Benchmark performance](howto/benchmark-performance)

    Learn how to benchmark the performance of Aiven for Redis service.
