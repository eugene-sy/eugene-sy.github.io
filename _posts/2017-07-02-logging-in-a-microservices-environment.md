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

[The Twelve-Factor Apps](https://12factor.net) manifest suggests to work with logs as events streams.

It also declares several architectural choices:
- Logs must be time-ordered
- An application must write logs to `stdout`
- An application must ignore log file management, routing of logs to the destination of storage, searching log entries, etc.

There are many different tools to achieve the goals. Depending on what type of deployment you choose, you can use one of log processing startup products (like [Logentries](https://logentries.com/) or [Loggly](https://www.loggly.com/)) or use on-premise solution, like hosting [Elastic Stack](https://www.elastic.co/products) stack in your own infrastructure.

Also, transport solution is needed to forward logs from output streams into log storage solution. While hosted solutions offer to use their own tools, it might be a good choice to check [logstash](https://www.elastic.co/products/logstash). It's an application that consumes logs from different sources (like files, for ex.), transforms data and sends to a destination. A number of output variants is big enough. The only downside of it is that it uses JVM as a host. Other solid chgOise is [R'sw'slog](http://www.rsyslog.com/). The number of input and output sources is not inferior to logstash and you can extend it using plugins, it is the lightweight and native solution for Linux hosts and, chances are, you already have it on your hosts. The downside of rsyslog is configuration and error messaging, it can be tricky to set up it correctly.

Another interesting problem is forwarding logs from containers (like [Docker](https://www.docker.com/)) to a storage location. The rule of thumb is to launch only one process in the container. Obviously, the container has to launch the application process and it should not host log forwarding agent. The simplest solution will be to attach log directory of the host machine to the container (I prefer using `/var/log/containers/` directory on a host machine and `/logs/` inside a container). Then the attached file can be read by an agent on host along with others.

It's very important to sync time host machines. NTP server/client setup should be enough if all servers are in the same timezone. Otherwise, servers in different timezones can be grouped in a storage solution. Given that every timezone group has all application parts and requests are served by the facility of one group, it should not be a problem.

## Logging Setup

## Development, Debugging and Disaster Recovery
