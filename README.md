## Sales Analysis using SQL

/*
Title: Sales Count Status Analysis

Description:
This SQL query categorizes sales counts into different status levels based on the number of activated MSISDNs. It retrieves data from the 'Above_49Sales_perDay' table in the specified database and assigns a status label to each record based on the following criteria:
- 'less than 60' for sales counts below 60
- 'B/w 61-80' for sales counts between 61 and 80
- 'more than 80' for sales counts above 80.

Purpose:
The purpose of this analysis is to categorize sales counts into meaningful status levels for further analysis and reporting. This information can help identify trends and patterns in sales activities.

*/

-- Selecting all columns from the 'Above_49Sales_perDay' table and adding a new column for count status
SELECT *,
       CASE 
            WHEN [ActivatedMSISDNCount] < 60 THEN 'less than 60'
            WHEN [ActivatedMSISDNCount] BETWEEN 61 AND 80 THEN 'B/w 61-80'
            ELSE 'more than 80'
       END AS CountStatus
FROM [dbo].[Above_49Sales_perDay];
