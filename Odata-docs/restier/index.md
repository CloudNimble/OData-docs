---
title: Introduction to Microsoft Restier
description: An introduction to Microsoft Restier, a rapid API development framework for building secure, queryable APIs on ASP.NET Classic.
author: RobertMcLaws
ms.author: OData
ms.topic: overview
ms.date: 04/10/2021
ms.custom: template-overview
---

# Welcome to Restier!

Restier is a RESTful API development framework for building standardized, OData V4 based RESTful services on .NET platform.

Restier is the spiritual successor to [WCF Data Services](https://en.wikipedia.org/wiki/WCF_Data_Services). Instead of generating endless boilerplate code with the current Web API + OData toolchain, Restier helps you boostrap a standardized, queryable HTTP-based REST interface in literally minutes. And that's just the beginning.

Like WCF Data Services before it, Restier provides simple and straightforward ways to shape queries and intercept submissions
before and after they hit the database. And like Web API + OData, you still have the flexibility to add your own
custom queries and actions with techniques you're already familiar with.

But Restier isn't just for OData and the Entity Framework. It also supports adding additional publishers to support other 
protocols and additional providers to support other data sources.

## What is OData?

OData stands for the Open Data Protocol. OData enables the creation and consumption of RESTful APIs, which allow 
resources, defined in a data model and identified by using URLs, to be published and edited by Web clients using 
simple HTTP requests.

OData was originally designed by Microsoft to be a framework for exposing Entity Framework objects over REST services.
The first concepts shipped as "Project Astoria" in 2007. By 2009, the concept had evolved enough for Microsoft to announce OData, along with a [larger effort](https://blogs.msdn.microsoft.com/odatateam/2009/11/17/breaking-down-data-silos-the-open-data-protocol-odata/)
to push the format as an industry standard.

Work on the current version of the protocol (V4) began in April 2012, and was ratified by OASIS as an industry standard in Feb 2014.

You can find out more about OData at [OData.org](http://www.odata.org/).

## Restier Contributors

Special thanks to everyone involved in making Restier the best API development platform for .NET. The following people
have made various contributions to the codebase:

| Microsoft     | External         |
|---------------|------------------|
| Lewis Cheng   | Cengiz Ilerler   |
| Challenh      | Kemal M          |
| Eric Erhardt  | Robert McLaws    |
| Vincent He    | Jan-Willem Spuji |
| Dong Liu      |                  |
| Layla Liu     |                  |
| Fan Ouyang    |                  |
| Mike Pizzo    |                  |
| Congyong S    |                  |
| Mark Stafford |                  |
| Ray Yao       |                  |