---
layout: post
title:  "OneNote and Microsoft Graph experiments"
author: gerald
categories: [ coding]
image: assets/images/landscape7.jpg
---


# Goal

Add a screenshot to a OneNote page

# Attempt #1

From Ayuba Audu (PM on OneNote). 

https://github.com/microsoftgraph/dotnetcore-console-sample/tree/master/base-console-app

https://github.com/microsoftgraph/dotnetcore-console-sample/blob/master/day25-onenote/Program.cs


Dead-end, unfortunately, because the sample is based on "app-only" authentication.

# Attempt #2

> All requests to Microsoft Graph require an authenticated context, either delegated or app-only.  Delegated is a union of the logged-in user’s context along with the application’s context.  App-only (as the name implies) is only the application’s context without any user involvement. [Source](https://briantjackett.com/2018/12/13/introduction-to-calling-microsoft-graph-from-a-c-net-core-application/)

Our tenant does not allow that kind of delegation (which makes sense).

There are 2 primary authentication flows against Azure Active Directory:

On behalf of user: **Also called delegated or app + user**

Application: Also called app-only

Let's see if we can make "app+user" work.

> MSAL and the Azure AD v2 endpoint are the go-forward direction (see Future state below) and as such we recommend you start there. [Source](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-8-authentication-roadmap-and-access-tokens/#)

# MS Graph documentation
[Overview of Auth approaches](https://docs.microsoft.com/en-us/azure/active-directory/develop/scenario-desktop-overview)
> If it's a .NET Core application and you agree to have the authentication interaction with Azure Active Directory (Azure AD) happen in the system browser.


Another sample:
https://developermessaging.azurewebsites.net/2019/10/07/msal-basics-a-guide-to-azure-ads-authentication-library/

**And another sample that actually works, for device flow only, only for MSA**
https://docs.microsoft.com/en-us/graph/tutorials/dotnet-core

Needed to make changes to not only enable device auth flow:

> _msalClient = PublicClientApplicationBuilder
                .Create(appId)
                .WithRedirectUri("http://localhost:1235")  
                .Build();

>  var result = await _msalClient.AcquireTokenInteractive(_scopes).ExecuteAsync();

Also changed the scopes to allow AAD account to work. Didn't success

# Attempt 3: use classis Visual Studio and regular .Net

Sample "just works"
https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-v2-windows-desktop

Where do I configure access permissions for "a25fca57-04c5-478f-b06d-a233e7f05f99"
https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Overview/appId/a25fca57-04c5-478f-b06d-a233e7f05f99/objectId/8b724205-f5b9-4fe1-85c0-ac854d41226a 
Or better:
https://aad.portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade 

# Litter

https://github.com/Azure-Samples/active-directory-dotnet-desktop-msgraph-v2




https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-25-use-case-create-a-onenote-notebook/

