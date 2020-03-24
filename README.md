# Analyzing Factors Impacting Incidence of Malaria Cases

With the coronavirus gaining a lot of attention in the media, people are beginning to worry about their safety and likelihood of surviving this growing pandemic. The likelihood of falling victim to diseases can be exacerbated by additional confounding social factors such as GDP, quality of roads, and access to doctors, water, and sanitation. To figure out what variables may have the biggest impact on people's susceptibilty to coronavirus, we decided to investigate how such factors impact malaria cases, and hope to extrapolate the results to the current coronavirus pandemic. 

## What Social Factors Impact Coronavirus?

On March 11 the [WHO declared the coronavirus outbreak a pandemic](https://www.who.int/dg/speeches/detail/who-director-general-s-opening-remarks-at-the-media-briefing-on-covid-19---11-march-2020), at which time there were 118,000 cases in 114 countries. The numbers continue to grow everyday, and no vaccine or cure has yet been found. People are growing increasingly worried about their health and the health of loved ones, and want to know what the chances are of contracting the disease, and if anything can be done to decrease those chances. Likewise, governments are making efforts at the systemic level to decrease the number of cases and fatalities resulting from this disease, as the growing number of cases creates a large burden on health systems. For example, [doctors are being sent into Italy from Cuba](https://www.reuters.com/article/us-health-coronavirus-cuba/cuban-doctors-head-to-italy-battle-coronavirus-idUSKBN219051) to provide more healthcare workers to accomodate the large influx of patients being seen by hospitals. 
In attempts to gain more insights into how to handle such a global disaster, people are looking to the paths past pandemics have taken, and are trying to extrpolate what those results could mean for today's circumstances. For example, [similarities are being drawn between the Great Influenza Pandemic of 1918 and COVID-19](https://www.weforum.org/agenda/2020/03/coronavirus-great-influenza-pandemic-covid19-prepared-outbreak/). In an effort to perform a similar analysis, social factors imapcting malaria incidence will be analyzed to hopefully provide som insight into what is important and what can be done when addressing the current crisis. 

## What Variables Strongly Impact the Number of Malaria Cases Across Countries?

To discover trends in variables affecting incidence of malaria cases, data sets from [Gapminder](https://www.gapminder.org/data/) were dwonloaded and analyzed first in Excel, and then in python using potly express. The largest possible data set over the longest period of tie would be ideal to better show real trends. However, data from the years 2000-2006 were used, as data for years outside of that range was not reliably recorded across the majority of counties. 

The following steps were used for analysis:
1. Data sets for all of the following social factors by country and year were dowloaded
  * Malaris Cases
  * Malaria Deaths
  * GDP
  * Access to a Water Source
  * Access to Basic Sanitation
  * Percent of roads that are paved
  * Medical Doctors per 1000 people
  * Number of Cars/Buses/Trucks 
2. Since data was not available in each of these categories for every country, preliminary selection for variables to be analyzed were selected. Cambodia had the most reliable data across all of the categories for the longest period of time, so the data was compiled into a single [Excel document](https://github.com/karinafrank/analyzing-factors-impacting-number-of-malaria-cases/blob/master/Regression%20Analysis.xlsx?raw=true) using VLOOKUP for Cambodia from years 2000-2006.
3. A multiple regression analysis was then conducted to provide which variables had the strongest predictive influence on the number of malaria cases the country experienced and to show how much changing one variable would affect the other. 
  * The Data Analysis plugin under the Data tab was used. 
  * The regression tool was selected. The Input Y range was specified as the Malaria cases column, as we want to examine how other variables result in changes in malaria cases. The Input X range was specified as the columns containing all of the other varibales we wanted to analyze. 
  * Labels for the data set were inlcuded and therefore checked off in the dialogue box.
  * The results were output into a separate worksheet, inlcuding the calculation of residuals.
4. The coefficients were analyzed to see which strongly predicted large changes in malaria cases. Overall access to basic sanitation and GDP were selected as the variables to analyze.

|	Coefficients|	Standard Error	|t Stat	|P-value	|Lower 95%	|Upper 95%	|Lower 95.0%	|Upper 95.0%|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Intercept|	38212.29474	|87088.97597	|0.43877304	|0.736771436|	-1068358.064|1144782.654	|-1068358.064	|1144782.654
|Water_Overall|	0	|0|	65535	|#NUM!|	0	|0|	0|	0|
|Water_Rural|	-5480	|2514.879719|	-2.179030655	|#NUM!|	-37434.57659|	26474.57659|	-37434.57659	|26474.57659|
|Water_Urban	1610.473684	|1233.72133	|1.305378812	|0.416159144	|-14065.44213|	17286.3895	|-14065.44213|	17286.3895|
|Sanitation_Overall	|9170.473684	|9485.823378	|0.966755686|	0.510759838	|-111358.3403|	129699.2876|	-111358.3403	|129699.2876|
|Sanitation_Rural|	-7400|	9033.714629|	-0.819153616|	0.563080625|	-122184.2276	|107384.2276	|-122184.2276|	107384.2276|
|Sanitation_Urban	|346	1702.082254|	0.203280423|	0.872327297	|-21281.0056|	21973.0056	|-21281.0056	|21973.0056|
|GDP|	-0.073950557	|0.160875577	|-0.459675474|	0.665044657	|-0.487494394|	0.33959328|	-0.487494394	|0.33959328|


5. Graphs showing the trendline equation and R^2 values for these variables were created in Excel.

![alt text](https://github.com/karinafrank/analyzing-factors-impacting-number-of-malaria-cases/blob/master/Malaria%20Cases%20v.%20GDP%20in%20Cambodia.JPG?raw=true)

![alt text](https://github.com/karinafrank/analyzing-factors-impacting-number-of-malaria-cases/blob/master/Malaria%20Cases%20v.%20Overall%20Sanitation%20in%20Cambodia.JPG?raw=true)

6. __Input python analysis steps __


*Instructions for this section:
What kind of data was important to use to answer this question, how did you find it, and why did you use this information? Was there some data that you wish you had? If so, how would you change your approach?
What metrics did you think were important to understanding a quantitative answer to your original question and why? Did you “translate” any of your data into numbers?
Did you base your data analysis on another type of analysis or desired outcome?
Use website links to your data sources, for example, if you used data from Baltimore City Open Data, add a link for the reader to learn more*

## Malaria Cases are Related to Overall Country Sanitation and GDP


*Instructions for this section*
What were the results of your data analysis and how did this contribute to your final solution?
What type of visualizations can best demonstrate what you found and what you think is important to emphasize to your audience?
Keep your data visualizations and tables in here for people to follow along with your analysis and explore how your data findings are relevant. For example, if you analyzed Baltimore Police Department Salary Data, add in a graph here to emphasize the trends in number of Police Officers and overtime earnings in fiscal years 2014-2018: Alt text


## Countries Must Reach a Critical Point in Reuction of Cases to Maintain Low Incidence

The results from the python analysis show an interesting trend. The longitudinal data for all the countries was not available over a long period of time, but instead of looking at changes over time, insight can be gained from looking at the general trends of countries' standing in the graphs generated. It appears that countries which are able to get below a certain point in malaria incidence rate are able to maintain that low incidence rate across GDP and sanitation levels. **insert some examples from the actual graph**

These results seem to align with many of the public health guidance being released at the moment relating to COVID-19. In one [Vox article](https://www.vox.com/2020/3/10/21171481/coronavirus-us-cases-quarantine-cancellation), it is discussed how there is a limit to the capacity healthcare systems can handle. In the wake of major outbreaks, healthcare systems' abilities to handle and contain the disease cases is severely strained, making the overall system less effective. However, as supported by the results generated by our analysis, as long as healthcare systems are able to get the number of disease cases below a certain point, where the burden on systems becomes managable by the resourses available, it seems that system is able to maintain and function well at that managble leevel of disease burden. 

*Intructions for this section:*
- What’s the answer to your original question? Were you able to come to any type of conclusive answer—why or why not?
- How would you build on your analysis if given more time?
- What do these answers mean for us in the real world?
- What do these answers mean for the audience in this industry?



