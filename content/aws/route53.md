---
title: "Route 53"
date: 2018-11-26T15:36:16-08:00
draft: false
---

# Route 53
## Summary
Route 53 is Amazons DNS service

## Routing Policies
* Simple Routing
* Weighted Routing
* Latency-based Routing
* Failover Routing
* Geolocation routing
* Multivalue Routing

## Simple Routing
It is the default for when you create a new record set and is most commonly used for basic sites that have a single server serving a website and has no intelligent type of routing.

## Weighted Routing
With weighted routing you can choose to have a percentage of the traffic routed to a specific resource or instance. A good reason you would do this is to forward traffic to a certain instance to test out a new feature to a percentage of users.

## Latency Routing
This allows you to base routing on what will be the lowest network latency available. 

## Failover Routing
Are used for an active/passive set up. When the active site is down it will then point to the back up passive site.

## Geolocation Routing
This is fairly straightforward. it will see the general location of the requester and route it/them to the appropriate instance. 

## Multivalue Routing
Allows you to randomly distribute traffic to resources and take out unhealthy ones.

## Alias Record
You set the domain name to the resource you would like to use.
