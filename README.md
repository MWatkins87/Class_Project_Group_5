# Class_Project_Group_5

- Class project for group 5 team members, Michael, Terry, and Matthew.

## Module 9 Project 1

- The team will work as a group to find and analyze a dataset of choice and work in the team repository created in Github
  https://github.com/MWatkins87/Class_Project_Group_5
- @MWatkins87's Group 5 Group Project has been created as a Kanban project in Github's Project section
  https://github.com/users/MWatkins87/projects/2/views/1

- Project 1 Overview and list of requirements can be found in the DU Bootcampspot.com website
  https://bootcampspot.instructure.com/courses/5432/pages/9-project-1-overview?module_item_id=1200592

---

### Executive Summary

---

**Introduction to the Analysis of Real Estate Price Trends**

Navigating the recent surge in housing prices represents one of the most significant challenges in the American real estate landscape. Conventional wisdom, supported by numerous studies, suggests that this increase is primarily driven by internal migration and a stagnant housing supply.

Contrary to expectations, regions experiencing population declines have not seen corresponding decreases in housing prices, suggesting that factors other than simple supply and demand dynamics are at play. This study aims to explore alternative factors that might be influencing these price trends.

Our analysis focuses on ten cities, chosen to represent both booming and sluggish housing markets based on recent performance metrics. The cities include Atlanta, Miami, Detroit, Tampa, and Las Vegas, which have shown strong market growth, and Baltimore, New Orleans, Washington D.C., San Francisco, and Portland, where the markets have been less robust.

We examined a range of data from 2012 to 2022 for these cities, considering variables such as population growth, homelessness, crime rates, college tuition costs, and mortgage rates. The objective is to identify both positive and negative correlations that could explain the divergent trends in housing prices across these different environments.

---

### Overview - Data Collection, Cleanup, and Exploration Processes

---

#### Project Dataset "house_values_zillow.csv" to Establish Housing Price Baseline

1.  First step is to pull data from Zillow and import the data from .csv file
    ---python

    $ house_values_df = pd.read_csv("house_values_zillow.csv")

2.  We then set variable values for "hv_filtered, States, Cities, Metro, Years"
3.  New Filtered DataFrames were created for the "States, Cities, Metro" data
4.  Metro data required filling and rounding the data to make it easier to read (.fillna, round)
5.  Column rename, for loop, and resetting the index to the renamed "years" column organized our filtered DataFrame
6.  Column(s) drop, Transpose, and conversion to DataFrame to prepare for plotting(.drop, .transpose, pd.DataFrame)
7.  Further DF cleanup with iloc to remove additional reference to 2nd Washington City column and for loop with .plot command to plot the median home prices n the target cities.
8.  Plot output for median house prices in the 10 target cities

#### mathew_watkins.ipynb

#### michael_sheridan.ipynb

#### terry_hood.ipynb

---

### Project Approach

---

Our project began with an intensive brainstorming session, wherein we delineated the project's objectives, delineated goals, and pinpointed key variables and social contexts likely to yield impactful datasets for comparison against our foundational dataset of median housing prices.

Slack communication Direct Message channel, Slack Huddle, Google Meets, Zoom, were all identified as team communication methodologies.

Task allocation was developed and populated in a Kanban style Project in Github Project, with team members assigned specific elements to navigate through the project's trajectory. Throughout the project lifecycle, we engaged in continuous comparison of dataset discoveries, collaborated to resolve coding intricacies, and conducted thorough reviews and evaluations of each other's work as part of a rigorous quality assurance process.

Collaboratively, we delved into the analysis of our findings, endeavoring to discern their implications and uncover correlations of significance.

---

### Dataset(s)

---

#### Zillow

- ([Zillow Housing Data](https://www.zillow.com/research/data/))
- CSV Data Name - house_values_zillow.csv
- ([Licensing for public records:](https://www.zillow.com/corp/PublicDataTerms.htm))

#### US Department of Education

- ([DataSetURL](https://collegescorecard.ed.gov/data/))
- ([Licensing/Copyright](https://www2.ed.gov/notices/copyright/index.html))

#### Bureau of Engraving and Printing

- ([bep.gov](https://www.bep.gov/currency/production-figures/annual-production-reports))
- ([Licensing](https://www.bep.gov/footer/foia))

#### Michael Dataset 1

#### Michael Dataset 2

---

### Additional Research -

---

1. List additional questions that surfaced during analysis

2. Additional research identified if time was available

- The Most Valuable Housing Markets in America
- Housing market predictions: The forecast for the next 5 years
- Who is Buying a House in this Market?
- Rental income and its effect on housing prices

3. Future development or code architecture that would make continued analysis more streamlined and productive

---

### Results and Conclusions

---

---

### Sources

---

- Class Lessons
- Instructor
- Teacher Assistant
- Classmates
- Xpert Learning Assistant
- Co-Pilot
- Tutor

- ([COPILOT](https://copilot.microsoft.com/))
