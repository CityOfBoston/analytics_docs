# Data Platform

## Overview

Historically, data has been siloed by departments and even within teams in each department which creates issues like multiple variants of important datasets, a decrease in data accuracy, difficulty in cross-department collaboration, and impedes the goal of Boston being a data-driven city. To combat these issues, we are building a [centralized data platform](https://statescoop.com/bostons-new-centralized-data-platform-is-its-starting-point-for-predictive-analytics/) for the entire City of Boston which serves as a single source of truth for its data. This allows each department to maintain ownership over their data but with built-in data best practices, tools, and support from our team. So, far we've onboarded 30 out of our 74 departments and are continuously working on breaking down our city's data silos.

In this guide, you'll find information and tutorials on all of the features of our data platform and how we maintain a strong data foundation that is accurate, reliable, and secure. At a high-level, we use a tool called [Civis Platform](employee-handbook/tools/civis-platform.md) for everything from querying/analyzing data to building automated pipelines, visualizations, and models. We also run our own infrastructure on [AWS](employee-handbook/tools/amazon-web-services.md) for custom applications, visualizations, and emergency situations.

## **Data Classification**

Before you start querying data, it's good to have an understanding of how data is organized and classified. All data stored in our data warehouse will be classified into one of the below three access level types, in accordance with our Data Governance Policy. 

### Open data

* No restrictions on internal use by any user of the platform or City of Boston employee. 
* Any data already shared on the [Analyze Boston](open-data.md) portal is classified as open data. However, not all data in open data schemas are published on Analyze Boston, it must first go through a [separate approval process](https://bostonopendata.knack.com/opendataapprovalpublication#processoverview/). All squares are rectangles but not all rectangles are squares.

### Internal data \(default classification level\)

* No restrictions on internal use by members of the Analytics team.
* Users from other teams must request access to each internal data schema they want, the data owner will approve the request prior to the requesting team being granted access. 

### Restricted data

* Anyone, including all members of the Analytics team, must request access on a table by table basis from the data owner using the [Data Access Request Form](https://bostonopendata.knack.com/DAR#home/). 

{% hint style="info" %}
An administrator of the Civis Platform can see all the data stored in the platform. By nature, the administrator role is designed to have full access.
{% endhint %}

## Querying Data

### Via Civis Platform

### Via a SQL Client

## Analyzing Data

### Jupyter Notebooks

## Importing, Transforming, and Exporting Data

### Civis Modules

### Custom Modules

#### Sandbox

{% hint style="danger" %}
Any table in `sandbox` is subject to deletion at any time - please do not build visualizations or automation on these tables. Also, storage of [restricted data](https://docs.boston.gov/analytics/guides/data-platform#data-classification) is **not allowed** in the`sandbox` schema.
{% endhint %}

## Data Pipelines

## Data Access Requirements

A summary of the type of data sharing we require from vendors and any party we pull data from automatically. Feel free to share with departments and external stakeholders.

{% hint style="info" %}
Please include the language below in any City of Boston data sharing agreement.
{% endhint %}

* The City must be able to programmatically \(not manually\) export the data at regular daily \(or more frequently if possible\) intervals. The City requires an export method which will allow for automated exports, without manual work. We will accept any type of API access or being provided a REST endpoint which will give us direct access to the data. A browser login where a person has to log into the portal and manually click a button to export the data is not sufficient. If an API is not possible, we will accept a daily upload of the data onto our SFTP site. The vendor must accept full responsibility for delivering the raw transactional data onto our SFTP site and be responsible for not missing any days of data.
* The format of the exported data must be either CSV, JSON, or another machine-readable format.
* The City must be provided with a data dictionary that describes the purpose of each column in each data table. The data dictionary must also describe all the possible values in each column if they are not obvious and how those values are defined in the system. For example, if there is a column for status with a few options for the type of status, then we need an explanation of what each status means. A diagram version of the data dictionary outlining all the columns is also encouraged. 
* If there is more than one table with data, and the tables logically relate to each other, the City must be provided with a [schema diagram](https://docs.oracle.com/database/121/COMSC/diagrams.htm#COMSC00016) of how each table connects to each other. It must outline primary and foreign keys used to connect the data. All data tables must logically connect to each other or you may provide an explanation of why a specific table does not connect to the rest of the data.

{% hint style="info" %}
[Here](https://docs.google.com/document/d/1R7_ONukFVptqRGmm1R4VpRpmQ9hyfwMMAqd6FsG5wgI/edit?usp=sharing) is a view-only version of this section. Share with anyone.
{% endhint %}

## Naming Conventions

### Schema Naming Conventions

**Overall guidelines:**

* All schema names align with the above Data Classification categories. 
* The prefix of each schema designates the department or project to which the data belongs. 
  * Data owned by the Environment department will be held in schemas prefixed with `env_` , and followed by `internal_data`, `open_data`, or `restricted_data` to correspond with access levels outlined above. 
  * Data coming from the 311 system doesn't have a designated department owner outside of DoIT, so it is prefixed with `lagan_311_` to indicate the project name. Same for Hansen/IPS data, it's prefixed with `hansen_` instead of `[department]_hansen_`. 
  * Data owned and generated by the Analytics Team is held in schemas prefixed with `analytics_` . 
  * In addition to the normal schemas, there is a `sandbox` schema meant for ad hoc and testing purposes of the Analytics Team.
* If you are a member of the Analytics Team, you will have full read access to any table in any `*_open_data` and `*_internal_data` schemas. 
* All `restricted_data` tables are on a person-by-person access only, you must [request it](data-platform.md#restricted-data) for yourself for a specific project.
* All members of the Analytics Team can write to the sandbox schema. Please read the [table naming guide](data-platform.md#table-view-naming-conventions) before creating tables.

{% hint style="success" %}
\[department acronym or project name\]\_\[[data classification level](https://docs.boston.gov/analytics/guides/data-platform#data-classification)\]
{% endhint %}

### Table/View Naming Conventions

In general, the table/view naming conventions make it easier to find datasets as well as quickly understand what is in them and what they are used for. Please think carefully about your table name. Don’t use extra filler words, don’t put your name into production tables \(ex: mbta\_alerts\_janedoe\), and make the table name be descriptive of what the purpose of the table is.

**Overall guidelines:**

* All table names should be **lowercase.**
* All table names should use [**snake case**](https://en.wikipedia.org/wiki/Snake_case)**.**

{% hint style="success" %}
\[**high\_level\_project\_name**\]\_\[**purpose\_of\_table**\]\_\[optional: **suffix** \(see below\)\]
{% endhint %}

Putting the high-level project name first will allow all tables to be grouped together and will allow all the related data to be located faster.

**Table/View Suffixes:**

* `_view` or `_vw` **-&gt;** represents this is a view and not a table
* `_staging` or `_stg` **-&gt;** represents a table that is temporarily used for computation

**Good Examples:**

* _mbta\_alerts_ **\(project and purpose are clear\)**
* _mbta\_alerts\_staging_ **\(clear this is a staging table\)**
* _mbta\_alerts\_previous\_24\_hours\_view_ **\(clear this is a view\)**

**Bad Examples:**

* _alerts\_mbta_ **\(project name should go first\)**
* _mbta\_alerts\_new_ **\(\_new implies there are now two versions of truth\)**
* _mbta\_new_ **\(unclear what data the table actually stores\)**
* _mbta\_alerts\_new\_test_ **\(ok in sandbox, never ok in production\)**
* _mbta\_alerts\_2_ **\(there is really never any reason for the \_2\)**

{% hint style="warning" %}
A table in the **sandbox** schema should have your initials prefixed in the table name, ex: a table created in sandbox by Jane Doe containing salaries should be labeled ****`jd_employee_salary`
{% endhint %}

### Column Naming Conventions

**Overall guidelines:**

* All column names should be lowercase.
  * Column names are case sensitive in Postgres.
* All column names should use [**snake case**](https://en.wikipedia.org/wiki/Snake_case)**.**
* Whenever possible and useful, make all the column names identical to the column names in the source data. 
* Column names may only be title case or uppercase in a view used for a report or application.

**Geospatial Columns**

{% hint style="success" %}
column\_name\_\[spatial\_reference\_number\]
{% endhint %}

### Data Pipeline Naming Conventions

Data pipeline definitions live in version control in GitHub but only become live when they are added in platform. This section talks about the naming conventions for both the definition and the in-platform workflow.

#### In GitHub

**Overall guidelines:**

* Group workflows together alphabetically by putting the high level project name first, ex: 311, Hansen.
* Designate the source and target \(import and export\) platforms of the data. 
* Make the workflow name in Civis and the yaml file name in Github as identical as possible to ease lookup.
* All data pipeline definition files should be lowercase.
* All data pipeline definition files should use [**snake case**](https://en.wikipedia.org/wiki/Snake_case)**.**

{% hint style="success" %}
project\_name\_from\_source\[\_source2\]\_to\_destination\[\_destination2\].yaml
{% endhint %}

**Good Examples:**

* covid\_john\_hopkins\_historical\_from\_github\_to\_civis
  * for a workflow that pulls COVID John Hopkins data from Github and imports it to Civis \(one source, one destination example\)
* tapas\_from\_googlesheet\_knack\_to\_arcgis.yaml
  * for a workflow that pulls data from a Google Sheet and a Knack form and uploads it to ArcGIS. \(multiple sources example\)
* mbta\_heatmap\_from\_mbta\_api\_to\_s3
  * for a workflow that pulls data from the MBTA API and uploads it to S3 for the MBTA heatmap project. 

#### In Civis Platform

The name of the workflow in Civis should be the same as the data pipeline definition yaml file name for that workflow, except replacing the underscores with spaces and applying capitalization rules.

**Example:**

* covid\_john\_hopkins\_historical\_from\_github\_to\_civis **-&gt;** COVID John Hopkins Historical from Github to Civis

### Data Unit Test Naming Conventions

The data unit test files located in [civis\_pipelines/test/data unit test/expectations/](https://github.com/CityOfBoston/civis_pipelines/tree/master/tests/data_unit_tests/expectations) should be named after the table they are running the data unit test on.

**Overall guidelines:**

* Name the data unit test after the table name \(including schema\).
* Use a hyphen between the schema/table name \(a . causes parsing issues\).
* All data unit test names should be lowercase.
* All data unit test files should use [**snake case**](https://en.wikipedia.org/wiki/Snake_case) ****\(except the hyphen\).

{% hint style="success" %}
\[schema\]-\[table\].json
{% endhint %}

**Example:**

* analytics\_open\_data.moving\_truck\_permits **-&gt;** analytics\_open\_data-moving\_truck\_permits.json

## [Networking](https://docs.boston.gov/analytics-internal/guides/networking)

## File-Sharing Server

Also known as transfer.boston.gov or the SFTP Server, the file-sharing server is used in situations where you need to share large files or sensitive information [which shouldn't be shared via email](https://docs.boston.gov/analytics/guides/employee-handbook/security#everything-is-public-record). It acts just like a shared folder on your computer and you can access it at [transfer.boston.gov](https://transfer.boston.gov/) via a web browser or via an SFTP client such as WinSCP or FileZilla.

{% hint style="success" %}
Need an account? Email the [Analytics Team](mailto:analyticsteam@boston.gov) and we can [create one for you](employee-handbook/tools/serv-u.md#add-a-new-user).
{% endhint %}

**Example \#1:** A vendor needs to send us data automatically and we can't connect to their database directly. They could set up a job that sends files to a secure area in our file-sharing server.

**Example \#2:** You need to send a file containing sensitive information to someone in a different department.

{% hint style="warning" %}
We previously used an IP address directly for certain use-cases but that has been **deprecated**. If you're still using an IP address, please switch to using [transfer.boston.gov](https://transfer.boston.gov/) as the host.
{% endhint %}

