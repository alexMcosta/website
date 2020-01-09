---
title: "Glacier"
date: 2020-01-09T05:48:16-08:00
draft: false
---

# Glacier

AWS Glacier is used for archival data and long term data store. It is low cost at as low as $0.0007 per Gigabyte a month at the time I am writing this. The reason that the price of the storage is so low is that it is expected that the data will hardly ever be accessed. When you do need to grab this data the retrieval process can take 3 - 5 hours.

## Archives
The data that is stored in Glacier is known as an archive. An archive can be a single file or multiple files and requires an initiation job to pull the archives back out of AWS Glacier. A single archive size limit is 40TB 

## Vaults
You organize your archives into Vaults. I like to think of vaults as the buckets of Glacier all though I am sure that is not an accurate way to think of them. You can lock vaults where long-term record retention is need to adhere to regulations or compliance. You can use these lockable policies on each individual vault and requires a few steps in order for the lock to initiate as a fail safe to not lock you out of data that that you do not want a lock on.

## Security
You can monitor access to AWS Glacier via CloudTrail. it also uses AES-256 encryption for data at rest.

## Lifecycle Policies
You can also set up lifecycle policies in S3 to have older data automatically archive into Glacier. When you do use lifecycle policies you are using the AWS S3 API and therefore you will have to retrieve the data via S3 UI or the S3 API and will not be viewable via the native glacier API or UI.

