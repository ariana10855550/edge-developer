---
title: Network request blocking tool
description: Block network requests with the Network request blocking tool to find out how webpages look and behave when some resources are not available.
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: conceptual
ms.prod: microsoft-edge
ms.date: 02/10/2022
---
# Network request blocking tool

Use the **Network request blocking** tool to check how a webpage looks and behaves when some resources are unavailable, such as image files, JavaScript files, fonts, or CSS stylesheets.

When a webpage depends on _external resources_ that are hosted on other servers than the HTML webpage, sometimes those servers might be unresponsive or unavailable to some users. When this happens, some resources that your webpage depends on might not be retrieved by the web browser.  It's important to check how your webpage behaves when external resources fail to load.  Test whether the webpage handles missing resources gracefully, or appears broken to your users.

After you create blocked network requests and test the webpage, you can then edit or delete the blocked network requests.


<!-- ====================================================================== -->
## Block a network request

To block a network request:

1. Go to the webpage for which you want to block network requests.

1. To open DevTools, right-click the webpage, and then select **Inspect**.  Or, press `Ctrl`+`Shift`+`I` (Windows, Linux) or `Command`+`Option`+`I` (macOS).

1. In DevTools, on the main toolbar, click the **Network request blocking** tab.  If that tab isn't visible, click the **More tabs** (![More tabs icon.](../media/more-tabs-icon-light-theme.png)) button, or else the **More Tools** (![More Tools icon.](../media/more-tools-icon-light-theme.png)) button.

1. Click the **Add pattern** (![Add pattern icon.](media/add-pattern-icon.png)) button.  The **Enable network request blocking** checkbox is automatically selected.

1. In the **Text pattern to block network requests** text box, type the URL of a network request that you want to block.  You can either type the full URL, or replace parts of it with `*` for wildcard pattern matching.

1. Click the **Add** button:

   ![Blocking the https://*.contoso.com/* URL pattern in the network request blocking tool.](media/block-network-request.png)


<!-- ====================================================================== -->
## Delete a blocked network request

To delete a specific network blocking request:

*  In the **Network request blocking** table, hover over the network blocking request, and then click the **Remove** (![Remove blocked request icon](./media/remove-blocked-request-icon.png)) button:

   ![Removing a blocked request](./media/remove-blocked-request.png)


To delete all network blocking requests at once:

*  In the toolbar, click the **Remove all patterns** (![Remove all blocked requests icon](./media/remove-all-blocked-requests-icon.png)) button.


<!-- ====================================================================== -->
## Modify a blocked network request

To change an existing blocked network request:

*  In the **Network request blocking** table, hover over the blocked network request, and then click **Edit** (![edit blocked request icon](./media/edit-blocked-request-icon.png)):

   ![Editing a blocked request](./media/edit-blocked-request.png)


<!-- ====================================================================== -->
## Toggle network request blocking

To toggle network request blocking without having to delete and re-create all of the blocked network requests:

*  In the toolbar, select or clear the **Enable network request blocking** checkbox:

   ![Toggling network request blocking](./media/toggle-request-blocking.png)


<!-- ====================================================================== -->
## Block a network request by using the Network tool

You can block network requests that are made by your webpage either by using the **Network request blocking** tool or by using the **Network** tool.

To block network requests by using the **Network** tool:

1. Go to the webpage for which you want to block network requests.

1. To open DevTools, right-click the webpage, and then select **Inspect**.  Or, press `Ctrl`+`Shift`+`I` (Windows, Linux) or `Command`+`Option`+`I` (macOS).  DevTools opens.

1. In DevTools, on the main toolbar, click the **Network** tab.  If that tab isn't visible, click the **More tabs** (![More tabs icon.](../media/more-tabs-icon-light-theme.png)) button, or else the **More Tools** (![More Tools icon.](../media/more-tools-icon-light-theme.png)) button.

1. In the table of network requests in the bottom pane, find the network request that you want to block.

1. Right-click the network request, and then click **Block request URL** to block this specific resource, or **Block request domain** to block all resources from the same domain:

   ![Blocking from the network tool](./media/block-request-from-network-tool.png)

   _To zoom, right-click > **Open image in new tab**._
