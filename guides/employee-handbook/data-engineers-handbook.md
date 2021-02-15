# Data Engineer's Handbook

## Toolkit

| Name | What we use it for |
| :--- | :--- |
| [Civis Platform](tools/civis-platform.md) | Querying our data warehouse, running data pipelines, Jupyter notebooks, reports, and ML models. |
| [DBeaver](tools/dbeaver.md) | Writing/running SQL queries against multiple types of databases as well as database management. |
| [VSCode](tools/visual-studio-code.md) | Writing, testing, and debugging code \(mostly Python, SQL, and YAML\). |
| FileZilla | Accessing data on SFTP servers. |
| [GitHub](tools/github.md) | Version controlling our code. |

## Development Environment

## Data Pipelines

## Code Review

Version control is a mean to both backup code and track changes over time. While most software companies tend to operate under the "work quickly and break things" principle. This is mainly possible with continuous testing and deployment cycles, but since the City of Boston is a municipal goverment, we operate on a slower pace than most our industry friends.

While a monorepo with no development branch is the latest trend for software, we use the old model of two branches. This is to ensure that at least one branch will be working at any given moment, and to facilitate a larger number of code reviews than most companies employ.

#### Branches

All branches are on the [civis\_pipelines](https://github.com/CityOfBoston/civis_pipelines) repo:

* Master branch is production code. It will locked down to only admins.
* Develop branch is the final checkpoint development branch into which all new code is merged for testing. Serves as the final staging branch.
* Various feature specific branches are the first pass at writing new code. When developing new code, create a new branch and name it logically to describe what you are doing on it.
* Add a year & month to the feature branch name, all feature branches will be deleted after a year.
* Please make sure that all commits are **descriptive**. They should give a good idea on exactly what your changes are for.

### Our Development Process

#### Step 1:

* Create new feature branch, fork it off the **develop** branch. Name it something that **specifically** describes your addition to the code. Ex: spatial-snap-class. 
  * Branch names should describe exactly what you are working on, not just the name of the project
* Write your code on it. Run the code on the isolated development environment on the ETL server. This will ensure you can break things while you are developing and no one will get upset. More on that below.

#### Step 2:

* When you are ready to commit the code into the main code base, open a pull request from the feature branch you created into the develop branch.
  * Set yourself as the Assignee.
  * Tag a person as the Reviewer.
    * Optional: if you want to tag someone with an ‘FYI good for you to check this out’, set them as the second Reviewer. This implies they should read over the pull request and acknowledge that they read it, but doesn’t make them responsible for the code.
* **Squash** all your commits when merging to the develop branch.
* This will kick off automated tests, as well as alert the reviewer that they have been tagged. The tests will check that all things in the Production Checklist below are done.
* The reviewer will get automatically notified by our slackbot

#### Step 3:

* The reviewer will take a look at the code \(all pull requests will be prioritized to happen as quickly as possible by the reviewer\). Please review the code within 24-48 hours but talk to your manager if you are unsure about priorities.
* The reviewer will either reject or approve.
  * If a rejection occurs, the reviewer will leave comments. Address the comments and re-request a review.
  * An approval means the code is good to go.

#### Step 4:

* Once the code was approved, merge the pull request into the develop branch.
* Unless you have specific reason not to, open a second pull request from develop into master branch.
* Delete your feature branch \(any feature branch over a year old will be deleted\)
* Ensure that the second round of checks between develop and master is conducted by at least one person

