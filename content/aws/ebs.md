---
title: "EBS"
date: 2020-01-11T05:41:51-08:00
draft: false
---

# EBS

AWS EBS can be best described as hard drives that you can attach and detach from EC2 instances. It is important to note that only one EBS volume can be attached to only one EC2 instance at a time. AWS EBS is meant to store data that is change pretty frequently and needs to exist beyond the lifespan of an EC2 instance, such as a database filesystem. The different types of EBS volumes can be broken down into two catagories HDD-backed volumes and SSD-backed volumes. Since EBS volumes are network-attached devices other network IO loads on the EC2 instance might affect the performance of the EBS volume. 

## HDD-backed Volumes

### st1 (Throughput Optimized HDD)
st1 instances are idea for frequently accesses throughput intensive workloads that have large IO sizes and datasets where the dominant performance attribute is throughput such as streaming, big data, log processing, and data warehouse.

### sc1 (Cold HDD)
sc1 is the lowest cost EBS volume type and are ideal for infrequently accessed workloads with large, hardly used datasets with large IO sizes. 

## SSD-backed Volumes

### gp2 (General Purpose SSD)
gp2 is cost-effective storage that is used for a broad range of workloads. generally if you have a project that does not seem to meet the specifications of the other instance types then this would be a good volume type to choose.

### io1 (Provisioned IOPS SSD)
io2 is best suited for workloads that are expected to have IO intensive workloads with small IO size and the major attribute being IOPS. Such as databases that are sensitive to storage performance.