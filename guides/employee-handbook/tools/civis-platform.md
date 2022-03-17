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

## Civis Backend Database

Our instance of Civis is backed by a [PostgreSQL](broken-reference) database (Amazon RDS) and can be connected to like any other database. In order to connect, you must be using your computer at City Hall.

### Connecting to the Civis Database

In order to connect directly to the Civis database, you must first have a SQL client installed. We recommend one named [DBeaver](broken-reference) and the following instructions will be for DBeaver.&#x20;

1. Install DBeaver and open it
2. Follow the [database connection guide](broken-reference) choosing PostgreSQL as the database type
3. Once you get to the connection settings part, use the following info:
   1. Host, Database, and Port: [Click here to view](https://app.gitbook.com/@boston/s/analytics-internal/guides/civis/connecting-to-civis-in-dbeaver)
   2. Username and Password: Given to you by [Analytics Team](../../../#connect-with-us) or one you set if you have a Civis Platform account
4. Click Finish

Now you should be able to [view all of the schemas and tables/views](https://github.com/dbeaver/dbeaver/wiki/Database-Navigator) you have access to!

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

If you want to generate an email trigger to start a workflow then we've made things a bit simpler for you. Under BostonRobot, you'll find a script template called "[Email Trigger](https://platform.civisanalytics.com/spa/#/scripts/new?type=custom\&fromTemplateId=77467)" in Code > More Script Templates.

Once you've clicked that, all you have to do is put the workflow id which you can find in the url when viewing the workflow. You would then generate the email address the same way we mentioned previously.

How this script template works is, it takes the workflow id you input and then uses the Civis API to kick off the workflow.

Once you've created your trigger and tested it, add it to the [Email Triggers project](https://platform.civisanalytics.com/spa/#/projects/134640) in Civis so you can easily find it again later, and please use the naming convention: **Email Trigger - {Workflow Name}**

![](<../../../.gitbook/assets/image (3).png>)

## Permissions

## Schemas

### Creating New Schemas

There are three types of schemas that you can create: **open\_data**, **internal\_data** and **restricted\_data**. You can read more about these in the [Data Classification](broken-reference) section.

In order to make sure each new schema that gets created has the correct permissions, we've created script templates that you can run in Civis which will create the necessary groups, assign permissions, and update existing groups for you.

{% hint style="info" %}
Only users in the admin group can create new schemas.
{% endhint %}

#### Open & Internal Schemas

Both open and internal schemas can be created with the same script template below. The script template will change what it does based on whether the schema name contains **open\_data** or **internal\_data** in it.

{% embed url="https://platform.civisanalytics.com/spa/#/scripts/sql/39625074" %}
Parameterized SQL job in Civis that uses the source code below. Just enter in a schema name and run.
{% endembed %}

{% embed url="https://github.com/CityOfBoston/civis_pipelines/blob/master/utils/create_new_schema_open_and_internal.sql" %}
Source code for creating open and internal schemas.
{% endembed %}

#### Restricted Schemas

Similarly, the restricted schema script template will assign the appropriate permissions for a restricted schema and only a restricted schema. It must have restricted\_data as the suffix otherwise it will raise an error.

{% embed url="https://platform.civisanalytics.com/spa/#/scripts/sql/61096138" %}
Parameterized SQL job in Civis that uses the source code below. Just enter in a schema name and run.
{% endembed %}

{% embed url="https://github.com/CityOfBoston/civis_pipelines/blob/master/utils/create_new_schema_restricted.sql" %}
Source code for creating restricted schemas
{% endembed %}

#### Other Schemas

If you need to create a schema that fits outside of the logic above, this should be a flag to consider your other options. While nothing will stop you from creating a schema without a template, we have permission unit tests that will catch and flag schemas that aren't created properly and are a security risk.

### Granting Access To Schemas

Users are granted access to schemas via [roles](https://app.gitbook.com/@boston/s/analytics-internal/guides/civis/civis-platform-management#database-roles) instead of directly adding them to the schema. The only exception is restricted schemas which go through a [review process](broken-reference) and access is normally temporary and taken away after the work is completed.

{% hint style="info" %}
Only users in the admin group can grant access to schemas.
{% endhint %}

Below are a few example scenarios (see [Postgres Grant](https://www.postgresql.org/docs/current/sql-grant.html) for all options):

{% tabs %}
{% tab title="New User (Analytics Team)" %}
```sql
-- All open data and sandbox write access
GRANT sandbox_write TO user_role;
```
{% endtab %}

{% tab title="Data Engineer (Analytics)" %}
```sql
-- All open data & internal data
GRANT bostonrobot TO user_role;
```
{% endtab %}

{% tab title="New User (x Team)" %}
```sql
-- Select access only to their department & all open data
GRANT x_internal_data TO user_role;

-- Gives write access to their department schema
GRANT x_internal_data_write TO user_role;
```
{% endtab %}

{% tab title="Restricted Access" %}
```sql
-- Allow user to use the schema
GRANT USAGE ON x_restricted_data TO user_role;
-- Allow user to use the table inside the schema
GRANT SELECT ON [TABLE] TO user_role;
```
{% endtab %}
{% endtabs %}

## Contract
