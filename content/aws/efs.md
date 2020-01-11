---
title: "EFS"
date: 2020-01-09T06:22:43-08:00
draft: false
---

# EFS

AWS EFS (Elastic File System) is a network file system as a service that allows you to connect multiple EC2 instances via mount targets in an AZ (Availability Zone) to concurrently access data files on the Elastic File System. EFS supports NFSv4 and NFSv4.1 but it is highly recommended to use NFSv4.1 so you can take advantage of scalability and parallelism features. You can create more then one EFS file systems in a region. EFS is ideal for growing data sets consisting of large files that need multi client access and higher performance. since this is a file system it is not ideal for use with relational databases, temporary storage, or archival storage. EFS is more ideal for application data and user directory storage.

