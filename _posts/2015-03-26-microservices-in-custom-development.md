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

Lots of enterprise manager (that I have seen) believe, that the best software tools for enterprise are produced by large corporations like IBM, Oracle and so on.
Free and opensource software is a core of evil for them. They believe that only systems with price over several thousands of dollars are scalable and maintainable.
You have no chance to bring them over.

Another reason, why you cannot use microservices is that you will have to spend more time on development and analysis. There is a chance that this approach could bring you less headache in testing and production is not a reason. 'Developer time cost money', - it is reason of manager. The time in testing, debugging and maintenance don't count.

Also, you can meet a reason like 'I don't understand the profit of it'. We met this one while changing Java to Scala, I think we did not convince out manager that Scala is better for our company, but we still use it.

## Customer

Again, we are talking about enterprise customer. I believe that there are some Oracle databases, application server clusters and even more complex systems already installed.
Your customer payed lots of money for it. Your customer continues to pay for support. And why he have to adopt something new for your comfort? Most of the time, reasons like speed, scalability and reliability are not as good as you think. Large enterprise can pay for a time while their employees are waiting for response of some sort of applications and people.

Also, I believe that managers in enterprises are the same manager in consulting companies, and IBM, Oracle and other corporations are their gods.

## Conclusion

I believe that microservices is a good way to build your applications, it allows to build more scalable and robust applications with smaller teams and less pain.
But, it is sad to say, consulting and custom development are not ready for it for reasons of momentum in thinking and large investments in monolithic architecture.

P.S. I have no purpose to insult anyone in this article, just to outline my thoughts.

## Links

[Microservices initiative](http://microservices.io/)
