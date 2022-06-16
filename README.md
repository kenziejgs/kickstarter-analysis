# An Analysis of Kickstarter Campaigns
Analyzing the outcomes of various kickstarters with a focus on theater kickstarters
---
## Overview of Project
This project utilized a dataset detailing the outcomes, initial dates, final dates, number of backers, and total pledged (among other variables) for a wide variety of Kickstarter campaigns. From within this dataset the client was primarily focused on the outcomes for Kickstarter campaigns in the theater world, specifically plays. In order to guide the client to a successful launch of their potential Kickstarter campaign, I wanted to demonstrate the outcome of various theater Kickstarters based upon their start date as well as their initial goal.

## Analysis and Challenges
#### Theater Outcomes by Launch Date
###### Analysis
In order to best guide the client towards the optimal launch date for their potential Kickstarter campaign, I examined the data for any trends on outcome based upon launch dates. After converting the original launch dates from Unix format to readable dates, it became much easier to work with our data.

From the converted dates, the year for each datapoint was pulled into a separate column entitled "Years" using the `=year` function on Excel. This column was used in creating a Pivot Table with "Years" and "Parent Category" as possible filters, the "Date Created Conversion" as the rows and "Outcomes" as the columns and values, pictured below.

![PIVOT TABLE](https://github.com/kenziejgs/kickstarter-analysis/blob/43286c6a71ceda73ea5a80050c1ce9a6a90b39e3/Screen%20Shot%202022-06-15%20at%205.50.45%20PM.png)

From this point, I was able to filter the data by "Parent Category" or "Years" to better aid the client. I filtered the data set by "Parent Category" to display only theater Kickstarter campaigns and created a line chart to depict the outcomes based upon which month of the year the Kickstarter campaign was launched. This chart can be seen below.

![Theater Outcomes by Launch Date](https://github.com/kenziejgs/kickstarter-analysis/blob/918e3ad43963d5c2430b14ff6bbfcdf5259459f2/Resources/Theater_Outcomes_vs_Launch.png)

###### Challenges
One challenge with this particular analysis was the creation of the Pivot Table as shown. The rows category started out with three separate options for measuring the "Date Created Conversion" data and it required the analyst to remove the extra options of "years" and "quarters." This left us with the "Dates Created Conversion" variable being measured by month, which is the most likely to be helpful for the client.

Another challenge that had to be addressed was the concatenation 
