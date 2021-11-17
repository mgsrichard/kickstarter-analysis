# Kickstarting with Excel

## Overview of Project

Louise has requested that we provide her with some additional data from our Kickstarter analysis.  She is interested in finding out how different campaigns turned out based on their launch dates and their funding goals. 

### Purpose
The purpose of the challenge is to analyze the data, zeroing in on plays only, to find out what the experience of the campaigns was in relation to the month of the year in which they launched and also in relation to the size of the original goal.  We seek to understand if some months are more successful for launch, and if a particular value range of goals are more successful than others. We will provide results through charts and written analysis.

## Analysis and Challenges
To find these answers, I started in Excel.  First I added a column for year in the original Kickstarter data tab, using the Excel function YEAR() and referencing the date created which was in column S in my worksheet. Then I created a pivot table based on the data.  Pivot tables are a little challenging for me, but I am starting to get a good feel for how they work and what happens when you move different fields into the filter, row, column, and value boxes.  Here's how my pivot table looked:

insert pivot table image

My pivot table came out correct, and then I created the line graph from the data.  I clicked around inside Excel until I found the spot to remove the filter drop down boxes from the graph for a more professional finished look, as in the example in the directions for the challenge.  I saved my line graph image as "Outcomes Based on Dates" and moved on to the next question. 

For the next part, I set up a new sheet in my Excel workbook and called it "Outcomes Based on Goals."  I entered the column and row labels and started to program the counts in the first three columns using the COUNTIF() function.  I was already familiar with the function COUNTIF() (no S) and so I started with that, but then realized that COUNTIF() would only look at a single criteria and I needed to look at 3 or 4.  I briefly considered nesting IF() and AND() statements before I realized that it  said COUNTIFS() (with an S).  So then I learned about COUNTIFS() and was able to program my cells with it.  The first and last rows had three criteria, one for which outcome, a single criteria for value, and one for subcategory, which is plays for all the counting formulas. The in between rows had 4 criteria, one for outcome, one for lower range value, one for upper range value, and one for subcategory.   I was careful about using >,<, >= and <= to be sure that all values would be included, and that I wasn't leaving out the value right at the boundary between the value ranges in the rows. The formula I programmed for successful plays with a goal of less than 1,000 is:

=COUNTIFS(Kickstarter!F:F, "successful",Kickstarter!D:D,"<1000",Kickstarter!R:R,"plays")

The formula I programmed for failed plays with a goal of 1000 to 4999 is:

=COUNTIFS(Kickstarter!F:F,"failed",Kickstarter!D:D,">=1000",Kickstarter!D:D,"<=4999",Kickstarter!R:R,"plays")

I then found the total number of projects using the SUM() function, and found the percent of successful, failed, and canceled projects for each value range, dividing the individual counts by the total counts and rounding to 2 decimal places with ROUND() for clean looking percentages.  For example, for the percentage of successful plays, in the first value range, my formula is =ROUND(B2/E2,2). Next, since we didn't have a table in the directions to compare our numbers to, I decided I wanted to check my work a little. I created a new little pivot table that summed up the counts of failed, successful, and canceled projects and filtered it to just plays.  My total counts matched up, so I felt more confident. I also thought it was worth checking that there were zero canceled plays, so I went back to the original kickstarter data page and filetered by canceled plays to verify that zero was correct. I also could see in the example graph from the challenge directions that the line for canceled plays seemed to be right along the x axis (it's grey though, so it's hard to tell if there is a line there or if it's just the axis itself), so that all seemed to fit and be correct.  Here's an image of my outcome by goal spreadsheet, and below it an image of my checking pivot table:

insert outcome by goal spreadsheet
insert check pivot table

Finally, I created my line graph.  I stretched it out until the proportions looked good and put a title on it.  I saved it as "Outcomes Based on Goal."

### Analysis of Outcomes Based on Launch Date

Below we can see the graph for outcomes based on launch date.  One conclusion to be drawn from this graph is that, broadly speaking, theater kickstarters are more likely to succeed than to fail.  The successful graph line is consistently above the failed line through all months.  For example, in March, 56 succeeded and 33 failed.  A second conclusion is that the best time to launch a campaign is in the months of May, June, and July, and May seems to be the absolute best time for a campaign, with 111 successes versus 52 failures.  Thirdly, October, November, December, and January are the least desirable months to launch, with fewer launches and a lower rate of successes.  


### Analysis of Outcomes Based on Goals

In the graph below we are graphing outcomes versus the amount of the original goal.  Generally, campaigns with smaller goals are more likely to be successful.  Even though the graph shows a higher percentage of successes than failures for the ranges between $35,000 and $45,000,  I would caution that the majority of the data analyzed falls into the smaller categories, and the ones in the $35,000 to $45,000 range make up only 9 of 1,047 launches considered. Additionally, 85% of the campaigns we analyzed had a goal of $10,000 or less, which leads to the conclusion that most campaigns, successful or not, have goals of $10,000 or less. In short, the lower the goal, the more likely the campaign is to succeed.

### Challenges and Difficulties Encountered

My main challenges in this assignment were to become comfortable with how pivot tables work, and also to familiarlize myself with the function COUNTIFS().  On the Git side, I have been challenged to learn about how to upload and commit files, and how to edit and insert links and images with Markdown.

## Results

In conclusion, theater Kickstarters are more likely to succeed than fail, and May-July is the optimal window for launching. Most campaigns have goals of $10,000 or less, and the lower your goal, the higher your chances are of achieving your fundraising goal.

The limitations I can see to this dataset are that it is drawn from only one crowdsourcing site, and that it mixes currencies.  Kickstarter is one of many crowsourcing sites, and it's possible that there are biases about who chooses which sites for which projects.  Are theater campaigns more or less likely to be launched here, and more or less likely to be viewed by the theater community and its supporters? I don't know.  There could be many unknown factors in the selection of the crowdsourcing site.  Secondly, we have considered money amounts from around the world without doing any currency conversions, so it's possible that we are not always comparing apples to apples in the data.  Does an Australian dollar have the same feel, the same buying power, as a US dollar or a British pound?  As far as I can tell we don't have data from Japan or India where the basic unit of currency is more comparable to our cents than our dollars, so it seems that at least we are not off in scale.  


There are other analyses/tables we could look at.  For example, have theses trends changed over the years as more fundraising has moved online? It might be interesting to compare on a yearly basis.  Also, we could look at the duration of the campaigns.  Is it possible that having a couple more weeks makes it more likely for the campaign to be successful?  Another possibility is that we could also do an analysis of size of individual donations, and figure out whether campaigns are more likely to be successful with many small donations or if having one or two large donations makes reaching the goal more likely.  


- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
