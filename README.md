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

Another challenge that had to be addressed was the separation of the "Category and Subcategory" column. This data was much more useful to me as seperate variables, but the original worksheet had the two listed together. In this case, the category and subcategory were distinguished using a "/" between the two. This made it simple to break them into separate columns using the "Text to Columns" option in Excel. However, in some cases, this may be accomplished using the Excel `=LEFT` or `=RIGHT` functions.

#### Outcomes Based on Goal
###### Analysis
For this portion of my analysis, the goal was to demonstrate how a Kickstarter's initial goal impacted their success rate. This could help guide the client towards an appropriate goal amount for her project. In this case, I wanted to only show her the success or failure of Kickstarter campaigns similar to hers, so I needed to focus on the "plays" Subcategory specifically. It was also helpful to create large groupings of goal amounts because looking at the patterns with each distinct goal value would have yielded an outrageous number of different goals. In order to simplify the information and demonstrate general success rates by intial goal, I used the following breakdown of possible initial goals:

![Goal Values](https://github.com/kenziejgs/kickstarter-analysis/blob/c04c734211b305db878a247a491c84417bb990d7/Screen%20Shot%202022-06-16%20at%208.40.03%20AM.png)

In addition to these goal categories, each possible outcome was counted into seperate columns labeled "Number Successful," "Number Failed," and "Number Canceled." In order to measure how many Kickstarter campaigns falling into the "plays" Subcategory were successful, failed or canceled, I used the `=COUNTIFS` formula in Excel to count a campaign _ONLY_ when it met all of the requirements described in the formula. The formula was written to require that each data point was assessed based on the following criteria (found in the original Kickstarter worksheet) before being counted:

* the initial Kickstarter goal value
* the subcategory
* the outcome

For example, for the lowest goal grouping of "Less than 1000" in the "Number Successful" column, the formula was written to only count items with a goal less than $1000, that were designated as "plays" and had "successful" indicated in the outcomes column. This formula was written like this:
```
=COUNTIFS(Kickstarter!D:D,"<1000",Kickstarter!R:R,"plays",Kickstarter!F:F,"successful")
```
This same premise was used throughout the entire worksheet, depending on the criteria specified for the column and row. The only additional caveat to this process worth mentioning is that the formula has additional criteria to consider when the goal range is between two numbers, rather than simply less than $1000. This formula looks nearly identical, but is shown below:
```
=COUNTIFS(Kickstarter!D:D,">=1000", Kickstarter!D:D, "<=4999", Kickstarter!R:R,"plays",Kickstarter!F:F,"successful")
```
Once this was completed for all possible categories, I calculated the total number of Kickstarters falling into the subcategory "plays" for each goal grouping with a simple `=SUM` formula and calculated the percentage of succesful, failed and canceled Kickstarter campaigns for each goal category. This left the following spreadsheet from which I could create a visualization:

![Outcomes Spreadsheet](https://github.com/kenziejgs/kickstarter-analysis/blob/b865dcd8dbffc57671f385a9dd0d7f84654b546b/Outcomes%20Spreadsheet.png)

From this information, I used the data in the various percentage columns and the "Goal" column to create a line chart visualizing how many Kickstarter play campaigns were successful or failed based upon their initial funding goals.

![Outcomes Chart]()
