### CowJacket dbt Cloud Implementation

CowJacket wants to adopt dbt as their transformation tool in order to standardize transformations, simplify testing, improve lineage visibility, and make it easier to manage transformation workflows. You have been asked to set up the dbt Cloud environment and use the [SQL module data](https://github.com/dataengineering-community/launchpad/tree/main/04-SQL) as source.

You are to:

- Set up a dbt Cloud account and create three environments: dev, staging, and production.
- The staging environment is where the dbt Cloud CI job will run.

Follow the three-layer modeling approach:

- staging/
- intermediate/
- marts/

The project should follow a direct promotion strategy, where a dbt Cloud CI job is triggered automatically for every pull request. Once approved, models can be promoted directly to production.

Your project should also include:

- seeds/
- sources/
- models/
- exposures/

At least one model should materialize to a different dataset than the default one for the environment. For example, if the production schema is `analytics`, ensure a particular job writes to `analytics_marts`.

Put in place a guardrail so that this model does not materialize in production when running from the dev environment.

You are also expected to:

- Set up unit tests and data tests, including generic and custom tests.
- Put in measures to optimize test performance, especially for large datasets.
- Ensure that every model and column is properly documented.

For observability, make sure that every dbt run/build logs useful metadata into a warehouse table. This should include:

- model name  
- environment  
- duration  
- status  
- row count  
- and any other relevant metadata  

This will help the team monitor performance, debug issues, and track changes over time.

**Note:** You can use any data platform of choice (Snowflake, local or cloud-hosted supported databases).

## Submission:
Submit a link to your GitHub repo containing your solution.

Submit using this form - https://forms.gle/2wtvJTHBib4kb7cT7

**Duration:** 7 days

**Deadline:** 17/12/2025
