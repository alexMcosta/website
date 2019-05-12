---
title: "Projects"
date: 2019-05-12
draft: False
---

# Projects
___

## [Narkwhal](https://github.com/alexMcosta/narkwhal)

Narkwhal is a CLI that goes through an AWS account and removes parked EBS volumes based on user specified criteria. 

### Current Features:

- Looking through multiple accounts.
- Looking through multiple regions.
- Inactivity of volumes based on time using Cloudwatch metrics.

### Future Features:
- Ability to select which volumes to delete not just all that match params.
- Ability to take a `.yaml` file that holds configuration so it can run as a cron job.
- Notify admins of volume deletion.
- Ability to tag a volume to be ignored by Narkwhal for X amount of time.

___