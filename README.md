# Kickstarting with Excel

## Overview of Project
Louise recently put on a play which almost reached its goal, but not quite. Now she wants to know how successful or unsuccessful other plays were using goal amount and launch date.

### Purpose
The purpose of this analysis will be to help Louise decide when the best time would be to start a fundraising campaign for theater plays and how much she should set as her goal.

## Analysis and Challenges
I started by using the spreadsheet titled "Kickstarter" to create a PIVOT table in a new tab. I named the tab Theater Outcomes by Launch Date. I used the Years and Parent Category for filters and ungrouped the Years by month. Months are in the x-axis and outcomes are in the y-axis. Then I created a line chart based of that PIVOT table. I titled the chart Theater Outcomes by Launch Date

Then I used the Kickstarter sheet to add a new data table. The new table went on a new tab titled Outcomes based on Goals. I typed in the column headers using the outcomes "successful", "failed", and "canceled". In the rows I use pre-determined goal ranges. 

I created a `COUNTIFS()` formula to calculate the number of successful, failed, and canceled projects within the given goal range:
```
=COUNTIFS(Kickstarter!$D:$D, "<1000",Kickstarter!$F:$F, "successful",Kickstarter!$R:$R, "plays")
```
A `SUM()` formula to total the successful, failed, and canceled projects within the given range:
```
=SUM(B2:D2)
```
and divide by formulas to calculate the percentage of successful, failed, and canceled projects:
```
=(B2/E2)
```
Here is the result of that data table.
![Kickstarter-Outcomes_vs_Goals](https://github.com/brown-rox20/kickstarter-analysis/blob/main/Kickstarter-Outcomes_vs_Goals.png)

Using that data table I created a pivot table with goal-amount ranges on the x-axis and the percentage of successful, failed or canceled projects on the y-axis. I then changed the data type to percentage.
![Outcomes_vs_Goals-PIVOT](https://github.com/brown-rox20/kickstarter-analysis/blob/main/Outcomes_vs_Goals-PIVOT.png)

Next I created a line chart and titled it "Outcomes Based on Goal".
### Analysis of Outcomes Based on Launch Date
The best month for Louise to start her fundraising campaign is in June. We see the second highest rate of success in June as well as a decrease from the previous month in failed campaigns.
![Theater_Outcomes_vs_launch](https://github.com/brown-rox20/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
Louise would benefit most by setting her goal below $5,000.00. Goals set in the less than 1000 and 1000 to 4999 range had the highest rate of success while also having the lowest rate of failures.
![Outcomes_vs_Goals](https://github.com/brown-rox20/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
One difficulty I ran into was when I created the pivot table for Outcomes Based on Goal. The pivot table sorted the goal ranges from A to Z which caused the goal ranges to be out of order.
![Kickstarter-Challenges_Difficulties](https://github.com/brown-rox20/kickstarter-analysis/blob/main/Kickstarter-Challenges_Difficulties.png)

Though the data set looked at 1047 different fundraising campaigns for plays the data is spread out over a seven year span. It might be beneficial to find a more recent data set with more plays to measure.

## Results

- Two conclusion that can be drawn from Theater Outcomes Based on Launch Date is that there are significantly fewer canceled Theater campaigns and the successes and failures have relatively similar peaks throughout the months.

- In the Outcomes Based on Goals we can see that percentage of outcomes and goal ranges are inversely proportional to each other.

- One limitation the data has is that it's a relatively small sample size for the amount of years it covers.

- Here is another way to look at Outcomes Based on Goals:
![Alt_Outcomes_Based_on_Goals](https://github.com/brown-rox20/kickstarter-analysis/blob/main/Alt_Outcomes_Based_on_Goals.png)
