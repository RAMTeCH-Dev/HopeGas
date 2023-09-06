---
layout: default
title: "Dev IIS"
category: infrastructure
item: iis
latest: true
order: 5
---

# Install IIS Role on Server

ArcGIS Web Adaptor requires that IIS and specific IIS components be enabled on supported Windows operating systems. 
The setup will not proceed if IIS is not detected and specific IIS components are not enabled.

```
Caution:
You must enable IIS and the required components before proceeding with the ArcGIS Web Adaptor installation.
```

To enable IIS and the required IIS components on Windows Server 2016, Windows Server 2019, and 
Windows Server 2022, complete the following steps:

 1. Open **Server Manager** and click **Manage > Add Roles and Features**. Click **Next**.
 2. Select **Role-based or feature-based installation** and click **Next**.
 3. Select the appropriate server. The local server is selected by default. Click **Next**.
 4. Enable **Web Server (IIS)** and click **Next**.
 5. No additional features are necessary to install the Web Adaptor, so click **Next**.
 6. On the **Web Server Role (IIS)** dialog box, click **Next**.
 7. On the **Select role services** dialog box, verify that the web server components 
 listed in the [Required IIS components](https://enterprise.arcgis.com/en/web-adaptor/11.1/install/iis/manually-enable-iis-and-required-components.htm#GUID-FCE5C4E8-C261-4920-9A26-DF5600164391) section are enabled. Click **Next**.
 8. Verify that your settings are correct and click **Install**.
 9. When the installation completes, click **Close** to close the wizard.

 ### Required IIS Components
 The IIS components listed below satisfy the minimum requirements to run the Web Adaptor. If other IIS components are enabled, they do not need to be removed.

 * Web Server
   * Common HTTP Features
     * Default Document
     * Static Content
   * Security
     * Request Filtering
     * Windows Authentication
   * Application Development
     * ISAPI Extensions
     * ISAPI Filters
     * WebSocket Protocol
 * Management Tools
   * IIS Management Console

