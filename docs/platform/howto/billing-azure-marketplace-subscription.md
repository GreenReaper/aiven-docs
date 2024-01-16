---
title: Set up Azure Marketplace subscriptions
---

Aiven makes its services available through the Microsoft Azure
Marketplace. This article shows the steps needed to create a
subscription that links the accounts.

First, there are some steps that need to be completed on the Azure
Marketplace page before heading over to the Aiven Console and finishing
the process.

## Azure Marketplace setup

1.  Search for \"Aiven Managed Database Services\" on the [Azure
    Marketplace](https://portal.azure.com/#view/Microsoft_Azure_Marketplace/MarketplaceOffersBlade/selectedMenuItemId/home).
    This page contains information about all of Aiven\'s services and
    how the marketplace subscription works. Click the **Subscribe**
    button on this page.

![Azure Marketplace listing tile for Aiven Managed Database Services](/images/platform/howto/azure-marketplace-listing.png)

2.  Select your desired Azure subscription resource group to organise
    your resources, give the subscription a name, and make sure that
    \"Recurring billing\" is turned on. There is only one plan available
    because all of the costs are managed by Aiven based on what you use
    during the month.
3.  Progress to the \"Review + subscribe\" screen, then read and agree
    to the terms of use.
4.  When you are ready, click the **Subscribe** button at the bottom of
    the page. You will NOT be charged by clicking this button; this only
    sets up a billing subscription between Azure and Aiven. You will
    only be charged after deploying Aiven services.
5.  You should now see a message that says \"Your SaaS subscription is
    in progress\". This takes a few minutes to complete before you can
    progress.
6.  When you see the message \"Thank you for your order. Configure the
    SaaS service to complete the purchase\", click the \"Configure
    account now\" button to head over to the Aiven website to complete
    the process.

## Aiven account setup

7.  You should now be on the [Azure signup page at
    Aiven](https://console.azure.aiven.io/login), asking you for your
    email address to log in to the account. This should be the same
    email as you use on the Azure console.
8.  After entering your email address, you will be authenticated via
    Azure single sign-on and then returned to the Aiven Console.
9.  You will be sent an email to \"Activate your new subscription\" -
    click on the **Activate now** link to join your Aiven account to
    your Azure account.

:::note
The URL is [https://console.azure.aiven.io](https://console.azure.aiven.io) - this is different from the
Aiven Console ([https://console.aiven.io](https://console.aiven.io)).
:::

When you view the Aiven subscription on the Azure SaaS resource list,
you will see a link to **Open SaaS Account on publisher\'s site**. You
can use this link to complete the subscription process if anything goes
wrong during the steps listed here.
