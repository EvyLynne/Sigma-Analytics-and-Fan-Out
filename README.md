## Purpose:
This repo is a study of "Resolving The Fan Trap with Sigma and Snowflake UDF" published by Sigma Analytics using Microsoft Power BI.  <br> https://quickstarts.sigmacomputing.com/guide/tables_fan_traps/index.html#0 <br>
## Data Source:
This study uses the sample .csv files available in step 2, "Data Modeling" of the walk through. https://quickstarts.sigmacomputing.com/guide/tables_fan_traps/index.html#1 <br>
I used Power BI instead of Sigma and did not use Snowflake.   <br>
### Step 3 of the tutorial notes
https://quickstarts.sigmacomputing.com/guide/tables_fan_traps/index.html#2, shows the relationships between the .csv tables.  <br>
<ol>
  <li>Power BI accurately connected the tables, but did not set up the relationship between events and order_header as one to many.  I manually updated it.</li>
  <li>I created the LEFT OUTER JOIN in Power Query using Merge Queries as new and called the resulting table, "Step 3 Join" when I expanded the join, I took all the columns including the duplicates as in the tutorial - this creates a denormalized table. </li>
  <li>Third item</li>
</ol>


