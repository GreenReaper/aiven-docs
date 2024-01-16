---
title: Create an Aiven for Apache Flink® application
---

[Aiven for Flink applications](/docs/products/flink/concepts/flink-applications) in Aiven for Apache Flink® servers as a container that
includes everything connected to a Flink job, including source and sink
connections and data processing logic. The [Aiven
Console](https://console.aiven.io/) provides a guided wizard to help you
build and deploy applications, simplifying the process of selecting the
source and sink tables, writing data transformation statements, and
validating and ingesting data through the interactive query feature.

This article provides the information required to build and deploy
applications on Aiven for Apache Flink service.

:::note
You must set up the
[data service integration](/docs/products/flink/howto/create-integration) before building applications.
:::

## Create an application via the Aiven console

Follow these steps to build your first Aiven for Flink application:

1.  In the [Aiven Console](https://console.aiven.io/), open the Aiven
    for Apache Flink service for which you want to create an
    application.

2.  Select **Applications** from the left sidebar and select **Create
    application** to create your first application.

3.  In the **Create new application** screen, enter the name of your
    application and configure the necessary deployment settings. select
    **Create application**.

4.  Select **Create first version** to create the first version of the
    application.

5.  Select **Add your first source table** to add a source table.

    :::note
    Since this is your first application, there are currently no other
    applications where you can import source tables.
    :::

6.  In the **Add new source table** screen,

    -   Select the **Integrated service** from the drop-down list.
    -   In the **Table SQL** section, enter the statement that will be
        used to create the table.
    -   Optionally, select **Run** to view how data is being pulled from
        the data source. This could take some time based on the data and
        the connection.
    -   Select **Add table**.

7.  Select **Next** to add the sink table, and then select **Add your
    first sink table**.

    :::note
    Since this is your first application, there are currently no other
    applications where you can import sink tables.
    :::

8.  In the **Add new sink table** screen,

    -   Select **Integrated service** from the drop-down list.
    -   In the **Table SQL** section, enter the statement that will be
        used to create the table.
    -   Select **Add table**.

9.  Select **Next** to enter the **SQL statement** that transforms the
    data from the source stream. Optionally, select **Run** to view how
    data is being pulled from the data source.

10. Select **Save and deploy later** to save the application. You will
    see the application on the landing page that provides you with an
    overview of your application.

    ![Application landing page with an view of source table, SQL statement and sink table](/images/products/flink/application_landingpage_view.png)

11. Select **Create deployment**. On the **Create new deployment**
    screen,

    -   Choose the version you wish to deploy. The default version for
        the first deployment is **Version: 1**.
    -   Choose the
        [savepoint](/docs/products/flink/concepts/savepoints) from where you want to deploy. No savepoints are
        available for the first application deployment.
    -   Use the toggle for **Restart on failure** to enable or disable
        the option of automatically restarting a Flink job in case it
        fails.
    -   Enter the number of [parallel
        instances](https://nightlies.apache.org/flink/flink-docs-master/docs/dev/datastream/execution/parallel/)
        you want to have for the task.

12. Select **Deploy without a savepoint** to deploy your application.

13. The deployment status will show **Initializing: version 1** and then
    **Running: version 1**.

Your first application is now created and deployed, and you can view the
data related to the actions the application needs to perform in your
sink source.
