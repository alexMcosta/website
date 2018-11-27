---
title: "RDS"
date: 2018-11-27T14:05:39-08:00
draft: true
---

# RDS
## Summary
RDS is AWS's relational database hosting service.

## Databases Supported
* MySQL
* MariaDB
* PostgreSQL
* Aurora
* SQL Server
* Oracle

## Backups

### Automated Backups
* Enabled automatically.
* Allow to backup to any point of time within a retention period.
* Retention period is between 1 and 30 days.
* Also stores transaction logs.
* When doing a recovery. AWS will choose the most recent daily backup and then apply the transaction logs from the day.
* Can recover up to the second within a retention period.
* Backed up data stored to S3 and get free storage up to the size of your database.
* backups happen during the backup window time set.
* If RDS is deleted these backups will be deleted.

### Snapshots
* Are done manually.
* Stored even if RDS instance is deleted.

## Read Replica
Will copy each WRITE to the database to a replica databases that are used solely for READ access. This spreads the stress from the main database since most traffic online is READ.
**NOTE** Can have 5 read replicas per production database by default.
**NOTE** Not available for SQL Server or Oracle.

## Multi-AZ
This allows you to have an exact copy of your database in a different availability zone so that way when or if your main database fails or the availability zone is compromised than AWS will have the application automatically point to this replica database. This is not for performance improvement only disaster recovery.

## Other Notes
* **PORT 3306** You need to open up port 3306 to the EC2 security group your program is running on.
* **Encryption** Supports encryption at rest. This is done using AWS's KMS. Encryption includes the backups.