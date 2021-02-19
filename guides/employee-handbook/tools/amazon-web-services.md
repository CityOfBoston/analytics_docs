# Amazon Web Services

## What is AWS?

Amazon Web Services \(also referred to as AWS\) is a cloud provider - this means a supplier of servers and resources that are easily accessible online. Cloud servers come with several advantages to enterprise servers for small teams, namely that with proper usage typically only used infrastructure is paid for.

In other words, you only pay for what you use. This is in contrast to an on-premise server, where regardless of whether you use 1 node or all the nodes, you have to pay for the server and its power costs.

## Philosophy

A cloud strategy will always favor infrastructure as code as the most important piece of the cloud is the ability to replicate its features. At the City of Boston, we use [Terraform](https://www.terraform.io). This is to prevent vendor lockout, and more importantly, allow us to work on an open-source platform.

Terraform is an Infrastructure as Code software product that allows you to backup and deploy your entire cloud architecture as lines of code. This is invaluable when migrating to another cloud account or provider, and when things go wrong \(as they always do\)

## Services

### EC2

This service allows us to create servers on-demand.

{% hint style="danger" %}
Be very careful about your security settings for all EC2 instances. Improper security settings can lead to the VPC being hacked.
{% endhint %}

### [S3](https://s3.console.aws.amazon.com/s3/home)

S3 stands for Simple Storage Service and we use it mostly for storing large volumes of raw data like backups of databases. You can think of this as the equivalent of file storage \(a folder on a computer\).

### [Secrets Manager](https://console.aws.amazon.com/secretsmanager/home)

We use secrets manager to store credentials for all of our applications and accounts.

