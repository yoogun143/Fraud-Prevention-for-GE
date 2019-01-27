# Fraud-Prevention-for-GE
R Shiny app:
https://yoogun143.shinyapps.io/GE-Fraud-Prevention/

## 1. Introduction
General Electric (GE) is an American multinational conglomerate incorporated in New York and headquartered in Boston, Massachusetts. As of 2016, the company operates through the following segments: aviation, current, digital, energy connections, global research, healthcare, lighting, oil and gas, power, renewable energy, transportation, and capital which cater to the needs of financial services, medical devices, life sciences, pharmaceutical, automotive, software development and engineering industries. 

In 2017, GE ranked among the Fortune 500 as the thirteenth-largest firm in the U.S. by gross revenue,. In 2011, GE ranked as the 14th most profitable. As of 2012, the company was listed the fourth-largest in the world among the Forbes Global 2000, further metrics being taken into account.

The main purpose of this paper is to provide a tool for Quality Assurance of GE to detect any suspicious behaviors flagged by the internal system. The business intelligence tools used here are Tableau and R Shiny, which are helpful to analyst to analyze the structured data and deliver an engaging dashboard for audience. For the overview dashboard, 4 business questions will be addressed accordingly through the filters on the left panel. Following on from that, any further investigation for each graph will be examined through the specific dashboard. This dashboard will help audience to break down the dilemma into smaller parts by using top-down approach, starting with Business, then GUID and finish with description of violation.

## 2. Business Questions
In order to tackle some of the challenges GE may confront when detecting fraud and unusual activities, some business questions have been raised by our teams. There will be 5 questions in total classified into 2 categories which are spatial and time series analysis.

Time series analysis:
-	Number of records by months of years.
-	Number of records by days of months.
-	Number of records by days in a year.
Spatial analysis?
-	Number of records by country.
-	Number of records in United States.

Although the answers to those questions are not represented in the dashboard because of the limitation in space allowed and for the comfort of audience when using dashboard, they will be explained comprehensively in this report.
	
  Those business questions will enable firm owners or board of directors to make a wise decision on Quality Assurance by performing a comprehensive regular check on specific months or days in the month as there is a high possibility of occurrences in the past. For the spatial analysis, the authority can have an overview of the heat distribution all over the world and in each state of US explicitly. Those graphs can be extremely helpful to prevent the fraud worldwide especially when GE functions in global world. Likewise, the questions about the pattern in the department allows GE to concentrate on the department with unusual activities.

## 3. Research Method
For the Heat table, we search for unique values of Indicator_Actual_Possible and there are 68 of them. After that, we compare those values with the match values in Indication_Name of “Sanitized Indicator Types” table. It turns out that there are some mismatches because there is not a consistency in the name written. For example, one use “space” for separator while the other use “_”. The full list of names altered provided in the appendix.

For cleaning the location, we find all unique values of Location and then manually breakdown the location into city, state and country. The full list of breakdown is provided in appendix.

We have collated 4 graphs in our dashboard. The various types of graphs we have utilized in our dashboard include “discrete line graph” for visualizing the months in a year, events are irregularly occurring on (violations are referred to as “events” in this context). Different color lines have been used to represent each class of violation, and they are segregated in terms of “Months”. On the second graph, we have designed a “Area graph” in order to drill down and further interpret the data by visualizing the days, wherein events are bizarrely registered. 

Furthermore, we have made use of a geographical map to visualize and comprehend the countries, wherein users violate the most (“dark green” through “dark red”), with “dark red” representing intense violations, and “dark green” representing less violations. First of all, we had converted the “identities” text file into an excel file and further found the “unique values” for each location, and filled the corresponding city, state and country. This is auto detected as “geographic” data type in Tableau. The dashboard further drills down to United States alone for representing the number of users who make violations in each and every state, in a similar fashion as the previous graph. 

For the R Shiny, we build a dashboard to detect the pattern of violation through days in a year. There is an option for audience to click and drag the mouse over the line graph to zoom in a specific date range. The initial line graph will be broken down into four segments of Class for further investigation. Finally, the data table will extract the data from the date range chosen and the number of observations as well as the percentage will be shown. The variables for classification will be chosen by users, whether it is GUID, Class or Business
