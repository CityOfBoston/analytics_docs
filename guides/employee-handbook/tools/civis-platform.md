---
description: >-
  The platform we use for data warehousing, analytics, and reporting.
  https://www.civisanalytics.com/civis-platform/
---

# Civis Platform

## Introduction to Civis

## Getting Started

### What is Civis?

{% hint style="info" %}
If you don't see Civis in your Access Boston page, your manager should check to see if you've been added to the [Civis group](https://access.boston.gov/group-management) and that any temporary emails have been shut off if you've recently received a permanent email address.
{% endhint %}

## Query Pane

## Jupyter Notebooks

## Import, Export, and Transform Modules

## Workflows

### Email Triggers

Email triggers are a way to run a workflow or job in Civis in addition to or instead of the regular scheduling function. An email trigger is a unique email address that Civis can generate for a job which, when emailed, starts the job it's associated with. It looks something like this:

`console-inbound+run.67836378.05864b7b894943e7b12c879db180ce3a@civisanalytics.com`

#### How do I create an Email Trigger?

As mentioned previously, an email trigger can only be created on a **job** in Civis. To create an email trigger for an individual job:

1. Go to the job you want to use
2. Click on the automate button at the top
3. Scroll to the bottom and click "**Generate an email address** to trigger this job via email."

Read more about [Scheduling and Chaining Jobs in Civis](https://civis.zendesk.com/hc/en-us/articles/213752583-Schedule-and-Chain-Jobs).

#### How do I create an Email Trigger for a workflow?

If you want to generate an email trigger to start a workflow then we've made things a bit simpler for you. Under BostonRobot, you'll find a script template called "[Email Trigger](https://platform.civisanalytics.com/spa/#/scripts/new?type=custom&fromTemplateId=77467)" in Code &gt; More Script Templates.

Once you've clicked that, all you have to do is put the workflow id which you can find in the url when viewing the workflow. You would then generate the email address the same way we mentioned previously.

How this script template works is, it takes the workflow id you input and then uses the Civis API to kick off the workflow.

Once you've created your trigger and tested it, add it to the [Email Triggers project](https://platform.civisanalytics.com/spa/#/projects/134640) in Civis so you can easily find it again later, and please use the naming convention: **Email Trigger - {Workflow Name}**

![](../../../.gitbook/assets/image%20%283%29.png)

## Permissions

## Contract

