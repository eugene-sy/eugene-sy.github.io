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

Also, transport solution is needed to forward logs from output streams into log storage solution. While hosted solutions offer to use their own tools, it might be a good choice to check [logstash](https://www.elastic.co/products/logstash). It's an application that consumes logs from different sources (like files, for ex.), transforms data and sends to a destination. A number of output variants is big enough. The only downside of it is that it uses JVM as a host. Other solid choice is [rsyslog](http://www.rsyslog.com/). The number of input and output sources is not inferior to logstash and you can extend it using plugins, it is the lightweight and native solution for Linux hosts and, chances are, you already have it on your hosts. The downside of rsyslog is configuration and error messaging, it can be tricky to set up it correctly.

Another interesting problem is forwarding logs from containers (like [Docker](https://www.docker.com/)) to a storage location. The rule of thumb is to launch only one process in the container. Obviously, the container has to launch the application process and it should not host log forwarding agent. The simplest solution will be to attach log directory of the host machine to the container (I prefer using `/var/log/containers/` directory on a host machine and `/logs/` inside a container). Then the attached file can be read by an agent on host along with others.

It's very important to sync time host machines. NTP server/client setup should be enough if all servers are in the same timezone. Otherwise, servers in different timezones can be grouped in a storage solution. Given that every timezone group has all application parts and requests are served by the facility of one group, it should not be a problem.

## Logging Setup

With log storage and search infrastructure in place, it must be easier to browse events that happen inside the application. But it can be improved.

Log storage solutions offer advanced log parsing capabilities to improve search and analysis. Services written in different languages or with different frameworks/libraries tend to use different formats of output. It makes parsing much more difficult. To avoid this there are two approaches:
- set up agents to parse output streams into similar structures
- set up services to produce similar output.

Personally, I prefer the second way. It makes configuration of a transport agent simpler and shorter. Also, settings for a logger for each platform can be wrapped into a library and included into services to makes it DRY'er.

It's still needed to provide several agent input configurations because, sometimes, it's easier to configure agent rather than an application. For example, this path can be followed for 3rd-party tools, like databases, HTTP servers, etc.

Another, small but important detail, that can be overlooked is log levels definition. Ideally, it should be consistent, for example, it might be defined implicitly with `ENVIRONMENT` environment variables or explicitly with `LOG_LEVEL`. Values of the variable must be consistent too. It's confusing when some parts of application use numbers as configuration options, other different variants of spelling of words.

## Development, Debugging and Disaster Recovery

It's not very important to follow this steps while the application is in a development stage, but it can dramatically enhance an experience of operating the application in production.

It's common to have limited logging enabled for applications in production mode, and excesive logging for development. It makes sense because logging affects performance. But, what if you want temporary increase the level of detail for given service? For that case an HTTP endpoint can be built in the application. The other scenario can be followed if the application uses configuration storage solution, like [Zookeeper](https://zookeeper.apache.org/) or [etcd](https://coreos.com/etcd/), the log level setting can be stored there and changed when needed.

With an ability to change log level on the fly, it becomes easier to debug problems in the production envirionment, but the process it still manual. What about automating it? Depending on the solution used for the application and other services in the infrastructure, there are different choices to automate. One will be to set up counters in configuration storage and increased log level can be set when the counter exceeds given number (also configurable). Another approach is to write an application that monitors the behavior of infrastructure and turns on the excessive logging with a number of rules. When established, along with monitoring and alerting system, it becomes a powerful tool to prevent and overcome disasters in the application.

## Conclusion

Logging might seem to be the least important thing compared to business needs and feature requests from the customers. But still, it is very important. And depending on the time, when a company will start to implement it in more correct and robust way the costs of the process will differ dramatically. Start the process as early as you can to save effort and time in future.
