---
title: "Projects"
date: 2019-05-26
draft: False
---

# Projects
___

## [Narkwhal](https://github.com/alexMcosta/narkwhal)

![alt-text](https://i.pinimg.com/originals/74/68/f1/7468f1d665e551fad8eac0c9f97977e3.jpg)

Narkwhal is a CLI that goes through an AWS account and removes parked EBS volumes based on user specified criteria. 

### Current Features:

- Looking through multiple accounts.
- Looking through multiple regions.
- Inactivity of volumes based on time using Cloudwatch metrics.

### Future Features:
- Ability to select which volumes to delete not just all that match params.
- Ability to take a `.yaml` file that holds configuration so it can run as a cron job.
- Notify admins of volume deletion.
- Ability to tag a volume to be ignored by Narkwhal for X amount of times.

___

## [Gatfish](https://github.com/alexMcosta/gatfish)

![alt-text](https://cdn.drawception.com/images/panels/2015/1-5/PChhFFR6ym-8.png)

Gatfish is a program that that governs AWS resource's tags based on the level of requirements that are needed. Gatfish can handle multiple different AWS accounts as long as Gatfish is ran with access to the `.aws/accounts` file.

At this time Gatfish is currently in development with the following features being on the MVP:

- Ability to take multiple accounts
- `ALL` setting that will enforce whatever level wanted on all resources
- `DIRE` tag setting that will immediately terminate a resource if the tag is not on the resource. It will output this to some logs
- `REQUIRED` tag setting that will stop the resource if it is able. and output the resource ID to the logs.
- `WANTED` tag setting that will only output to logs that the resource was not tagged.
- `AUTO` tag setting will auto add a tag to a resource if it can find the tag.
- Results will be exported in two formats. `JSON` and a human readable `.txt` file that will also come with stats such as percentage of resources that do not meet the requirements as well as the biggest culprits by gathering information from Cloudtrail. 

___