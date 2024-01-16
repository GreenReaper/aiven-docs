---
title: Set up SAML with OneLogin
---

This article explains how to set up SAML with
[OneLogin](https://www.onelogin.com/) for an organization in Aiven. For
more information on SAML and instructions for other identity providers,
see the
[Set up SAML authentication](/docs/platform/howto/saml/saml-authentication) article.

## Prerequisite steps in Aiven Console

1.  In the organization, click **Admin**.
2.  Select **Identity providers**.
3.  Click **Add identity provider**.
4.  Enter a name and select SAML. You can also select the groups that
    users will be added to when they sign up or log in through this
    authentication method.

You are shown two parameters needed to set up the SAML authentication in
OneLogin:

-   Metadata URL
-   ACS URL

## Configure SAML on OneLogin

1.  Log in to the [OneLogin Admin
    console](https://app.onelogin.com/login).

2.  Select **Applications** and click **Add App**.

3.  Search for **SAML Custom Connector (Advanced)** and select it.

4.  Change the **Display Name** to `Aiven`.

5.  Add any other visual configurations you want and click **Save**.

6.  In the **Configuration** section of the menu, set the following
    parameters:

      Parameter              Value
      ---------------------- --------------------------------------------------------------------------------
      `ACS URL Validation`   `[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#?&//=]*)`
      `ACS URL`              `ACS URL` from Aiven Console
      `Login URL`            `https://console.aiven.io`
      `SAML Initiator`       `Service Provider` (or `OneLogin` if your users will sign in through OneLogin)
      `SAML nameID format`   `Email`

7.  Click **Save**.

8.  In the **SSO** section of the menu, set **SAML Signature Algorithm**
    to `SHA-256`.

9.  Copy the certificate content, `Issuer URL` and
    `SAML 2.0 Endpoint (HTTP)`. These are needed for the SAML
    configuration in Aiven Console.

10. Click **Save**

11. Assign users to this application.

## Finish the configuration in Aiven

Go back to the **Authentication** page in [Aiven
Console](https://console.aiven.io/) to enable the SAML authentication
method:

1.  Select the name of the OneLogin method that you created.
2.  In the SAML configuration section, click **Edit**.
3.  Add the configuration settings from OneLogin:
    -   Set the `SAML IDP URL` to the `SAML 2.0 Endpoint (HTTP)` from
        OneLogin.
    -   Set the `SAML Entity ID` to the `Issuer URL` from OneLogin.
    -   Paste the certificate from OneLogin into `SAML Certificate`.
4.  If you set `SAML Initiator` to `OneLogin` in your OneLogin
    application, then toggle on `IdP login`.
5.  Toggle on **Enable authentication method** at the top of the page.
6.  In the **Signup and link accounts URLs** section, copy the
    appropriate link and send it to your users to switch them to the new
    IdP:
    -   **Signup URL**: For users that don\'t have an Aiven user account
        and need to create a new Aiven user linked to this IdP.
    -   **Account link URL**: For users that already have an Aiven user
        account to link their existing Aiven user with the configured
        IdP.

:::note
If you set up a SAML authentication method before and are now switching
to a new IdP, existing users need to log in with the new account link
URL to finish the setup.
:::

## Troubleshooting

If you are getting errors, try this:

1.  Go to the app in OneLogin and click **Settings**.
2.  Under **More Actions**, select **Reapply entitlement Mappings**.

If you continue to have issues, you can use the [SAML Tracer browser
extension](https://addons.mozilla.org/firefox/addon/saml-tracer/) to
check the process step by step.
