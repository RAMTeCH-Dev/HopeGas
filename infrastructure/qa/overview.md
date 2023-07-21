---
layout: default
title: "QA Overview"
category: infrastructure
item: qa-overview
latest: true
order: 5
---

# QA Enterprise Architecture

The QA Environment is setup as a High Availability (HA) multi-machine deployment.  The setup includes a primary/standby Portal for ArcGIS configuration and a two ArcGIS Server site.  Windows fail-over clustering is used for system fail over.

The following machines are included in the QA deployment:
 - wsvEsriPortq100.hopegas.loc
 - wsvEsriPortq200.hopegas.loc
 - wsvEsriFedq100.hopegas.loc
 - wsvEsriFedq200.hopegas.loc

## System Diagram

 - Add image here

## System Specifications

### wsvEsriPortq100.hopegas.loc
#### Hardware 
	- xx Core
#### Apps and Features
 - IIS
 - Portal for ArcGIS - Version: 11.1
 - Web Styles - Version: 11.1
 - Web Adapter - Version: 11.1
   - Patches: MSP
 

### wsvEsriPortq200.hopegas.loc
### wsvEsriFedq100.hopegas.loc
### wsvEsriFedq200.hopegas.loc


