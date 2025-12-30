## Purpose:
This repo was intended to be a study of "Resolving The Fan Trap with Sigma and Snowflake UDF" published by Sigma Analytics using Microsoft Power BI.  <br> https://quickstarts.sigmacomputing.com/guide/tables_fan_traps/index.html#0 <br>
I found problems in the data provided for the tutorial.  Some of the data provided was missing values needed for the study, but those were easily remedied.  However; the data provided to demonstrate aggregation issues for denomralization was incorrect.  The amount value provided in the events csv should have been a product of qty and price.  However; it was incorrect.  It's possible that when the data was saved to the csv that the incorrect, filtered data was saved rather thant he correct original data. I decided to scrap this project and archive this repo. I can't recommend this website as a resource for people learning this concept.<br>
## Data Source:
This study uses the sample .csv files available in step 2, "Data Modeling" of the walk through. https://quickstarts.sigmacomputing.com/guide/tables_fan_traps/index.html#1 <br>
I used Power BI instead of Sigma and did not use Snowflake.   <br>
### Step 3 of the tutorial notes
https://quickstarts.sigmacomputing.com/guide/tables_fan_traps/index.html#2, shows the relationships between the .csv tables.  <br>
<ol>
  <li>The events.csv was missing event name and attendance. I manually created the columns as conditional columns using the event id in Power Query.</li>
  <li>Power BI accurately connected the tables, but did not set up the relationship between events and order_header as one to many.  I manually updated it.</li>
  <li>I removed any autosumming that PBI set up.</li>
  <li>I created the LEFT OUTER JOIN in Power Query using Merge Queries as new and called the resulting table, "Step 3 1st Join" when I expanded the join, I took all the columns including the duplicates as in the tutorial - this creates a denormalized table. </li>
  <li>I removed any automatic relationships that PBI set up with the new merged table and the existing tables. </li>
  <li>I once again chose Power Query Merge Queries as new for the second join which pulled in order_details to the new table so as to not corrupt prior data. </li>
  <li>This join required joining order_details to the order_header using the orderid for those tables. Intrestingly, this triggered a Privacy Level warning in PBI.  I checked ignore. </li>
  <li>Once again, I removed automatic relationships and autosum.  I named this table, "Step 3 2nd Join"</li>
  <li>I also hid order_header.event_id column and order_details.order_id column from final report.</li>
  <li>When I duplicated step #4, I found that the price column was missing.  I added a conditional column based on product and made up a value for cracker jacks.</li>
  <li>When I Tried to duplicate the fan out issue, I found that the amount included in the order_header table .</li>
</ol>


