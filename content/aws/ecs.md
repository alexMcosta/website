---
title: "ECS"
date: 2018-11-12T07:01:05-08:00
draft: false
---

# ECS
## Summary
“An Amazon ECS cluster is a regional grouping of one or more container instances on which you can run task requests. Each account receives a default cluster the first time you use the Amazon ECS service. Clusters may contain more than one Amazon EC2 instance type.” - AWS

ECS (Elastic Container Service) allows you to  manage docker containers on a cluster of EC2  instances. It is basically AWS’s version of managing  Docker.

### ECS Task Definitions
Task definitions are required to run docker containers on ECS. They  are in JSON format and consist of essentially a blueprint of the containers that make up your application.  It can contain information like how much CPU should be used per container, how much memory per container, whether there are multiple containers for a task, or even which Docker images to use with the containers making up your task.

### ECS Services
Allows auto scaling of groups in ECS. I really do not have much more to say about it until I poke around it more.

### ECS Clusters
A group of containers you can place tasks on.  Containers can only be part of one cluster at one time. Are region specific and you can also create IAM policies for your clusters.

### ECS Schedulers
#### Custom Scheduler
Pretty self explanatory . It is a custom built scheduler to meet your needs.
#### Service Scheduler
Makes sure that certain tasks are running at certain times,  and makes sure tasks are re scheduled if a task fails. Only hearing about this and not using it it seems like it would be useful for cron-jobs

### ECS Container Agent
Only supported on EC2 instances with Linux. 

### Limits
1000 clusters per region
1000 instances per cluster
1000 tasks per service
500 services per cluster
10 containers per Task Definition
10 Tasks per host
1 load balancer per service