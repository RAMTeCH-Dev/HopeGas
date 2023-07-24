---
layout: default
title: "QA Portal Primary"
category: infrastructure
item: wsvEsriPortq100
latest: true
order: 7
---

# Portal primary deployment template

## Getting started
Follow the process for cinc install and setup as defined in 
[Infrastructure Getting Started](https://ramtech-dev.github.io/HopeGas/infrastructure/get-started.html)

The chef srcipt for the wsvEsriPortq100.hopegas.loc machine is located at 
[wsvEsriPortq100 chef script]()

This chef workflow will do the initial step in deployment of the highly available ArcGIS Enterprise.  
This will configure 
 - Machine 1: ArcGIS Enterprise primary machine

To run Chef, the workflow uses Cinc Client in local mode.

**Prerequesite**

* Create service account to run the ArcGIS Enterprise services
  * a group managed service account was set up for this purpose
* Create portal content file share granting full permissions to the service account
* Portal for ArcGIS 10.11 setups.
* Portal for ArcGIS 10.11 authorization files.
* Domain name for your web site routed.
* SSL certificate in PKCS12 (a.k.a. pfx) format issued by certification authority (CA) for the domain.

**The workflow will:**

* Install a primary Portal for ArcGIS and authorize it. Create the initial administrator account.
* Install Portal for ArcGIS Web Styles on both the primary machines.
* Install and configure ArcGIS Web Adaptor for Portal for ArcGIS on both primary machines.
* Install/configure IIS web server on both the ArcGIS Enterprise primary node.
* Import the domain CA-issued certificate.
* Install a primary and standby ArcGIS Data Store and configure it as a relational and tile cache store with ArcGIS Server.



## recipes run
 - arcgis-enterprise::system
 - esri-iis
 - arcgis-enterprise::disable_loopback_check
 - arcgis-enterprise::install_portal
 - arcgis-enterprise::webstyles
 - arcgis-enterprise::portal
 - arcgis-enterprise::portal_wa
 - arcgis-enterprise::install_patches

## Step 1.  Install Cinc Client

See [Getting Started for details](https://ramtech-dev.github.io/HopeGas/infrastructure/get-started.html)

## Step 2. Download Chef Cookbooks for ArcGIS

See [Getting Started for details](https://ramtech-dev.github.io/HopeGas/infrastructure/get-started.html)

## Step 3. Set up Local ArcGIS Software Repository

The deployment templates require ArcGIS setup archives to install ArcGIS applications. 
The setup archives must be located in a local or shared ArcGIS Software Repository directory specified by the arcgis.repository.archives attribute. 
Before running the setups, the setup archives are extracted into a local directory specified using the arcgis.repository.setups attribute.

On the ArcGIS Enterprise primary machines, set up local ArcGIS software repositories.

> Note: Alternatively, instead of copying ArcGIS setup archives on the primary and standby machines, a shared ArcGIS software repository can be set up on the file server machine.

Create directory 'C:\Software\Archives' and copy the ArcGIS Enterprise 10.11 setup archives to that directory:

* ArcGIS_Web_Adaptor_for_Microsoft_IIS_109_177789.exe
* Portal_for_ArcGIS_Windows_109_177786.exe
* Portal_for_ArcGIS_Web_Styles_Windows_109_177787.exe