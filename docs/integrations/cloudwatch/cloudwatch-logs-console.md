---
title: Send logs to AWS CloudWatch from Aiven web console
---

You can find here the steps to send your Aiven service logs to the AWS
CloudWatch using the [Aiven web console](https://console.aiven.io).

## Prerequisites

You will need:

-   An AWS account, and which region it is in.
-   An Aiven account with a service running.
-   An AWS Access Key and Secret Key. Generate the credentials by
    visiting **IAM dashboard** then click in **Users**, open the
    **Security credentials** tab, and choose **Create access key**.
    Click on **Download** as you will need this shortly.

## Configure the integration

Start by configuring the link between the Aiven service and the AWS
CloudWatch. This setup only needs to be done once.

1.  Select **Integration endpoints** in the [Aiven
    Console](https://console.aiven.io/), then choose **AWS CloudWatch
    Logs**.
2.  Select **Add new endpoint** or **Create new**.
3.  Configure the settings for the new endpoint:
    -   **Endpoint name** is how you will refer to this logs integration
        when linking it to other Aiven services.
    -   Your AWS credentials: **Access Key** and **Secret Key**.
    -   Your AWS account **Region**.
    -   **Log Group Name** where your logs streams can be grouped in a
        group on AWS CloudWatch. If this field is not provided, it will
        be generated for you.
4.  Select **Create** to save this endpoint.

## Send logs from an Aiven service to AWS CloudWatch

Follow the steps in this section for each of the services whose logs
should be sent to AWS CloudWatch.

1.  On the **Overview** page of your service, select **Integrations**
    and choose the **Amazon CloudWatch Logs** option.

![Screenshot of system integrations including AWS CloudWatch Logs](/images/integrations/cloudwatch-overview-integrations.png)

2.  Pick the endpoint by the **Endpoint name** you created earlier from
    the dropdown and choose **Enable**.
3.  Visit your AWS account and look under **CloudWatch** and explore the
    **Logs** section to see the data flowing within a few minutes.

:::note[See also]
Learn more about [Amazon CloudWatch and Aiven](/docs/integrations/cloudwatch).
:::
