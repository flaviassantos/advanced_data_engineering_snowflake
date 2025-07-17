## IaC

In practice, the workflow looks like this:

Create GitHub repository to version control the code
Develop Terraform code to manage Snowflake objects
Setup config files and initialize the Terraform Provider
Plan the changes on Snowflake
Apply the changes to Snowflake

https://www.youtube.com/watch?v=chqyASQ_Rrg

---
## Scenario briefing

In this repo, you'll play the role of a data engineer on the Tasty Bytes team. Tasty Bytes is a fictional food truck company that runs 450 food trucks around the world. Here's the scenario:

You work directly with analysts that track the sales performance of Tasty Bytes food trucks. On occasion, they approach you for help on pinpointing exact causes behind unexpected food truck performance, or for help building pipelines to extract new insights.

Recently, they've approached you with concerns about the performance of a food truck in Hamburg, Germany. Weve learned from sales analysts on the tasty bites team that sales in the city of Hamburg, Germany mysteriously dropped to zero for nearly the whole month of February. Weve been tasked with wrangling the data and figuring out what may have happened. Lets use the raw data we've loaded and performed some transformations to pinpoint the exact cause

### Streams 

so far, we've performed our transformations and calculations against entire sets of data. Every time you wanted to modify our views like Daily City Metric V, for example, we reprocessed every single row in that view to do so. But what if we could focus on only processing rows with changes rather than all of the rows within a table or view? That would be far more efficient. For example, let's say you have a table with 20 million rows. You need to calculate an aggregate value like a sum, using a column in that table, and you need to recalculate this value daily because new data is added to this table every day. If say only 1,000 rows are added to the table overnight, do you really need to reprocess the other 20 million rows to perform your aggregate calculation? Thankfully, no, and this is where streams come in. 

Stored procedures are incredibly powerful. They make it easy to take large swaths of logic, place them in a centralized location, and then reuse them as needed. It's incredibly common to use them to perform aggregations, to update records, perform complex procedural logic


# Errata
````
snow git execute @advanced_data_engineering_snowflake/branches/main/module-1/hamburg_weather/pipeline/data/load_tasty_bytes.sql -D "env='STAGING'" --connection advanced_data_engineering_snowflake --database=COURSE_REPO --schema=PUBLIC
````
