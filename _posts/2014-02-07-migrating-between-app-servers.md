---
layout: post
title:  "Migrating Application between Application Servers"
date:   2014-02-06 12:00:00 +0000
categories: blogs appserver migration
tags: appserver migration
---
Many organisations are thinking about moving their applications from heavy weight “traditional” application servers such as WebSphere and WebLogic on to JBoss for a variety of reasons: performance, ease of use and total cost of ownership to name a few. JBoss has grown in popularity in the market place because open sourced software is no longer “scare-ware” and it has a growing history of performing well. Enterprise organisations are starting to take a leap of faith. But what is involved in migrating applications from one type of container to another? How easy is it to do and what are the pitfalls we should be aware of?

<br>
<h2 style="font-size: 35px">In principle it seems quite simple, take a working application and move it to a new container, but it never is that simple.</h2>
<br>

There are three main areas you should consider, infrastructure, configuration and application.

New servers normally mean new hardware. Considerations for the hardware are the OS and the version of the OS, number of processors, memory capacity, disk usage and capacity. All these must be assessed to make sure the application will perform in the new container.

Secondly, you need to migrate the application referenced resources to the new container. Resources such as database connections, queue definitions or URL endpoints. Hold on….JBoss and WebLogic do not have a URL endpoint equivalent configuration. When a configuration item is not supported in the new container then you will have to modify the application to manage the resources internally. The difficulty here is to identify what resources are required by the application and then create the resource definition in the new container or update the application accordingly.

<br>
<h2 style="font-size: 35px">
Unfortunately, the reality is, server configuration is a complex process and there is not an easy mapping from one application server to another.</h2>
<br>

Thirdly, you need to analyse the application to see if it uses any proprietary APIs that need converting to an equivalent container API. Without analysing the code or expert knowledge of the application there is no easy way of doing this. Often these APIs are not picked up until a bug is raised in a Test, or worse, a Production environment. The application may need redeveloping to change the APIs. Even if there are no proprietary APIs to convert, what is definite is the application deployment descriptors will need converting. For example, WebSphere provides proprietary features and configurations within a series of .xmi files. These settings need converting to settings within the new container deployment descriptors. If you are moving application from Oracle WebLogic Server to JBoss Application Server (or Wildfly) - take a look at <http://windup.jboss.org>

Finally, when you have migrated the applications you need to run a full set of regression tests to make sure you have not changed or broken any functionality. Therefore, to successfully migrate a stack of enterprise applications you need to have expertise from infrastructure, operations, developers and testers.

So next time your CTO asks you to quickly migrate all your applications to a new container for a cost cutting exercise in triple quick time at least you will be able to reason why the process may not be so quick to implement.