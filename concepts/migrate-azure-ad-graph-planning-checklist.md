---
title: "App migration planning checklist"
description: "Checklist for migrating your apps from Azure AD Graph to Microsoft Graph"
author: "dkershaw10"
ms.localizationpriority: medium
ms.prod: "applications"
---

# App migration planning checklist

> [!WARNING]
> **Azure AD Graph is deprecated**. To avoid loss of functionality, migrate your applications to Microsoft Graph before June 30, 2022 when Azure AD Graph API endpoints will stop responding to requests.
>
> Microsoft will continue technical support and apply security fixes for Azure AD Graph until June 30, 2022 when all functionality and support will end. If you fail to migrate your applications to Microsoft Graph before June 30, 2022, you put their functionality and stability at risk.

Use the following checklist to plan your migration.

## Step 1: Review the differences between the APIs

In many respects, Microsoft Graph is similar to the earlier Azure AD Graph. In many cases, simply change the endpoint service name and version in your code, and everything should continue to work.

Nonetheless, there are differences. Certain resources, properties, methods, and core capabilities have changed.

Specifically, look for differences in the following areas:

- [Request call syntax](migrate-azure-ad-graph-request-differences.md) between the two services
- [Feature differences](migrate-azure-ad-graph-feature-differences.md), such as directory extensions, batching, differential queries, and so on
- [Entity resource names](migrate-azure-ad-graph-resource-differences.md) and their types
- [Properties](migrate-azure-ad-graph-property-differences.md) of request and response objects
- [Methods](migrate-azure-ad-graph-method-differences.md), including parameters and types

## Step 2: Examine API use

[Examine the APIs](migrate-azure-ad-graph-audit-api-use.md) used by your app, the permissions they require, and compare to the list of known differences.  

Verify that the APIs your app needs are generally available in Microsoft Graph v1.0 and that these APIs work the same way.

In some cases, new capabilities and features are designed to replace earlier approaches.

Use the [Graph Explorer](https://aka.ms/ge) to experiment with new calls and to develop new approaches. For best results, sign in using the credentials of a test user in a test tenant so that you see what the API does over important data sets.

## Step 3: Review app details

- [App registration](migrate-azure-ad-graph-app-registration.md) and consent changes (which should be none).
- Token acquisition and [authentication libraries](migrate-azure-ad-graph-authentication-library.md).
- For .NET applications, use of [client libraries](migrate-azure-ad-graph-client-libraries.md).

## Step 4: Deploy, test, and extend your app

Before updating your app for everyone, ensure you test thoroughly and stage your rollout to your customer audience.

Now you've made the switch to Microsoft Graph, it's never been easier for you to unlock many more datasets and features that are now at your fingertips. You can get a taste of what's possible by looking at some of the [Major services and features in Microsoft Graph](./overview-major-services.md).

[Microsoft authentication library](/azure/active-directory/develop/reference-v2-libraries) (MSAL) is now the recommended authentication library for use with the Microsoft identity platform. If you're currently using the [AD authentication library](/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL), plan to switch to MSAL. See further guidance to [migrate applications to the Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-migration).

## Next Steps

- Learn about [request call syntax](migrate-azure-ad-graph-request-differences.md) to start step 1: reviewing API differences.
