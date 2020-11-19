# Data Visualization Project: "Ford GoBike" Bicycle-Sharing
## by Karine Legrand
## from the "Data Analyst Nanodegree Program" - Udacity Certificate

### This Project focused on the fundamental Topic of Data Visualization and mastering techniques, for both gaining a deep Understanding of the Data, in the <i>Exploratory Analysis</i>,  as well as to produce polished plots for communicating the findings in the <i>Explanatory Analysis</i>.
### We chose to investigate the data from an american Bike Rentals Company, "Bay Wheels" (former "Ford Go Bike") and provide an Analysis, based on each rentals' characteristics, finally conveying our main findings and "tell a story" about the data, by choosing a path of questions and answering them.

#### <ins>Learning goals</ins>:
* Supplement statistics with visualizations to build understanding of data (extensive use of the python <i>matplotlib</i> and <i>seaborn</i> libraries)
* Choose appropriate plots, limits, transformations, and aesthetics to explore a dataset, allowing us to understand distributions of variables and relationships between features. Thereby, we build a progressive Analysis, first depicting a single variable (<i>univariate exploration</i>), then two variables (<i>bivariate exploration</i>) and finally produce more complex plots with three or more variables (<i>multivariate exploration</i>)
* Use design principles to create effective visualizations for communicating findings to an audience. Choose a path within these findings, to "tell a story" that can be easily followed and understood by this audience (not necessarily familiar with statistics)

#### <ins>Provided Files</ins>:

* The "Exploratory Analysis" Part of the Project is contained in the python jupyter notebook ```exploration_fordgobike.ipynb```,
that can be viewed with "nbviewer" (Table of Content and anchor links are not rendered within GitHub) here:<br>
https://nbviewer.jupyter.org/github/rinkalaone/visualize-data_udacity-project5/blob/master/exploration_fordgobike.ipynb

* The "Explanatory Analysis" has been built using the jupyter notebook ```fordgobike_slide_presentation.ipynb```.
A Slides-Presentation was generated using the module "reveal.js" on the command line:<br>``` jupyter nbconvert fordgobike_slide_presentation.ipynb --to slides --post serve --template output_toggle```<br><br>
The Presentation can be viewed and navigated through, by clicking or pressing the arrow keys, here:  
https://rinkalaone.github.io/presentation-slides_udacity-project5/
<br><i>(How to navigate: if sub-slides follow the current slide (the down arrow at the bottom right is black colored), click the down-arrow. Otherwise click the right-arrow or press the right-key)</i>

* The review from a Udacity mentor, is included in _"ProjectReview.pdf"_, validating that the project passed successfully for certification

----


## Detailed overview of the Dataset, Exploratory Analysis, Summary of Findings and Key Insights for our Explanatory Analysis:

## Dataset

The dataset we imported, cleaned and conducted our Analysis on, contains more than 1,7 millions (1753003) observations of bike rentals in the area of Greater San Fransisco for the whole year of 2018. There are 16 characteristics describing each ride, such as duration, start and end timestamps, pick-up/drop-off points and informations about the user such as gender, year of birth and registration mode.
The data can be found on the website of the "Bay Wheels" company, [here](https://s3.amazonaws.com/baywheels-data/)


## Summary of Findings

We focused our Analysis on the features of "duration" and "pick-up time" through different perspectives (by months of the year, days within a week and hours within a day), to inspect how they possibly correlate with one another on one hand and with other features of the dataset on the other hand. We gathered different findings through our different phases of Exploratory Analysis that we expose here:

#### <ins>Univariate Exploration</ins>

The "duration" variable takes a wide range of values (between 1 minute to more than 23 hours), with most values in the lower part of the distribution (99% of the rides last less than 1 hour and 40 minutes) and a frequency peak for duration values between 5 and 10 minutes. A logarithmic scale transformation on the x-axis, reveals a "log-normal" shape of the distribution.

The distribution of rentals *per month* reveals a seasonal variation with the highest number of rentals during summer and the least during winter, as we would intuitionally expect. More surprisingly, we notice a quite constant use of the rentals on *working days*, but a drop on the *week-end*. Enforcing this tendency, the daily distribution of rentals per *pick-up hour* reveals a bimodal shape with two peaks around 8am and 5pm: i.e. a heavy use at opening and closing office hours.    

Beyond our main features of interest, we inspected the categorical variables describing the users and could discern the following user's profile summary:
- In terms of gender, the population is composed by 73.5% of "male", 25% of "female" and 1.5% of "other" users
- Most of the users are between 20 and 60 years old. The "age" distribution is approximately right skewed with a peak between 25 and 35 years
- A large majority of users are "Subscribers" (88.5%), versus "Customers" (11.5%)
- 10.5% of "Subscribers" make use of the "bike-share" Program

#### <ins>Bivariate Exploration:</ins><br>

The "duration" variable seems to be influenced by all the users' characteristics we have been looking at (gender, age, user-type):<br>
- "user-type" shows the strongest correlation with  "duration":  
In average, "Customers" tend to use rentals for a significant longer time than "Subscribers" (14 minutes vs. 8 minutes)
- When looking at the differences between gender groups, it seems that "male" users pick-up rentals for slightly shorter trips
- Users in their 20's, 50's and 60's, tend to pick-up rentals for a slightly longer time than users of other age categories

The "pick-up time" variables are influenced by users' characteristics in the following way:
- There are less men, in proportion, using rentals during summer and also during the week-end, than the 2 other gender groups
- Looking at the differences across age categories, we found out following tendencies:
    1. The older the users, the more rentals are used, in proportion, from January until May
    2. During the month of June the use of rentals across all age categories is uniform, in proportion
    3. The younger the users, the more rentals are used, from July until October
    4. The youngest and oldest users, pick-up more rentals in proportion, during the week-end than users of other age categories
- Looking at the user-type variable, we notice following tendencies:
    1. There are more Customers using rentals, in proportion, from May to September<br>
    2. There are more Subscribers using rentals, from October until March<br>
    3. There is the same proportion of both user-types during April.<br>
    4. Customers use more rentals during the week-end than during the working days, as opposed to Subscribers<br>
    5. Customers use more rentals during the week-end, in proportion, than Subscribers<br>
    6. Customers use more rentals, between 10am and 6pm, in proportion, than Subscribers

Finally, the duration vary with the "pick-up time" in the following way:
- Trips duration tend to be slightly longer during the months from June until October
- During the week, from Monday until Thursday, the duration of the trips tend to be minimum in average. It increases, slightly on Fridays and is maximum during the week-end
- During the day, the duration time is maximum in average at 8am and between 11am and 6pm.

#### <ins>Multivariate Exploration:</ins>

We found out that the "user-type" variable, which we knew had an influence on both "duration" and "pick-up time" variables, is a feature that actually explains more precisely, how the median duration vary with times of pick-up:<br>Trips duration do not vary much by time of pick-up for the "Subscribers" group. It remains either constant by month of the year and for each day of the week (8 minutes) or shows few variation by pick-up hour, during the day (6 to 9 minutes).
There is a bigger variation of the median "duration" within the group of "Customer" users: 1) during the week-end rentals last about 18 minutes, versus 13 minutes during working days and 2) during the day, they last 17 minutes from 11am to 3pm versus around 12 minutes. The biggest variation of the trips' duration observed, for the "Customers", occurs in the measurement by days of the week and hour of the day. The duration time shows less fluctuation, when looking at the median variation by month (between 13 and 15 minutes).

We observed that 'gender' somewhat emphasized the effect of the user-type variable on the "duration" and "pick-up" time variables. Both the "duration" by "pick-up" times and the proportions of rentals by time show a tendency of a bigger contrast of values within the group of "Customer" users, for the "Female" group.

#### <ins>Analyzing the Findings and overall Conclusion:</ins>
Focusing on the analysis of the "duration" and "pick-up time" variables of the dataset, helped us gain Insights on *how* and *what* the Rentals are used *for* and by *whom*.

The main reason, by far, why people use the rentals service of the "Bay Wheels" Company, is for daily commuting purposes, all year long, mainly on working days and opening/closing office hours. The trips median duration remains quite constant, around 8 minutes. The users, most probably residents of the bay, are subscribers of the service.

Another way of using the rentals, in a much smaller proportion, appears to be for recreational or touristic purposes, all year long and for a much longer time in average. The users, probably tourists or visitors are customers of the service.

## Key Insights for Presentation
(Exposes a Path of choice for conveying the findings we made and "tell a story")

We want to answer the following questions:

- "Who uses the rentals service?"
- "When are the bikes used?"
- "How long are the trips?"

We saw that we must combine the different questions together to get a full answer to each of them. So answering the distinct 3 questions will eventually turn into answering "Who uses the rentals service, when and for how long?".

We will start answering the 3 questions, distinctively. First plotting all users features distributions, frequencies by time of pick-up and trips duration.  
We will then move on answering "Who uses rentals when", focusing on plotting frequencies for several user features by week and by day. And combining different user features.  
We will next answer "Who uses rentals for how long", plotting an overview of the duration distribution for user characteristics with boxplots and then plotting the median duration for the same features.
Finally we will answer "who uses rentals,  when and for how long", focusing on the median duration by times of pick-up, for the "user-type" feature.

## Feedback on Plot Design

Using Feedback from Family members, that are unfamiliar with statistics and boxplots in particular, we decided to remove outliers from the boxplots and add horizontal lines to highlight the highest median value in each boxplot.

## Resources

We used following websites, apart from the Udacity courses content, for python programming references and for solving encountered issues with the used libraries(pandas, numpy, seaborn and matplotlibb):  
- pandas.pydata.org  
- www.stackoverflow.com  
- matplotlib.org  
- stackabuse.com  
- kaggle.com  
- https://seaborn.pydata.org/  
- https://medium.com/analytics-vidhya/the-ultimate-markdown-guide-for-jupyter-notebook-d5e5abf728fd  

and following books:  
-  "Learning IPython for Interactive Computing and Data Visualization Second Edition" by Cyrille Rossant  
- "Python for Data Analysis" by Wes McKinney  
- "Interactive Data Visualization with Python" by „Abha Belorkar, Sharath Chandra Guntuku, Shubhangi Hora, and Anshu Kumar“  
- "Pandas for Everyone" by Daniel Y. Chen.  
