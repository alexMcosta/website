---
title: "SQS"
date: 2018-11-30T16:33:59-08:00
draft: False
---

# SQS
## Summary
SQS stands for Simple Queue Service. It is a messaging service that stores queued messages while waiting for a computer to process them.

* Oldest AWS service.
* Pull based system.
* Default retention is 4 days. With 1 minute being the minimum and 14 days being the maximum.
* Messages are 256kb in size.

## Types Of Queues
### Standard Queue

* Default.
* Unlimited transactions per second.
* Messages will be delivered at least once.
* Messages are usually delivered in the order given but can not be guaranteed.

### FIFO Queues
* Will come in FIFO order
* Message delivered once and is available until the consuming process deletes it.
* Limit of 300 transactions per second.

## Polling
By default SQS uses **SHORT POLLING** to constantly check SQS to see if there is a message to process, even if there are no messages available in the queue. To save money you can use **LONG POLLING** since it does not return a response until a message is in the queue or it times out.

## Visibility Timeout
After the reader pulls the message the message in the SQS queue becomes "invisible". the Visibility Timeout is the time that the message is invisible. If the message is processed during this timeout period then it will be deleted from the queue. If the job is not processed **WITHIN THE VISIBILITY TIMEOUT PERIOD** then the message will reappear in the queue and has a chance of being processed again.

* Default is 30 seconds.
* Max is 12 hours.