---
title: Getting started with Aiven for PostgreSQL®
---

Aiven for PostgreSQL® is available in the [Aiven
console](https://console.aiven.io).

## Create an Aiven for PostgreSQL® service

1.  Log in to the [Aiven web console](https://console.aiven.io/).

2.  Follow
    [these instructions](/docs/platform/howto/create_new_service) to create a new Aiven for PostgreSQL service.

    Once the service is ready, the status changes to *Running*. This
    typically takes a couple of minutes, depending on your selected
    cloud provider and region.

## Connect to PostgreSQL with `psql`

1.  Log in to [Aiven Console](https://console.aiven.io).

2.  Navigate to your service\'s page, and select **Overview** for the
    left sidebar.

3.  In the **Connection information** section, identify **Service URI**,
    which is the direct PostgreSQL connection endpoint.

    :::note See also
For more information on direct connections and connection pooling,
    visit the dedicated
    [page](concepts/pg-connection-pooling).
:::

4.  Use [psql](howto/connect-psql) to
    connect to the PostgreSQL instance by the following command:

    ``` 
    psql SERVICE_URI_OF_YOUR_SERVICE
    ```

## Load a test dataset in PostgreSQL

If you\'re checking out PostgreSQL, loading a test dataset will give you
something to look at. This example uses `dellstore2`, a standard store
dataset with products, orders, inventory and customer information.

1.  Download the `dellstore2-normal-1.0.tar.gz` file from the
    [PostgreSQL
    website](https://www.postgresql.org/ftp/projects/pgFoundry/dbsamples/dellstore2/dellstore2-normal-1.0/)
    and unzip it.

2.  Navigate to the `dellstore2-normal-1.0` folder on your terminal.

3.  Connect to your PostgreSQL instance with `psql` as shown above.

4.  Create a `dellstore` database and connect to it with the following
    command from `psql`:

    ``` 
    CREATE DATABASE dellstore;
    \c dellstore
    ```

    :::tip
    Your `psql` terminal prefix will change to `dellstore==>` when you
    are connected to the correct database.
    :::

5.  Populate the database by executing the following command from
    `psql`:

    ``` 
    \i dellstore2-normal-1.0.sql
    ```

6.  Verify which objects have been created from `psql`:

    ``` 
    \d
    ```

The output should look like this:

``` 
List of relations
Schema |           Name           |   Type   |  Owner
--------+--------------------------+----------+----------
public | categories               | table    | avnadmin
public | categories_category_seq  | sequence | avnadmin
public | cust_hist                | table    | avnadmin
public | customers                | table    | avnadmin
public | customers_customerid_seq | sequence | avnadmin
public | inventory                | table    | avnadmin
public | orderlines               | table    | avnadmin
public | orders                   | table    | avnadmin
public | orders_orderid_seq       | sequence | avnadmin
public | products                 | table    | avnadmin
public | products_prod_id_seq     | sequence | avnadmin
public | reorder                  | table    | avnadmin
(12 rows)
```

:::note See also
-   Code examples for connecting to PostgreSQL from your application:
    -   [Go](howto/connect-go)
    -   [Python](howto/connect-python)
-   How to [use PgAdmin](howto/connect-pgadmin) with Aiven for PostgreSQL
-   How to
    [migrate your PostgreSQL to Aiven](concepts/aiven-db-migrate)
-   Learn PostgreSQL with some [PostgreSQL
    Exercises](https://pgexercises.com/)
-   The [awesome PostgreSQL
    ecosystem](https://github.com/dhamaniasad/awesome-postgres) of tools
    and solutions
:::
