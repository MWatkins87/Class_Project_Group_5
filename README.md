# Class_Project_Group_5

- Class project for group 5 team members, Michael, Terry, and Matthew.

## Module 9 Project 1

- The team will work as a group to find and analyze a dataset of choice and work in the team repository created in Github
  https://github.com/MWatkins87/Class_Project_Group_5
- @MWatkins87's Group 5 Group Project has been created as a Kanban project in Github's Project section
  https://github.com/users/MWatkins87/projects/2/views/1

- Project 1 Overview and list of requirements can be found in the DU Bootcampspot.com website
  https://bootcampspot.instructure.com/courses/5432/pages/9-project-1-overview?module_item_id=1200592

### Executive Summary

---

**Introduction to the Analysis of Real Estate Price Trends**

The recent surge in housing prices in the American real estate landscape presents a significant challenge, with conventional wisdom attributing it primarily to internal migration and a stagnant housing supply. However, contrary to expectations, regions experiencing population declines have not seen corresponding decreases in housing prices, suggesting additional influencing factors.

This study investigates alternative factors affecting housing price trends across ten selected cities, representing both booming and sluggish markets. These cities include Atlanta, Miami, Detroit, Tampa, and Las Vegas with strong market growth, and Baltimore, New Orleans, Washington D.C., San Francisco, and Portland with less robust markets.

Analysis spanning from 2012 to 2022 incorporates various variables such as population growth, homelessness, crime rates, college tuition costs, and mortgage rates to identify correlations explaining the divergent housing price trends observed.

### Overview - Data Collection, Cleanup, and Exploration Processes

---

##### _Project Dataset "house_values_zillow.csv" to Establish Housing Price Baseline_

1.  First step is to pull data from Zillow and import the data from .csv file

    ```python
    house_values_df = pd.read_csv("house_values_zillow.csv")
    ```

2.  We then set variable values for "hv_filtered, States, Cities, Metro, Years"
3.  New Filtered DataFrames were created for the "States, Cities, Metro" data
4.  Metro data required filling and rounding the data to make it easier to read (.fillna, round)
5.  Column rename, for loop, and resetting the index to the renamed "years" column organized our filtered DataFrame
6.  Column(s) drop, Transpose, and conversion to DataFrame to prepare for plotting(.drop, .transpose, pd.DataFrame)
7.  Further DF cleanup with iloc to remove additional reference to 2nd Washington City column and for loop with .plot command to plot the median home prices n the target cities.
8.  Plot output for median house prices in the 10 target cities

#### _mathew_watkins.ipynb_

##### _Dataset collected for Average College Tuition Costs_

1. First step is to pull data from US Dept of Education and import the data from .csv file

   ```python
   college_data21_22 = pd.read_csv("../Resources/data/MERGED2021_22_PP.csv", low_memory=False)
   ```

2. We then a new DataFrame and created our Column selection for the ne DF
3. New Filtered DataFrames were created for the "States, Cities" data
4. The DF was further flattened removing un-needed columns
5. The DF was grouped by city and the mean was calculated for each city average tuition cost(.groupby, .mean())
6. Column renamed for clarity and further sorting (.rename)
7. Now that we have a data set for each year I concatenated them together into one DataFrame

   ```python
   merged_college_cost = pd.concat([by_city_13, by_city_14, by_city_15, by_city_16, by_city_17, by_city_18, by_city_19, by_city_20, by_city_21, by_city_22], axis="columns", join="inner")
   ```

8. The DF was transposed to prepare for plotting (.transpose())

   ```python
   merged_college_cost = merged_college_cost.transpose()
   ```

9. This for loop goes through each city in the cities list we made earlier and plots a bar graph so we can see the change over 10 years

   ```python
   for city in cities:
     current_college_city = merged_college_cost[[city]].plot(kind="bar", title=city, legend=False, ylabel='Average Tuition Cost')
   plt.show()
   ```

##### _Scholastic Aptitude Dataset_

1. First step is to pull data from US Dept of Education and import the data from .csv file

   ```python
   sat_data21_22 = pd.read_csv("../Resources/data/MERGED2021_22_PP.csv", low_memory=False)
   ```

2. We then a new DataFrame and created our Column selection for the ne DF
3. New Filtered DataFrames were created for the "States, Cities" data
4. The DF was further flattened pulling only "CITY","SAT_AVG" columns
5. The DF was further refined with .dropna to clear out NaN's
6. The DF was grouped by city and the mean was calculated for each city average SAT score(.groupby, .mean())
7. Column renamed for clarity and further sorting (.rename)
8. Now that we have a data set for each year I concatenated them together into one DataFrame

   ```python
   merged_avg_sat = pd.concat([sat_data12_13, sat_data13_14, sat_data14_15, sat_data15_16, sat_data16_17, sat_data17_18, sat_data18_19, sat_data19_20, sat_data20_21, sat_data21_22], axis="columns", join="inner")
   ```

9. The DF was transposed to prepare for plotting (.transpose())

   ```python
   merged_avg_sat = merged_avg_sat.transpose()
   ```

10. This for loop goes through each city in the cities list we made earlier and plots a bar graph so we can see the change over 10 years

    ```python
    for city in cities:
      current_sat_college_city = merged_avg_sat[[city]].plot(kind="bar", title=city, legend=False, ylabel='Average SAT Scores')
    plt.show()
    ```

##### _Bureau of Engraving and Printing Dataset_

1. First step is to pull data from Bureau of Engraving and Printing by reading the data directly from the URL.

   ```python
   url = 'https://www.bep.gov/currency/production-figures/annual-production-reports'
   money = pd.read_html(url)
   money
   ```

2. The dataset was then used to define DataFrames to be merged, and cleaned

   ```python
   combined_df = money[0]
     for df in money[1:3]:
         combined_df = pd.merge(combined_df, df, on='Denomination', how='inner')
     money_df = combined_df[["FY 2012", "FY 2013", "FY 2014", "FY 2015", "FY 2016", "FY 2017", "FY 2018", "FY 2019", "FY 2020", "FY 2021", "FY 2022"]]
     for i in range(2010,2024):
         money_df = money_df.rename(columns={f"FY {i}":f"{i}"})
     money_df
   ```

3. The columns were then filtered for sum and the DF was prepared for plotting values

   ```python
   printed_money_totals_df = money_df.sum()
   printed_money_totals_df.plot(kind='bar', title='Money Printed Each Year in Billions')
   ```

#### _michael_sheridan.ipynb_

#### _terry_hood.ipynb_

### Project Approach

---

Our project began with an intensive brainstorming session, wherein we delineated the project's objectives, delineated goals, and pinpointed key variables and social contexts likely to yield impactful datasets for comparison against our foundational dataset of median housing prices.

Slack communication Direct Message channel, Slack Huddle, Google Meets, Zoom, were all identified as team communication methodologies.

Task allocation was developed and populated in a Kanban style Project in Github Project, with team members assigned specific elements to navigate through the project's trajectory. Throughout the project lifecycle, we engaged in continuous comparison of dataset discoveries, collaborated to resolve coding intricacies, and conducted thorough reviews and evaluations of each other's work as part of a rigorous quality assurance process.

Collaboratively, we delved into the analysis of our findings, endeavoring to discern their implications and uncover correlations of significance.

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

### Additional Research -

---

1. List additional questions that surfaced during analysis

2. Additional research identified if time was available

- The Most Valuable Housing Markets in America
- Housing market predictions: The forecast for the next 5 years
- Who is Buying a House in this Market?
- Rental income and its effect on housing prices

3. Future development or code architecture that would make continued analysis more streamlined and productive

### Results and Conclusions

---

### Sources

---

- Class Lessons
- Instructor
- Teacher Assistant
- Classmates
- Xpert Learning Assistant
- GitHub Copilot

* ([python](https://www.python.org/))
* ([pandas](https://pandas.pydata.org/))
* ([ChatGPT 3.5](https://chat.openai.com/))
* ([COPILOT](https://copilot.microsoft.com/))
