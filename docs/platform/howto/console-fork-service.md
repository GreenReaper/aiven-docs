---
title: Fork your service
---

Fork your Aiven service in order to make a copy of the service. You can
use it to create a development copy of your production environment, set
up a snapshot to analyze an issue or test an upgrade, or create an
instance in a different cloud/geographical location/under a different
plan.

Learn more
[about service forking](/docs/platform/concepts/service-forking).

## Fork a service using the console

1.  Log in to [Aiven Console](https://console.aiven.io/).
2.  Go to your **Services**, and select the service you want to fork.
3.  On the **Overview** page of your service, scroll down to **Fork
    Database** \> **New database fork**.
4.  In the **New Database Fork** window, select the new service region
    and plan.
5.  Select **Create fork**.

:::note[Result]
You have now copied your Aiven service.
:::

:::tip
You can now apply any integrations you may need for the copy.
:::

## Fork a service using the Aiven client (CLI)

1.  Prepare the command to create a new service, this will contain the
    new copy of your data store.

2.  Add the `service_to_fork_from` parameter to specify the service to
    use as the source. Change service type accordingly with `-t`, run
    the following command to see available options:

    ``` 
    avn service types        
    ```

For example, if you want to create a fork of your `forker` PostgreSQL®
service, and name it `forked`, the command would be something like:

``` 
avn service create forked -t pg --plan business-4 -c service_to_fork_from=forker
```

:::note[Result]
You have now copied your Aiven service.
:::

:::tip
You can now apply any integrations you may need for the copy.
:::
