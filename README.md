Project 1: Deliverable 3

# Kickstarting with Excel
 
## Overview of Project
 
This project represents the visualization and quantitative analysis of Kickstarter crowdfunding campaigns between the years 2009-2017, both successful and unsuccessful.  This analysis was conducted using Microsoft Excel and its various utilities, such as Pivot Tables and Pivot Charts.    
 
### Purpose
 
The purpose of this project is to assist a client, Louise, with better understanding the landscape of Kickstarter crowdfunding campaigns like the one which he launched to help fund the production of “Fever”, her upcoming theatrical play.  By analyzing a corpus of data from previous Kickstarter campaigns, including many launched for the purpose of funding other such theatrical productions, latent trends can be revealed which will provide insight into key characteristics which have historically correlated with successful crowdfunding campaigns.
 
### Background
 
Louise is interested in the trends of campaign outcomes correlated with two variables: launch dates and fundraising goals.  The campaign for “Fever” completed without meeting the fundraising goal, despite gaining traction quickly and approaching it, so presumably Louise will use the information provided by this analysis to either relaunch the campaign or design a future one with better prospects of success.
 
## Analysis and Challenges
 
The analysis of the dataset in question consisted of two major stages.  First; the dataset itself was formatted, filtered, and expanded using various formulae.  Because the client is interested in trends specifically regarding theatrical productions, a column was created within the dataset so that it could be filtered not just by "Category and Subcategory" as originally possible but more granularly by both "Parent Category" and "Subcategory" separately.  This allowed the data to be filtered for campaigns classified as "theater" generally and "plays" specifically, yielding a more relevant subset for analysis.  Another two new columns were created using the Unix datetime conversion formula to convert the provided Unix datetime code for each campaign's launch date and deadline into conventional month/day/year format for easier reference.  Certain specific dimensions of the modified dataset were then converted into tables which were used to generate visualizations, which were analyzed to observe latent trends in the data.  These analyses are summarized below.
 
### Analysis of Outcomes Based on Launch Date
 
Using the modifications made to the original dataset as described above, a Pivot Table was generated displaying the total count of every successful, failed, and canceled campaign indexed by outcome and the month of the year during which they were launched.  A grand total for each month was also included.  These results were then filtered to show only those data categorized as "theater" and a Pivot Chart line chart (see below) was generated from these results.

![Outcomes Based on Launch Date](https://github.com/AC-Melamed/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png)
 
From this chart a trend is visible whereby campaigns launched between the months of April and May are significantly more likely to succeed than those prior, and those launched during subsequent months decreasingly so.  The number of failed campaigns each month total less than the number of successful ones throughout the entire year while generally mirroring the trendline of the successful outcomes.  Meanwhile, the number of canceled campaigns trends very consistently throughout the year with no obvious seasonal impact.  
 
### Analysis of Outcomes Based on Goals
 
A second second Pivot Chart was generated using a new table populated by the percentages of successful, failed, and canceled campaigns classified under the Subcategory of "play" sorted by ranges of fundraising goal.  These ranges were divided in increments of $5000, from $1000 and less to $50000 and more.  From this new table, a Pivot Chart line chart (see below) was generated.  

![Outcomes Based on Goals](https://github.com/AC-Melamed/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png)
 
From this chart it is evident that campaigns with lower fundraising goals are more likely to succeed than those with higher goals, with some variation.  The first point at which a campaign becomes more likely to fail than succeed is the $15000-19999 mark, after which the probability briefly inverts again between the $30000-34999 and $35000-39999 marks before reverting again approximately around the $40000-44999 mark after which the probability of a successful outcome becomes dramatically decreased and an unsuccessful outcome dramatically increased.    
 
### Challenges and Difficulties Encountered
 
No significant challenges were encountered over the course of producing this project, aside from various technical and formatting issues in the Excel environment.  During the population of the "Outcomes Based on Launch Date" Pivot Table, a single datapoint was imported from the original dataset as an empty value which disrupted the table.  This datapoint was eventually isolated within the original dataset and deemed valid despite the error, so with no clear method of resolving it, the empty value in the table was manually removed.  It is not expected that this omission had a significant effect on the visualization produced nor the analysis thereof.  One other small difficulty encountered was the question of how to consider the category of campaigns classified as "Live" meaning they were ongoing at the time the data was gathered and as such cannot be considered either "Successful" nor "Failed" or "Canceled".  It was not expected that this category represented a large enough portion of the dataset to skew the visualizations produced for this analysis significantly, as confirmed by some brief experimentation with including them alongside the other outcomes, so they have been omitted.  What's more, even if they had been included in the visualizations, since their ultimate success or failure (in addition to other values regarding funding percentage, etc.) are categorically unknown, their inclusion would do little to inform the particular analyses of this project regardless.    
 
## Results
 
- What are two conclusions you can draw about the Outcomes based on Launch Date?
 
One conclusion that can be reached from analyzing the "Outcomes Based on Launch Date" data and visualization is that theatrical productions pursuing crowdfunding saw significantly increased success compared to the relative rate of failure when launched around the months of May through August.  This indicates that the Summer season represents the ideal time for such campaigns to begin soliciting funding, with diminishing effect over the course of the season.
 
Another conclusion that can be drawn is that, unlike the rate of failures and successes, the rate of canceled campaigns does not appear to be influenced at all by the seasons.  Therefore, any concerns regarding potential factors which might result in a campaign cancellation should be directed towards the investigation of other variables besides seasonality.    
 
- What can you conclude about the Outcomes based on Goals?
 
The primary conclusion reached from analyzing the "Outcomes Based on Goals” data and visualization is that the range of $15000-19999 marks the first point at which the fundraising goal of a Kickstarter theatrical play production becomes correlated with a greater chance of failure than success.  Additional conclusions can be drawn regarding higher fundraising goals, such as the $40000-44999 range at which point the percentage of successful campaigns drops most precipitously, but this primary conclusion remains the most significant for the purpose of this project.  
 
- What are some limitations of this dataset?
 
The dataset at hand is largely adequate for the particular modes of analysis performed by this project, but some limitations are apparent.  For instance-- the individual campaigns contained as datapoints therein are primarily indexable by quantitative dimensions such as launch dates and fundraising goals, with the sole exceptions being the categories/subcategories and outcomes classifications.  These data are useful for describing many trends but are not the only aspects with potential explanatory power.  Additional qualitative information such as that provided in the "Blurb" and "Title" columns for each campaign are included but non-indexable and thus provide very limited utility for analysis within Excel.  The application of a machine learning model for word frequency or other more complex semantic analysis could potentially take advantage of these data.  Harder limitations also exist, such as the limited date range from which the campaigns were sampled which ends at 2017, and the lack of any data identifying the original creators for each campaign who could potentially constitute a common variable between multiple data points if they have launched multiple campaigns.    
 
- What are some other possible tables and/or graphs that we could create?

Aside from the two tables and accompanying visualizations produced for this project, some other potential options might be considered for further analysis.  A box-and-whisker plot, for instance, displaying the statistical distribution of a quantitative value such as the number of backers or the fundraising goals would provide insight into the overall landscape of the dataset in a direct way.  Other, discrete factors such as the "Staff Pick'' boolean or the "Country" categories could provide additional dimensions within stacked line plots correlating quantitative dimensions and potentially reveal otherwise hidden influences on those trends.  

