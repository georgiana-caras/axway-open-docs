---
title: Configure Public API mode
linkTitle: Configure Public API mode
weight: 13
date: 2019-07-30
description: This section describes how to configure APIs and applications to be exposed publicly in API Manager and how to enable Public API mode in Joomla! Administrator Interface (JAI).
---

Public API mode enables you to expose non-business critical APIs and their methods so that your API consumers can access them without creating a user account or logging in.

When Public API mode is enabled, users can browse any APIs and applications you have specifically exposed for public access in API Manager, without logging in to API Portal. Users can still sign in or sign up to API Portal to use all the features.

## Differences in user experience

The user experience in public API mode is different than when signed in:

-   On the API Portal landing page, the Sign In button is replaced with an Explore button that goes to API Catalog.
-   The items in the main navigation menu have the following changes:
    -   API Catalog displays only the APIs and methods configured to be exposed in Public API mode, but is available normally.
    -   If not disabled, the Applications page is available as read-only. The Usage tab on the Applications page is always disabled.
    -   The Monitoring and Users pages are unavailable.

-   The user profile information is unavailable.

Public API mode only affects your APIs and applications. Joomla! articles, blogs, or forums are not included in Public API mode. You can manage how these are exposed by changing their **Access** settings in JAI.

This section describes how to configure APIs and applications to be exposed publicly in API Manager and how to enable Public API mode in Joomla! Administrator Interface (JAI).

## Configure APIs and applications in API Manager

For Public API mode access, create a separate organization and user in API Manager, and give that organization access to any APIs and applications that you want to expose publicly.

1.  In API Manager, add a new organization (for example, `Public API Org`).
1.  Add a user account for Public API mode access.
1.  -   Enable the user.
    -   Set **Organization** to the Public API organization you created (`Public API Org`)
    -   Set **Role** to `User`.

1.  Select **Change password**, and set the password for the Public API mode user.
{{< alert title="" >}}
Make a note of the login name and password you configure for the Public API mode user. You will need them later when configuring the Public API mode in JAI.
{{< /alert >}}
1.  Select the APIs to expose publicly. Go to **Frontend API**, select the APIs to expose (they must be in **Published** state), click **Managed selected > Grant access**, set **Grant API access** to **The following organizations**, and add and select your Public API mode organization.
{{< alert title="" >}}
You can import two versions of a back-end API: one that contains only non-business critical information and is exposed in Public API mode, and a full version which is not exposed without a user login.
{{< /alert >}}
1.  Select the applications to expose publicly. Go to **Clients > Applications**, ensure that the organization of the applications is set to your Public API mode organization and the application has access to the required APIs, then share the application with the Public API mode user you created. It is recommended to only provide rights to view the application.

Enable Public API mode in API Portal
------------------------------------

Public API mode is disabled by default. You must enable it in JAI, and add the login details of the Public API mode user account you created in API Manager.

1.  Log in to JAI, and go to **Components > API Portal > Public API**.
2.  Switch **Enable Public API** to **Yes**.
3.  In **Public API Account Login**, enter the login name of the Public API mode user account you created.
4.  In **Public API Account Password**, enter the password of the Public API mode user account you created, and click **Save**.

Hide applications in Public API mode
------------------------------------

You can hide the Applications page from the main menu when Public API mode is enabled.

1.  In JAI, go to **Components > API Portal > Public API**.
2.  Switch **Make Application Menu Entry Public** to **No**.
3.  Click **Save**.

Disable testing API methods in Public API mode
----------------------------------------------

To disable the **Try it** functionality in Public API mode, follow these steps:

1.  In JAI, click **Menu(s) > Main Menu**.
2.  Select **APIs**.
3.  On the **API Catalog** tab, set **Show inline Try-it** to **Yes only to authenticated users**, and click **Save**.

Usage guidelines
----------------

-   Do not edit or delete the Joomla! default user group.
-   Do not change the value of the **Access** option in the **Menu > All Menu Items** in JAI for APIs and Applications because this may cause API Portal malfunction.

