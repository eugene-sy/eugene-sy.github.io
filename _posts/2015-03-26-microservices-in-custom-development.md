---
layout: post
title:  "Microservices in custom development"
date:   2015-03-26 12:43:58
categories: books
tags: [architecture, microservices, philosophy]
---

Nowadays microservice architecture is actively discussed in developer circles in media (like Twitter).
As for me, it's a promising way to build large scalable applications and I'd like to build applications in this way, but this type of architecture brings additional complexity and problems for developer teams. Now I'd like to discuss my view to this problems for developer in consulting company, that works on custom development projects.

My view is limited to Russian reality, but could be relevant to other markets.

## Developers

If we are working for enterprise customer, there is a big chance we are talking about slowly evolving environment of large J2EE and .Net applications.
Old-school enterprise developers tend to use old bullet-proof patterns in their work with wide support of instruments.
Most of those developers tend to be quite slow in learning something new and resist any new technologies, knowledge,...
So, if you'll try to start developing an application with a 'new' approach, you'll get a lot of resistance.

Another bad side of microservices is that you'll have some overhead in development process, as you need to integrate various parts of your application.
You also need separate deployment for each of your application parts. All those leads to another stage of resistance of developers.

Microservices requires some infrastructure to be deployed. First of all, there is a chance you will have to build some more server, configure them, add to monitoring platform. Usually it is done by hands of administrators or developers, but not with help of automation tools.
Also, when you are deploying tons of services, you have to use something for service discovery. And it requires research of tools, that will fit for you and your customer. It requires more work, so more resistance will be added.

And another word on tooling. Could you imagine microservices on IBM Websphere? Or even on IBM Webshphere Portal? I cannot.
Microservices requires something lightweight (in Java world it would be Jetty or even netty-based thing, like PlayFramework apps). Another tools leads to more time to research and build. This leads to resistance of developers...

## Managers

## Customer

## Conclusion

## Links

[Microservices initiative](http://microservices.io/)
