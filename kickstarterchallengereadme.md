# Kickstarting with Excel

## Overview of Project
Analyze the kickstarter campaign data in order to determine the outcomes of campaigns in relation to their respective launch dates and funding goals

## Analysis and Challenges
Across both analyses I used several functions including but not limited to: Year, Sum, Countifs & Pivot tables

### Analysis of Outcomes Based on Launch Date
I launched a pivot table including the data from the "Kickstarter Data" sheet.  That pivot table is included in the "Theater Outcomes by Launch Date" sheet.  

### Pivot Table Setup
The pivot table fields are in the following order: 
    Rows - Date Created Conversion
    Columns - Outcomes
    Filter - Parent Category, Years
    Values - Count of Outcomes
I filtered the table so that Parent Category = Theater.  
I also set the columns to show their values in Descending Order based on the Outcomes.

### Line Chart Creation & Images
After reviewing the pivot table, I created a line chart to review the data linearly over the course of the calendar year, Jan - Dec.  The image of this line chart is included in the resources folder of Week 1 Challenge link provided below:
 ![Theater_Outcomes_vs_Launch](https://github.com/Gkmb2390/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Conclusions for Outcomes Based on Launch Dates
1) Summer Months, May - Jul, saw the greatest number of successful campaigns launched in a given year.
2) October saw a significant rise in failed kickster campaigns, by comparison to the rest of the year.
3) Number of Successful campaigns vs Failed campaigns is roughly 2 to 1





### Analysis of Outcomes Based on Goals
Following step 3 in the setup of Outcomes Based on Goals. I input the Column Headers and Row ranges that were outlined.  
The requested countif formula necessitated that we only count campaigns according to their respective outcomes in the columns, within the ranges listed in their crossectional rows & that they be only inclusive of the "play" subcategory.

### Countifs Formulas Outline
In the first crossection cell,B2, "Number Successful" x "Less than 1000" I input the following formula:
 
 =COUNTIFS('Kickstarter Data'!$D$2:$D$4115,"<1000",'Kickstarter Data'!$F$2:$F$4115,"Successful",'Kickstarter Data'!$R$2:$R$4115,"plays",'Kickstarter Data'!$R$2:$R$4115,"plays")

In the following cell below, i.e. B3 - I adjusted the formula to include numbers in a range of value - respective to those values in A3, the outcome of this adjustment resulted in the following:
 
 =COUNTIFS('Kickstarter Data'!$D$2:$D$4115,">=1000",'Kickstarter Data'!$D$2:$D$4115,"<=4999",'Kickstarter Data'!$F$2:$F$4115,"Successful",'Kickstarter Data'!$R$2:$R$4115,"plays")

The above formula was duplicated and updated to reflect the ranges respective to column A, this process repeated through till B12. Only reverting to the initial formula (found in B2 - also found in line 29) for B13.  
The initial formula being updated to refect the "range" listed in A13, i.e. Greater than 50000 - formula listed below:

=COUNTIFS('Kickstarter Data'!$D$2:$D$4115,">=50000",'Kickstarter Data'!$F$2:$F$4115,"Successful",'Kickstarter Data'!$R$2:$R$4115,"plays")

Copying cells B2 - B13 into Columns C & D, updating the formulas to reflect the respective column headers to "Failed" & "Canceled" where "Successful could be found previously - see lines 41,45 & 50

### Sum Formula & Percentages
Following this I used the SUM function to generate a "Total Projects" Column whose formula from Cell E2 is found: SUM(B2:D2)
I then duplicated the formula in the cells B3-b13

Calculating the Percentages: I generated the following formula for each of the columns as follows:
Successful =B2/$E2	
Failed =C2/$E2	
Canceled =D2/$E2

Duplicating these formulas for each respective column, F,G & H through cells 3 - 13.

### Line Chart Creation & Images
I then Generated a Pivot Line Chart Identifying the Percentage of Successful, Failed & Canceled Kickstarter campaigns when viewed by their Goal ranges listed in Coulmn A - the results of said chart can be found below:
[Outcomes_vs_Goals](https://github.com/Gkmb2390/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

### Conclusions for Outcome Based on Goals
 1) The highest rates of successful campaigns were operating on Goals of values equal to or less than $4999.    
 2) Second highest success rates were for those campaigns whose goals ranged between 35000 - 44999. 
    Personal Comment - I would have assumed that the rates for successful campaigns were more linear - i.e. more successful at lower goals and less successful for higher goals. 
 3) The highest failure rates were found amongst thouse campaigns whose goals ranged over 45000
 4) In consideration to the subcategory of plays - there were no "canceled" kickstarter campaigns. 


### Challenges and Difficulties Encountered
I encountered an issue with the countifs formula for the Outcomes based on Goals calculations - I found that my total # campaigns, respective to outcomes were not equal to the total in a pivot table I created to double check my work.  Ultimately, I discovered that some of my formulas required an additional "=" after the ">" for those values within ranges for the sheet.  

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
    1) The greatest number of successful campaigns were launched in May, June & July. 
    2) There was a signficant rise in failed campaigns in the Month of October campaigns
- What can you conclude about the Outcomes based on Goals?
     1) The highest rates of successful campaigns were operating on Goals of values equal to or less than $4999.    
     2) Second highest success rates were for those campaigns whose goals ranged between 35000 - 44999. Personal Comment - I would have assumed that the rates for successful campaigns were more linear - i.e. more successful at lower goals and less successful for higher goals. 
    3) The highest failure rates were found amongst thouse campaigns whose goals ranged over 45000
    4) In consideration to the subcategory of plays - there were no "canceled" kickstarter campaigns. 
- What are some limitations of this dataset?
    1) Generalizaion of play category & content.  Not all plays discuss similar topics so some content maybe more successful in their kickstarters than others.  
    2) The play writers/actors also can add additional subtext & subjective context for if a campaign was successful.  If a play was written by a famous muscian or play write; or stared a famous actor who might be able to draw noteriatey to the campaign to improve its chances of success.
- What are some other possible tables and/or graphs that we could create?
    1) We could creat a chart/table based on the number goals that were successful/failed and include the pledged contributions.  In doing so we would be able to more clearly tell what range of campaigns were successful/failed and by how much they exceeded or missed their goals.  
    2) We could also take a deeper dive into types of plays that were successful and some of the under tones that they encompassed (i.e. comedy, tragedy, sci-fi, musical, etc)
