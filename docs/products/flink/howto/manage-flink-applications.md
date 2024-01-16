---
title: Manage Aiven for Apache Flink® applications
---

This section provides information on managing your Aiven for Apache
Flink® applications.

## Creating a new version of an application

To create a new version of the application deployed, follow these steps:

1.  Log in to the [Aiven Console](https://console.aiven.io/), and select
    your Aiven for Apache Flink® service.
2.  Select **Applications** from the left sidebar, and select the
    application that contains the deployment you want to create a new
    version.
3.  On the application landing screen, select **Create new version**.
4.  In the create new version screen, make any desired changes to the
    create statement, source, or sink tables.
5.  Select **Save and deploy later**. You can see the new version listed
    in the versions drop-down list on the left side of the screen.
6.  To deploy the new version of the application,
    [stop](/docs/products/flink/howto/manage-flink-applications#stop-flink-application) any
    existing version that is running.
7.  Select **Create deployment**, and on the **Create new deployment**
    screen:
    -   Choose the version you want to deploy.
    -   Choose the savepoint from where you want to deploy.
    -   Use the toggle for **Restart on failure** to enable or disable
        the option of automatically restarting a Flink job in case it
        fails.
    -   Enter the number of [parallel
        instances](https://nightlies.apache.org/flink/flink-docs-master/docs/dev/datastream/execution/parallel/)
        you want to have for the task.
8.  Select **Deploy from a savepoint** or **Deploy without savepoint**
    depending on your previous selection.

## Stop application deployment {#stop-flink-application}

To stop a deployment for your Flink application, follow these steps:

1.  Select **Applications** from the left sidebar on your Aiven for
    Apache Flink service, and select the application that contains the
    deployment you want to stop.
2.  On the application landing screen, select **Stop deployment**.
3.  On the **Stop deployment** screen, enable the option to **Create a
    savepoint before stopping** to preserve the current state of the
    application.

:::note
To stop a deployment without saving the current state of the
application, disable the option for **Create a savepoint before
stopping** and select **Stop without savepoint**.
:::

4.  Select **Create savepoint & stop** to initiate the stopping process.

The application status will display `Saving_and_stop_requested` and then
`Finished` once the stopping process is completed.

Additionally, you can view a history of all the application deployments
and statuses by selecting **Deployment history**.

## Rename application

To rename an application, follow these steps:

1.  Select **Applications** from the left sidebar on your Aiven for
    Apache Flink service, and select the application you want to rename.
2.  On the application landing screen, select the **Application action
    menu** (ellipsis) located on the right side of the screen, and
    select **Update application** from the menu options.
3.  In the **Update Application** screen, enter the new name for the
    application and select **Save changes** to confirm the new name and
    update the application.

## Accessing deployment history {#flink-deployment-history}

The **Deployment History** screen provides the following:

-   A list of all the deployments for an application
-   The user who created the application (created by)
-   Data and time of creation (created at)
-   Application version
-   If a savepoint was created or not

To view and delete the deployment history of an application, follow
these steps:

1.  Select **Applications** from the left sidebar on your Aiven for
    Apache Flink service, and select the application for which you want
    to view the deployment history.
2.  On the application landing screen, select **Deployment History** to
    view the deployment history.
3.  To remove a specific deployment from the history, locate it in the
    deployment history screen and select the **Delete** icon next to it.

To learn about the different application statuses, see \<Flink
application status\>

## Delete application

Before deleting an application, it is necessary to remove all associated
[deployment history](/docs/products/flink/howto/manage-flink-applications#flink-deployment-history).

1.  Select **Applications** from the left sidebar on your Aiven for
    Apache Flink service, and select the application you want to delete.
2.  On the application landing screen, select the **Application action
    menu** (ellipsis) located on the right side of the screen, and
    select **Delete application** from the menu options.
3.  In the **Delete Confirmation** screen, enter the name of the
    application and select **Confirm** to proceed with the deletion.
