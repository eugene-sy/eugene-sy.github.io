---
layout: post
title: "Logging in a Microservices Environment"
categories: architecture
tags: [architecture, microservices]
preface: "Logging is usually overlooked and considered to be easy to do. But it can become complicated when scaled up and especially in a multi-language environment. Here is my vision of the approach to do it right."
---

Life is easy and when an application is developed as a monolith and is deployed to only one server. You can simply log on the server and check log files. Obviously, you have to add some logging statements to the code and sometimes your framework does it for you, but it does not make any troubles yet.

Things get more complicated when you have to deploy several instances of your application to several servers. Or, in another case, you have to add another service to the infrastructure. The number of log files and hosts grows, it becomes more and more difficult to track event sequences in the application. As a result, it becomes more troublesome, time-consuming and costly to investigate and debug problems in the codebase of the application.

## Infrastructure Requirements

## Logging Setup

## Development, Debugging and Disaster Recovery
