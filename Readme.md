# Kickstarting with Excel

## Overview of Project
The fundraising goal for Louise's play “Fever” was almost reached within a short time frame. In order to determine how effective each campaign was, she has to know when they launched and how much they raised. To better understand the trend, the number and percentage of successful, failed, and cancel plays were visualized as functions of launched date and the pledged, respectively.   

### Purpose
To provide Louise with a better inside to reach her fundraising goal for her play using an available database on previous successful, failed, and canceled cases within 2009-2017.  

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
  The first step is converting Unix timestamps of launched date into a day-month-year format using (((J2/60)/60)/24)+DATE(1970,1,1). It should be noted that the type of obtained data should be changed from “General” to “short date” format. Next step is obtaining the month in three letter format using TEXT(P2,"mmm") and extracting year using Year(P2). After that we need to separate category and subcategory via using convert text to Colum wizard, then choosing delimited and finally put “/” as the delimiters. Now we have all we need to insert pivot table. The results indicated that the numbers of successful and failed campaigned followed a similar pattern except in December. While cancel cases almost remained constant within this timeframe. Also, The results indicated that the number of saucerful cases in all months were greater than cancel ones. However, I believe plotting the percentage of successful, failed, and canceled cases would give a better insight about the rate of success per month.

### Analysis of Outcomes Based on Goals
To properly extract the desire data it is important to use a proper constrain for each category. For example for goals less than $1000 we simply use =COUNTIFS(Kickstarter!$D:$D,"<1000"), while for 1000<=goals<5000 we need to include tow contains as bellow: COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<5000"). Noteworthy, the number of successful or failed cases in each category should be divided to total project in each category rather than total project for all category to obtain rate of success and failure. The graph shows that the rate of success and failure highly depends on the fundraising goal such that increase in the goal will reduce the chance of success. However, there is an exception within the range of $35000-$45000. Additionally, I believe plotting data in line graph is not a good idea because it may mislead the audience. Illustrating data with stacked column or bar chart will give a better understanding of the trend.  
### Challenges and Difficulties Encountered
My main challenge was determining proper graph type. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
1. There is a higher chance to get a successful campaign if the launche date is set to be on May.
2. It is less likely to achieve fundraising goal on December
- What can you conclude about the Outcomes based on Goals?
1. The campaigns that aimed to raise less than $20,000 or $35000-$45000 were more likely to achieve their goals.
- What are some limitations of this dataset?
This data set lacks the information related to the genre, and thus statistics of each genre

- What are some other possible tables and/or graphs that we could create?
1. Adding country to the filter to have outcome based on launched date for each country.
2. Rate of success or fail in each of category and subcategory.
3. The amount of pledge for each category, subcategory, and country.
4. Outcomes based on Goals for each country.
5. Number of a specific category such as film&video or subcategory such as television are being launched in different months.
 
